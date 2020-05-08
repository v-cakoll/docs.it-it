---
title: Aggiornare la codebase per usare i tipi di riferimento Nullable
description: Scegliere la strategia migliore per aggiornare la codebase per usare i tipi di riferimento Nullable.
ms.technology: csharp-null-safety
ms.date: 07/31/2019
ms.openlocfilehash: 5909eb9ffe1f5398fc2eb74848b82f8fe9516548
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/08/2020
ms.locfileid: "82975333"
---
# <a name="update-libraries-to-use-nullable-reference-types-and-communicate-nullable-rules-to-callers"></a>Aggiornare le librerie per usare i tipi di riferimento nullable e comunicare le regole Nullable ai chiamanti

L'aggiunta di [tipi di riferimento Nullable](nullable-references.md) significa che è possibile dichiarare se è `null` consentito o meno un valore per ogni variabile. Inoltre, è possibile applicare `AllowNull`diversi attributi:, `DisallowNull`, `MaybeNull`, `NotNull`, `NotNullWhen`, `MaybeNullWhen`e `NotNullIfNotNull` per descrivere completamente gli Stati null di argomenti e valori restituiti. Che offre un'esperienza ottimale durante la scrittura del codice. Si ottengono avvisi se una variabile che non ammette i valori null può `null`essere impostata su. Si ottengono avvisi se una variabile nullable non è controllata da null prima di dereferenziarla. L'aggiornamento delle librerie può richiedere tempo, ma i profitti valgono. Maggiori sono le informazioni fornite al compilatore *quando* un `null` valore è consentito o proibito, gli avvisi migliori che gli utenti dell'API otterranno. Iniziamo con un esempio familiare. Si supponga che la libreria disponga dell'API seguente per recuperare una stringa di risorsa:

```csharp
bool TryGetMessage(string key, out string message)
```

L'esempio precedente segue il modello `Try*` familiare in .NET. Per questa API sono disponibili due argomenti di riferimento: `key` e `message` . Questa API presenta le regole seguenti relative al valore null di questi argomenti:

- I chiamanti non `null` devono passare come argomento `key`per.
- I chiamanti possono passare una variabile il cui `null` valore è come argomento `message`per.
- Se il `TryGetMessage` metodo restituisce `true`, il valore di `message` non è null. Se il valore restituito è `false,` il valore di `message` (e il relativo stato null) è null.

La regola per `key` può essere interamente espressa dal tipo di variabile: `key` deve essere un tipo di riferimento non nullable. Il `message` parametro è più complesso. Consente `null` come argomento, ma garantisce che, in seguito all'esito positivo `out` , l'argomento non sia null. Per questi scenari, è necessario un vocabolario più completo per descrivere le aspettative.

Per l'aggiornamento della libreria per i riferimenti Nullable è necessario `?` più di un'irrigazione su alcune variabili e nomi di tipo. L'esempio precedente mostra che è necessario esaminare le API e prendere in considerazione le aspettative per ogni argomento di input. Prendere in considerazione le garanzie per il valore restituito e `out` gli `ref` eventuali argomenti o sul valore restituito dal metodo. Comunicare quindi tali regole al compilatore e il compilatore fornirà avvisi quando i chiamanti non rispettano tali regole.

Questo lavoro richiede tempo. Iniziamo con le strategie per rendere la libreria o l'applicazione compatibile con i valori null, con il bilanciamento di altri requisiti e risultati finali. Si vedrà come bilanciare lo sviluppo in corso abilitando i tipi di riferimento Nullable. Verranno illustrate le esigenze per le definizioni di tipo generico. Si apprenderà come applicare gli attributi per descrivere le condizioni preliminari e successive sulle singole API.

## <a name="choose-a-strategy-for-nullable-reference-types"></a>Scegliere una strategia per i tipi di riferimento Nullable

La prima scelta è se i tipi di riferimento nullable devono essere attivati o disattivati per impostazione predefinita. Sono disponibili due strategie:

- Abilitare i tipi di riferimento Nullable per l'intero progetto e disabilitarlo nel codice non pronto.
- Abilitare solo i tipi di riferimento Nullable per il codice che è stato annotato per i tipi di riferimento Nullable.

La prima strategia funziona meglio quando si aggiungono altre funzionalità alla libreria durante l'aggiornamento per i tipi di riferimento Nullable. Tutti i nuovi sviluppi supportano i valori null. Quando si aggiorna il codice esistente, si abilitano i tipi di riferimento nullable in tali classi.

Seguendo questa prima strategia, si eseguono le operazioni seguenti:

1. Abilitare i tipi di riferimento Nullable per l'intero progetto aggiungendo `<Nullable>enable</Nullable>` l'elemento ai file *csproj* .
1. Aggiungere il `#nullable disable` pragma a ogni file di origine nel progetto.
1. Quando si lavora su ogni file, rimuovere il pragma e risolvere eventuali avvisi.

Questa prima strategia ha più lavoro iniziale per aggiungere il pragma a ogni file. Il vantaggio è che ogni nuovo file di codice aggiunto al progetto sarà abilitato per i valori null. Eventuali nuovi lavori saranno in grado di riconoscere i valori null. è necessario aggiornare solo il codice esistente.

La seconda strategia funziona meglio se la libreria è in genere stabile e l'obiettivo principale dello sviluppo è l'adozione di tipi di riferimento Nullable. Si attivano i tipi di riferimento Nullable durante l'annotazione delle API. Al termine, si abilitano i tipi di riferimento Nullable per l'intero progetto.

Seguendo questa seconda strategia si eseguono le operazioni seguenti:

1. Aggiungere il `#nullable enable` pragma al file che si desidera rendere compatibile con Nullable.
1. Risolvere tutti gli avvisi.
1. Continuare questi primi due passaggi fino a quando non è stata resa disponibile l'intera libreria Nullable.
1. Abilitare i tipi Nullable per l'intero progetto aggiungendo l' `<Nullable>enable</Nullable>` elemento ai file *csproj* .
1. Rimuovere i `#nullable enable` pragma, perché non sono più necessari.

Questa seconda strategia ha meno lavoro in primo piano. Il compromesso consiste nel fatto che la prima attività quando si crea un nuovo file consiste nell'aggiungere il pragma e renderlo compatibile con i valori null. Se gli sviluppatori del team dimenticano, il nuovo codice si trova ora nel backlog di lavoro per rendere il codice Nullable compatibile.

La scelta di queste strategie dipende dalla quantità di attività di sviluppo attive nel progetto. Il progetto è più maturo e stabile, migliore sarà la seconda strategia. Maggiore è la maggior parte delle funzionalità sviluppate, migliore sarà la prima strategia.

## <a name="should-nullable-warnings-introduce-breaking-changes"></a>Gli avvisi Nullable introducono modifiche di rilievo?

Prima di abilitare i tipi di riferimento Nullable, le variabili sono considerate *Nullable ignare*. Quando si abilitano i tipi di riferimento Nullable, tutte queste variabili *non ammettono valori null*. Il compilatore emetterà avvisi se tali variabili non vengono inizializzate su valori non null.

Un'altra fonte di avvisi probabile è la restituzione di valori quando il valore non è stato inizializzato.

Il primo passaggio per indirizzare gli avvisi del compilatore consiste `?` nell'usare le annotazioni sui tipi Parameter e Return per indicare quando gli argomenti o i valori restituiti possono essere null. Quando le variabili di riferimento non devono essere null, la dichiarazione originale è corretta. Quando si esegue questa operazione, l'obiettivo non è solo correggere gli avvisi. L'obiettivo più importante è fare in modo che il compilatore conosca le finalità dei potenziali valori null. Quando si esaminano gli avvisi, si raggiunge la decisione principale successiva per la raccolta. Si desidera modificare le firme dell'API per comunicare in modo più chiaro lo scopo della progettazione? Una firma API migliore per il `TryGetMessage` metodo esaminato in precedenza potrebbe essere:

```csharp
string? TryGetMessage(string key);
```

Il valore restituito indica l'esito positivo o negativo e contiene il valore se il valore è stato trovato. In molti casi, la modifica delle firme API può migliorare il modo in cui comunicano i valori null.

Tuttavia, per le librerie pubbliche o le librerie con basi utente di grandi dimensioni, è preferibile non introdurre modifiche alla firma dell'API. Per questi casi e altri modelli comuni, è possibile applicare gli attributi per definire in modo più chiaro quando un argomento o un valore `null`restituito può essere. Indipendentemente dalla possibilità di modificare la superficie dell'API, probabilmente si noterà che le annotazioni di tipo non sono sufficienti per descrivere `null` i valori per gli argomenti o i valori restituiti. In questi casi, è possibile applicare gli attributi per descrivere più chiaramente un'API.

## <a name="attributes-extend-type-annotations"></a>Attributi estensione delle annotazioni di tipo

Sono stati aggiunti diversi attributi per esprimere informazioni aggiuntive sullo stato null delle variabili. Tutto il codice scritto prima di C# 8 ha introdotto tipi di riferimento Nullable è un *valore null ignaro*. Ciò significa che qualsiasi variabile di tipo riferimento può essere null, ma non sono necessari controlli null. Quando il codice *ammette i valori null*, tali regole cambiano. I tipi di riferimento non devono `null` mai essere il valore e i tipi di riferimento Nullable `null` devono essere controllati prima di essere dereferenziati.

Le regole per le API sono probabilmente più complesse, come si è visto con `TryGetValue` lo scenario API. Molte API hanno regole più complesse quando le variabili possono o non possono essere `null`. In questi casi, si useranno gli attributi per esprimere tali regole. Gli attributi che descrivono la semantica dell'API sono disponibili nell'articolo sugli [attributi che influiscano sull'analisi dei valori null](./language-reference/attributes/nullable-analysis.md).

## <a name="generic-definitions-and-nullability"></a>Definizioni generiche e supporto dei valori null

La comunicazione corretta dello stato null dei tipi generici e dei metodi generici richiede particolare attenzione. Questo deriva dal fatto che un tipo di valore nullable e un tipo di riferimento nullable sono fondamentalmente diversi. Un `int?` oggetto è un sinonimo `Nullable<int>`di `string?` , `string` mentre è con un attributo aggiunto dal compilatore. Il risultato è che il compilatore non può generare codice corretto `T?` per senza sapere `T` se è `class` o `struct`.

Ciò non significa che non è possibile usare un tipo Nullable (tipo di valore o tipo di riferimento) come argomento di tipo per un tipo generico chiuso. `List<string?>` E `List<int?>` sono istanze valide di `List<T>`.

Cosa significa che non è possibile usare `T?` in una dichiarazione di classe o metodo generica senza vincoli. Ad esempio, <xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable%7B%60%600%7D)?displayProperty=nameWithType> non verrà modificato in return `T?`. Per ovviare a questa limitazione, è possibile `struct` aggiungere `class` il vincolo o. Con uno di questi vincoli, il compilatore sa come generare codice sia `T` per che `T?`per.

Potrebbe essere necessario limitare i tipi utilizzati per un argomento di tipo generico in modo che siano tipi non nullable. A tale scopo, è possibile aggiungere `notnull` il vincolo su tale argomento di tipo. Quando viene applicato il vincolo, l'argomento di tipo non deve essere un tipo Nullable.

## <a name="late-initialized-properties-data-transfer-objects-and-nullability"></a>Proprietà con inizializzazione tardiva, oggetti Trasferimento dati e supporto di valori null

L'indicazione del supporto di valori Null delle proprietà che sono inizializzate in ritardo, ovvero impostate dopo la costruzione, potrebbe richiedere particolare attenzione per garantire che la classe continui a esprimere correttamente l'intento di progettazione originale.

I tipi che contengono proprietà inizializzate in ritardo, ad esempio oggetti Trasferimento dati (dto), vengono spesso creati da una libreria esterna, ad esempio un database ORM (Object Relational Mapper), un deserializzatore o un altro componente che popola automaticamente le proprietà da un'altra origine.

Si consideri la seguente classe DTO, prima di abilitare i tipi di riferimento Nullable, che rappresenta uno studente:

```csharp
class Student
{
    [Required]
    public string FirstName { get; set; }

    [Required]
    public string LastName { get; set; }

    public string VehicleRegistration { get; set; }
}
```

Lo scopo della progettazione, indicato in questo caso dall' `Required` attributo, suggerisce che in questo sistema le `FirstName` proprietà e `LastName` sono **obbligatorie**e pertanto non null.

La `VehicleRegistration` proprietà **non è obbligatoria**, pertanto può essere null.

Quando si abilitano i tipi di riferimento Nullable, si vuole indicare nel DTO quale delle proprietà può essere nullable, coerente con l'intento originale:

```csharp
class Student
{
    [Required]
    public string FirstName { get; set; }

    [Required]
    public string LastName { get; set; }

    public string? VehicleRegistration { get; set; }
}
```

Per questo DTO, l'unica proprietà che può essere null è ``VehicleRegistration``.

Tuttavia, il compilatore genera `CS8618` avvisi sia `FirstName` per che `LastName`per, per indicare che le proprietà che non ammettono i valori null non sono inizializzate.

Sono disponibili tre opzioni che consentono di risolvere gli avvisi del compilatore in modo da mantenere la finalità originale. Una di queste opzioni è valida; è consigliabile scegliere quella più adatta alle proprie esigenze di progettazione e stile di codifica.

### <a name="initialize-in-the-constructor"></a>Inizializzazione nel costruttore

Il modo ideale per risolvere gli avvisi non inizializzati consiste nell'inizializzare le proprietà nel costruttore:

```csharp
class Student
{
    public Student(string firstName, string lastName)
    {
        FirstName = firstName;
        LastName = lastName;
    }

    [Required]
    public string FirstName { get; set; }

    [Required]
    public string LastName { get; set; }

    public string? VehicleRegistration { get; set; }
}
```

Questo approccio funziona solo se la libreria utilizzata per creare un'istanza della classe supporta il passaggio di parametri nel costruttore.

Inoltre, una libreria può supportare il passaggio di *alcune* proprietà nel costruttore, ma non tutte.
Ad esempio, EF Core supporta il [binding del costruttore](/ef/core/modeling/constructors) per le proprietà di colonna normali, ma non le proprietà di navigazione.

Controllare la documentazione sulla libreria che crea un'istanza della classe, per comprendere in che misura è supportata l'associazione del costruttore.

### <a name="property-with-nullable-backing-field"></a>Proprietà con campo di supporto Nullable

Se l'associazione del costruttore non funziona per l'utente, un modo per risolvere questo problema consiste nel disporre di una proprietà che non ammette i valori null con un campo sottostante Nullable:

```csharp
private string? _firstName;

[Required]
public string FirstName
{
    set => _firstName = value;
    get => _firstName
           ?? throw new InvalidOperationException("Uninitialized " + nameof(FirstName))
}
```

In questo scenario, se si `FirstName` accede alla proprietà prima che sia stata inizializzata, il codice genera un' `InvalidOperationException`eccezione, perché il contratto API è stato usato in modo errato.

È necessario considerare che alcune librerie possono avere considerazioni speciali quando si usano i campi di backup. Ad esempio, potrebbe essere necessario configurare EF Core per l'uso corretto dei [campi di backup](/ef/core/modeling/backing-field) .

### <a name="initialize-the-property-to-null"></a>Inizializza la proprietà su null

Come alternativa Terser all'uso di un campo di supporto nullable o se la libreria che crea un'istanza della classe non è compatibile con questo approccio, è possibile semplicemente inizializzare la proprietà `null` direttamente su, con l'ausilio dell'operatore che perdona i`!`valori null ():

```csharp
[Required]
public string FirstName { get; set; } = null!;

[Required]
public string LastName { get; set; } = null!;

public string? VehicleRegistration { get; set; }
```

Non si osserverà mai un valore null effettivo in fase di esecuzione, ad eccezione di un bug di programmazione, accedendo alla proprietà prima che sia stata inizializzata correttamente.

## <a name="see-also"></a>Vedere anche

- [Eseguire la migrazione di una base di codice esistente a riferimenti nullable](tutorials/upgrade-to-nullable-references.md)
- [Utilizzo dei tipi di riferimento nullable in EF Core](/ef/core/miscellaneous/nullable-reference-types)
