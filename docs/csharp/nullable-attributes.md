---
title: Aggiornare le API con attributi per definire le aspettative null
description: Questo articolo illustra le motivazioni e le tecniche per l'aggiunta di attributi descrittivi per descrivere lo stato null degli argomenti e i valori restituiti dalle API
ms.date: 07/31/2019
ms.openlocfilehash: fedd701fb7a3bcdff96fc1abc5451cc59c01f34f
ms.sourcegitcommit: 9c3a4f2d3babca8919a1e490a159c1500ba7a844
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/12/2019
ms.locfileid: "72291316"
---
# <a name="update-libraries-to-use-nullable-reference-types-and-communicate-nullable-rules-to-callers"></a>Aggiornare le librerie per usare i tipi di riferimento nullable e comunicare le regole Nullable ai chiamanti

L'aggiunta di [tipi di riferimento Nullable](nullable-references.md) significa che è possibile dichiarare se è consentito o meno un valore `null` per ogni variabile. Che offre un'esperienza ottimale durante la scrittura del codice. Si ottengono avvisi se una variabile che non ammette i valori null può essere impostata su `null`. Si ottengono avvisi se una variabile nullable non è controllata da null prima di dereferenziarla. L'aggiornamento delle librerie può richiedere tempo, ma i profitti valgono. Le informazioni fornite al compilatore *quando* un valore `null` sono consentite o proibite, gli avvisi migliori che gli utenti dell'API otterranno. Iniziamo con un esempio familiare. Si supponga che la libreria disponga dell'API seguente per recuperare una stringa di risorsa:

```csharp
bool TryGetMessage(string key, out string message)
```

L'esempio precedente segue il noto modello `Try*` in .NET. Esistono due argomenti di riferimento per questa API: il `key` e il parametro `message`. Questa API presenta le regole seguenti relative al valore null di questi argomenti:

- I chiamanti non devono passare `null` come argomento per `key`.
- I chiamanti possono passare una variabile il cui valore è `null` come argomento per `message`.
- Se il metodo `TryGetMessage` restituisce `true`, il valore di `message` non è null. Se il valore restituito è `false,` il valore di `message` (e il relativo stato null) è null.

La regola per `key` può essere interamente espressa dal tipo di variabile: `key` deve essere un tipo di riferimento non nullable. Il parametro `message` è più complesso. Consente `null` come argomento, ma garantisce che, in seguito all'esito positivo, l'argomento `out` non sia null. Per questi scenari, è necessario un vocabolario più completo per descrivere le aspettative.

Per aggiornare la libreria per i riferimenti Nullable è necessario più di spruzzare `?` per alcune delle variabili e i nomi dei tipi. L'esempio precedente mostra che è necessario esaminare le API e prendere in considerazione le aspettative per ogni argomento di input. Prendere in considerazione le garanzie per il valore restituito e qualsiasi argomento `out` o `ref` al ritorno del metodo. Comunicare quindi tali regole al compilatore e il compilatore fornirà avvisi quando i chiamanti non rispettano tali regole.

Questo lavoro richiede tempo. Iniziamo con le strategie per rendere la libreria o l'applicazione compatibile con i valori null, con il bilanciamento di altri requisiti e risultati finali. Si vedrà come bilanciare lo sviluppo in corso abilitando i tipi di riferimento Nullable. Verranno illustrate le esigenze per le definizioni di tipo generico. Si apprenderà come applicare gli attributi per descrivere le condizioni preliminari e successive sulle singole API.

## <a name="choose-a-nullable-strategy"></a>Scegliere una strategia Nullable

La prima scelta è se i tipi di riferimento nullable devono essere attivati o disattivati per impostazione predefinita. Sono disponibili due strategie:

- Abilitare i tipi di riferimento Nullable per l'intero progetto e disabilitarlo nel codice non pronto.
- Abilitare solo i tipi di riferimento Nullable per il codice che è stato annotato per i tipi di riferimento Nullable.

La prima strategia funziona meglio quando si aggiungono altre funzionalità alla libreria durante l'aggiornamento per i tipi di riferimento Nullable. Tutti i nuovi sviluppi supportano i valori null. Quando si aggiorna il codice esistente, si abilitano i tipi di riferimento nullable in tali classi.

Seguendo questa prima strategia, si eseguono le operazioni seguenti:

1. Abilitare i tipi Nullable per l'intero progetto aggiungendo l'elemento `<Nullable>enable</Nullable>` ai file *csproj* . 
1. Aggiungere il pragma `#nullable disable` a ogni file di origine nel progetto. 
1. Quando si lavora su ogni file, rimuovere il pragma e risolvere eventuali avvisi.

Questa prima strategia ha più lavoro iniziale per aggiungere il pragma a ogni file. Il vantaggio è che ogni nuovo file di codice aggiunto al progetto sarà abilitato per i valori null. Eventuali nuovi lavori saranno in grado di riconoscere i valori null. è necessario aggiornare solo il codice esistente.

La seconda strategia funziona meglio se la libreria è in genere stabile e l'obiettivo principale dello sviluppo è l'adozione di tipi di riferimento Nullable. Si attivano i tipi di riferimento Nullable durante l'annotazione delle API. Al termine, si abilitano i tipi di riferimento Nullable per l'intero progetto.

Seguendo questa seconda strategia si eseguono le operazioni seguenti:

1. Aggiungere il pragma `#nullable enable` al file che si desidera rendere compatibile con Nullable.
1. Risolvere tutti gli avvisi.
1. Continuare questi primi due passaggi fino a quando non è stata resa disponibile l'intera libreria Nullable.
1. Abilitare i tipi Nullable per l'intero progetto aggiungendo l'elemento `<Nullable>enable</Nullable>` ai file *csproj* . 
1. Rimuovere i pragma `#nullable enable`, perché non sono più necessari.

Questa seconda strategia ha meno lavoro in primo piano. Il compromesso consiste nel fatto che la prima attività quando si crea un nuovo file consiste nell'aggiungere il pragma e renderlo compatibile con i valori null. Se gli sviluppatori del team dimenticano, il nuovo codice si trova ora nel backlog di lavoro per rendere il codice Nullable compatibile.

La scelta di queste strategie dipende dalla quantità di attività di sviluppo attive nel progetto. Il progetto è più maturo e stabile, migliore sarà la seconda strategia. Maggiore è la maggior parte delle funzionalità sviluppate, migliore sarà la prima strategia.

## <a name="should-nullable-warnings-introduce-breaking-changes"></a>Gli avvisi Nullable introducono modifiche di rilievo?

Prima di abilitare i tipi di riferimento Nullable, le variabili sono considerate *Nullable ignare*. Quando si abilitano i tipi di riferimento Nullable, tutte queste variabili *non ammettono valori null*. Il compilatore emetterà avvisi se tali variabili non vengono inizializzate su valori non null.

Un'altra fonte di avvisi probabile è la restituzione di valori quando il valore non è stato inizializzato.

Il primo passaggio per indirizzare gli avvisi del compilatore consiste nell'usare le annotazioni `?` per il parametro e i tipi restituiti per indicare quando gli argomenti o i valori restituiti possono essere null. Quando le variabili di riferimento non devono essere null, la dichiarazione originale è corretta. Quando si esegue questa operazione, l'obiettivo non è solo correggere gli avvisi. L'obiettivo più importante è fare in modo che il compilatore conosca le finalità dei potenziali valori null. Quando si esaminano gli avvisi, si raggiunge la decisione principale successiva per la raccolta. Si desidera modificare le firme dell'API per comunicare in modo più chiaro lo scopo della progettazione? Una firma API migliore per il metodo `TryGetMessage` esaminato in precedenza potrebbe essere:

```csharp
string? TryGetMessage(string key);
```

Il valore restituito indica l'esito positivo o negativo e contiene il valore se il valore è stato trovato. In molti casi, la modifica delle firme API può migliorare il modo in cui comunicano i valori null.

Tuttavia, per le librerie pubbliche o le librerie con basi utente di grandi dimensioni, è preferibile non introdurre modifiche alla firma dell'API. Per questi casi e altri modelli comuni, è possibile applicare attributi per definire in modo più chiaro quando un argomento o un valore restituito può essere `null`. Indipendentemente dalla possibilità di modificare la superficie dell'API, probabilmente si noterà che le annotazioni di tipo non sono sufficienti per descrivere i valori `null` per gli argomenti o i valori restituiti. In questi casi, è possibile applicare gli attributi per descrivere più chiaramente un'API. 

## <a name="attributes-extend-type-annotations"></a>Attributi estensione delle annotazioni di tipo

Sono stati aggiunti diversi attributi per esprimere informazioni aggiuntive sullo stato null delle variabili. Tutto il codice scritto prima C# di 8 introduce i tipi di riferimento Nullable è un *valore null ignaro*. Ciò significa che qualsiasi variabile di tipo riferimento può essere null, ma non sono necessari controlli null. Quando il codice *ammette i valori null*, tali regole cambiano. I tipi di riferimento non devono mai essere il valore `null` e i tipi di riferimento nullable devono essere controllati rispetto a `null` prima di essere dereferenziati.

Le regole per le API sono probabilmente più complesse, come si è visto con lo scenario dell'API `TryGetValue`. Molte API hanno regole più complesse quando le variabili possono o non possono essere `null`. In questi casi, si userà uno degli attributi seguenti per esprimere queste regole:

- [AllowNull](xref:System.Diagnostics.CodeAnalysis.AllowNullAttribute): Un argomento di input che non ammette i valori null può essere null.
- [DisallowNull](xref:System.Diagnostics.CodeAnalysis.DisallowNullAttribute): Un argomento di input nullable non deve mai essere null.
- [MaybeNull](xref:System.Diagnostics.CodeAnalysis.MaybeNullAttribute): Un valore restituito non nullable può essere null.
- [NotNull](xref:System.Diagnostics.CodeAnalysis.NotNullAttribute): Un valore restituito nullable non sarà mai null.
- [MaybeNullWhen](xref:System.Diagnostics.CodeAnalysis.MaybeNullWhenAttribute): Un argomento `out` o `ref` non nullable può essere null se il valore restituito soddisfa una condizione.
- [NotNullWhen](xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute): Un argomento nullable `out` o `ref` non può essere null se il valore restituito soddisfa una condizione.
- [NotNullIfNotNull](xref:System.Diagnostics.CodeAnalysis.NotNullIfNotNullAttribute): Un valore restituito non è null se l'argomento di input per il parametro specificato non è null.

Le descrizioni precedenti sono un riferimento rapido a ogni attributo. Ogni sezione seguente descrive il comportamento e il significato più approfondito.

L'aggiunta di questi attributi offre al compilatore ulteriori informazioni sulle regole per l'API. Quando il codice chiamante viene compilato in un contesto abilitato Nullable, il compilatore avvisa i chiamanti quando violano tali regole. Questi attributi non abilitano controlli aggiuntivi nell'implementazione.

## <a name="specify-preconditions-allownull-and-disallownull"></a>Specificare le precondizioni: `AllowNull` e `DisallowNull`

Si consideri una proprietà di lettura/scrittura che non restituisce mai `null` perché ha un valore predefinito ragionevole. I chiamanti passano `null` alla funzione di accesso set quando viene impostata su tale valore predefinito. Si consideri, ad esempio, un sistema di messaggistica che richiede un nome di schermata in una chat room. Se non viene specificato alcun valore, il sistema genera un nome casuale:

```csharp
public string ScreenName
{
   get => screenName;
   set => screenName = value ?? GenerateRandomScreenName();
}
private string screenName;
```

Quando si compila il codice precedente in un contesto ignaro Nullable, tutto funziona correttamente. Quando si abilitano i tipi di riferimento Nullable, la proprietà `ScreenName` diventa un riferimento non nullable. Questo è corretto per la funzione di accesso `get`: non restituisce mai `null`. I chiamanti non devono controllare la proprietà restituita per `null`. Ma ora impostando la proprietà su `null` viene generato un avviso. Per continuare a supportare questo tipo di codice, aggiungere l'attributo <xref:System.Diagnostics.CodeAnalysis.AllowNullAttribute?displayProperty=nameWithType> alla proprietà, come illustrato nel codice seguente: 

```csharp
[AllowNull]
public string ScreenName
{
   get => screenName;
   set => screenName = value ?? GenerateRandomScreenName();
}
private string screenName = GenerateRandomScreenName();
```

Per usare questo e altri attributi descritti in questo articolo, potrebbe essere necessario aggiungere una direttiva `using` per <xref:System.Diagnostics.CodeAnalysis>. L'attributo viene applicato alla proprietà, non alla funzione di accesso `set`. L'attributo `AllowNull` specifica le *condizioni preliminari*e si applica solo agli input. La funzione di accesso `get` ha un valore restituito, ma nessun argomento di input. Pertanto, l'attributo `AllowNull` si applica solo alla funzione di accesso `set`.

Nell'esempio precedente viene illustrato cosa cercare quando si aggiunge l'attributo `AllowNull` in un argomento:

1. Il contratto generale per tale variabile è che non deve essere `null`, quindi è necessario un tipo di riferimento non nullable.
1. Esistono scenari in cui la variabile di input deve essere `null`, anche se non sono l'utilizzo più comune.

Questo attributo è spesso necessario per le proprietà o per gli argomenti `in`, `out` e `ref`. L'attributo `AllowNull` è la scelta migliore quando una variabile è in genere non null, ma è necessario consentire `null` come precondizione.

Diversamente da scenari per l'utilizzo di `DisallowNull`: Usare questo attributo per specificare che una variabile di input di un tipo nullable non deve essere `null`. Si consideri una proprietà in cui `null` è il valore predefinito, ma i client possono impostarlo solo su un valore non null. Esaminare il codice seguente:

```csharp
public string ReviewComment
{
    get => _comment;
    set => _comment = value ?? throw new ArgumentNullException(nameof(value), "Cannot set to null");
}
string _comment;
```

Il codice precedente è il modo migliore per esprimere la progettazione che il `ReviewComment` potrebbe essere `null`, ma non può essere impostato su `null`. Una volta che il codice ammette i valori null, è possibile esprimere questo concetto in modo più chiaro ai chiamanti usando il <xref:System.Diagnostics.CodeAnalysis.DisallowNullAttribute?displayProperty=nameWithType>:

```csharp
[DisallowNull] 
public string? ReviewComment
{
    get => _comment;
    set => _comment = value ?? throw new ArgumentNullException(nameof(value), "Cannot set to null");
}
string? _comment;
```

In un contesto Nullable la funzione di accesso `ReviewComment` `get` può restituire il valore predefinito di `null`. Il compilatore avverte che è necessario verificarlo prima dell'accesso. Inoltre, avvisa i chiamanti che, anche se potrebbe essere `null`, i chiamanti non devono impostarlo in modo esplicito su `null`. L'attributo `DisallowNull` specifica anche una *condizione preliminare*, non influisce sulla funzione di accesso `get`. È consigliabile scegliere di usare l'attributo `DisallowNull` quando si osservano queste caratteristiche:

1. La variabile potrebbe essere `null` negli scenari principali, spesso quando ne viene creata la prima istanza.
1. La variabile non deve essere impostata in modo esplicito su `null`.

Queste situazioni sono comuni nel codice che originariamente era *null ignaro*. È possibile che le proprietà dell'oggetto siano impostate in due operazioni di inizializzazione distinte. È possibile che alcune proprietà siano impostate solo dopo il completamento di alcune operazioni asincrone.

Gli attributi `AllowNull` e `DisallowNull` consentono di specificare che le precondizioni sulle variabili potrebbero non corrispondere alle annotazioni Nullable di tali variabili. Sono disponibili informazioni più dettagliate sulle caratteristiche dell'API. Queste informazioni aggiuntive consentono ai chiamanti di usare correttamente l'API. Ricordare di specificare le precondizioni usando gli attributi seguenti:

- [AllowNull](xref:System.Diagnostics.CodeAnalysis.AllowNullAttribute): Un argomento di input che non ammette i valori null può essere null.
- [DisallowNull](xref:System.Diagnostics.CodeAnalysis.DisallowNullAttribute): Un argomento di input nullable non deve mai essere null.

## <a name="specify-post-conditions-maybenull-and-notnull"></a>Specificare le condizioni post: `MaybeNull` e `NotNull`

Si supponga di avere un metodo con la firma seguente:

```csharp
public Customer FindCustomer(string lastName, string firstName)
```

È probabile che sia stato scritto un metodo come questo per restituire `null` quando il nome cercato non è stato trovato. Il `null` indica chiaramente che il record non è stato trovato. In questo esempio è probabile che il tipo restituito venga modificato da `Customer` a `Customer?`. La dichiarazione del valore restituito come tipo di riferimento Nullable specifica lo scopo di questa API in modo chiaro. 

Per motivi trattati in [definizioni generiche e supporto di valori null,](#generic-definitions-and-nullability) la tecnica non funziona con i metodi generici. È possibile che si disponga di un metodo generico che segue un modello simile:

```csharp
public T Find<T>(IEnumerable<T> sequence, Func<T, bool> match)
```

Non è possibile specificare che il valore restituito sia `T?`. Il metodo restituisce `null` quando l'elemento cercato non viene trovato. Poiché non è possibile dichiarare un tipo restituito `T?`, si aggiunge l'annotazione `MaybeNull` al metodo restituito:

```csharp
[return: MaybeNull]
public T Find<T>(IEnumerable<T> sequence, Func<T, bool> match)
```

Il codice precedente informa i chiamanti che il contratto implica un tipo non nullable, ma il valore restituito *può* essere effettivamente null.  Usare l'attributo `MaybeNull` quando l'API deve essere un tipo non nullable, in genere un parametro di tipo generico, ma possono essere presenti istanze in cui viene restituito `null`.

È anche possibile specificare che un valore restituito o un argomento `out` o `ref` non sia null anche se il tipo è un tipo Nullable. Si consideri un metodo che garantisce che una matrice sia sufficientemente grande da mantenere un numero di elementi. Se l'argomento di input non dispone di capacità, la routine alloca una nuova matrice e copia tutti gli elementi esistenti al suo interno. Se l'argomento di input è `null`, la routine allocherà la nuova risorsa di archiviazione. Se la capacità è sufficiente, la routine non esegue alcuna operazione:

```csharp
public void EnsureCapacity<T>(ref T[] storage, int size)
```

È possibile chiamare questa routine come segue:

```csharp
// messages has the default value (null) when EnsureCapacity is called:
EnsureCapacity<string>(ref messages, 10);
// messages is not null.
EnsureCapacity<string>(messages, 50);
```

Dopo aver abilitato i tipi di riferimento null, è necessario assicurarsi che il codice precedente venga compilato senza avvisi. Quando il metodo restituisce, l'argomento `storage` è garantito che non sia null. Tuttavia, è accettabile chiamare `EnsureCapacity` con un riferimento null. È possibile rendere `storage` un tipo riferimento nullable e aggiungere la post-1 @no__t alla dichiarazione del parametro:

```csharp
public void EnsureCapacity<T>([NotNull]ref T[]? storage, int size)
```

Il codice precedente esprime molto chiaramente il contratto esistente: I chiamanti possono passare una variabile con il valore `null`, ma il valore restituito non è mai null. L'attributo `NotNull` è particolarmente utile per gli argomenti `ref` e `out` in cui `null` può essere passato come argomento, ma tale argomento è sicuramente not null quando il metodo restituisce.

È possibile specificare postcondizioni non condizionali usando gli attributi seguenti:

- [MaybeNull](xref:System.Diagnostics.CodeAnalysis.MaybeNullAttribute): Un valore restituito non nullable può essere null.
- [NotNull](xref:System.Diagnostics.CodeAnalysis.NotNullAttribute): Un valore restituito nullable non sarà mai null.

## <a name="specify-conditional-post-conditions-notnullwhen-and-maybenullwhen"></a>Specificare le condizioni postali condizionali: `NotNullWhen` e `MaybeNullWhen`

È probabile che si abbia familiarità con il metodo `string` <xref:System.String.IsNullOrEmpty(System.String)?DisplayProperty=nameWithType>. Questo metodo restituisce `true` quando l'argomento è null o una stringa vuota. Si tratta di un tipo di controllo null: I chiamanti non devono avere un valore null. controllare l'argomento se il metodo restituisce `false`. Per rendere un metodo simile a Nullable, impostare l'argomento su un tipo nullable e aggiungere l'attributo `NotNullWhen`:

```csharp
bool IsNullOrEmpty([NotNullWhen(false)]string? value);
```

Che informa il compilatore che il codice in cui il valore restituito è `false` non deve essere verificato come null. L'aggiunta dell'attributo informa l'analisi statica del compilatore che `IsNullOrEmpty` esegue il controllo null necessario: quando restituisce `false`, l'argomento di input non è `null`.

```csharp
string? userInput = GetUserInput();
if (!(string.IsNullOrEmpty(userInput))
{
   int messageLength = userInput.Length; // no null check needed.
}
// null check needed on userInput here.
```

Il metodo <xref:System.String.IsNullOrEmpty(System.String)?DisplayProperty=nameWithType> verrà annotato come illustrato in precedenza per .NET Core 3,0. Nella codebase potrebbero essere presenti metodi simili che controllano lo stato degli oggetti per i valori null. Il compilatore non riconosce i metodi di controllo null personalizzati ed è necessario aggiungervi le annotazioni. Quando si aggiunge l'attributo, l'analisi statica del compilatore sa quando la variabile testata è stata verificata come null.

Un altro uso di questi attributi è il modello `Try*`. Le postcondizioni per le variabili `ref` e `out` vengono comunicate tramite il valore restituito. Si consideri questo metodo illustrato in precedenza:

```csharp
bool TryGetMessage(string key, out string message)
```

Il metodo precedente segue un tipico linguaggio .NET: il valore restituito indica se `message` è stato impostato sul valore trovato o, se non viene trovato alcun messaggio, al valore predefinito. Se il metodo restituisce `true`, il valore di `message` non è null. in caso contrario, il metodo imposta `message` su null.

È possibile comunicare tale idioma utilizzando l'attributo `NotNullWhen`. Quando si aggiorna la firma per i tipi di riferimento Nullable, effettuare `message` a `string?` e aggiungere un attributo:

```csharp
bool TryGetMessage(string key, [NotNullWhen(true)] out string? message)
```

Nell'esempio precedente, il valore di `message` è noto come not null quando `TryGetMessage` restituisce `true`. È necessario annotare metodi simili nella codebase nello stesso modo: gli argomenti potrebbero essere `null` e sono noti come not null quando il metodo restituisce `true`.

È possibile che sia necessario anche un attributo finale. A volte lo stato null di un valore restituito dipende dallo stato null di uno o più argomenti di input. Questi metodi restituiranno un valore non null ogni volta che determinati argomenti di input non sono `null`. Per annotare correttamente questi metodi, usare l'attributo `NotNullIfNotNull`. Si consideri il seguente metodo:

```csharp
string GetTopLevelDomainFromFullUrl(string url);
```

Se l'argomento `url` non è null, l'output non è `null`. Una volta abilitati i riferimenti Nullable, la firma funziona correttamente, purché l'API non accetti mai un input null. Tuttavia, se l'input può essere null, il valore restituito può anche essere null. Pertanto, è possibile modificare la firma con il codice seguente:

```csharp
string? GetTopLevelDomainFromFullUrl(string? url);
```

Che funziona, ma spesso impone ai chiamanti di implementare controlli `null` aggiuntivi. Il contratto è che il valore restituito sarà `null` solo quando l'argomento di input `url` è `null`. Per esprimere il contratto, è necessario annotare questo metodo come illustrato nel codice seguente:

```csharp
[return: NotNullIfNotNull("url")]
string? GetTopLevelDomainFromFullUrl(string? url);
```

Il valore restituito e l'argomento sono entrambi annotati con la `?` che indica che è possibile `null`. L'attributo chiarisce ulteriormente che il valore restituito non sarà null quando l'argomento `url` non è `null`.

È possibile specificare le postcondizioni condizionali usando questi attributi:

- [MaybeNullWhen](xref:System.Diagnostics.CodeAnalysis.MaybeNullWhenAttribute): Un argomento `out` o `ref` non nullable può essere null se il valore restituito soddisfa una condizione.
- [NotNullWhen](xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute): Un argomento nullable `out` o `ref` non può essere null se il valore restituito soddisfa una condizione.
- [NotNullIfNotNull](xref:System.Diagnostics.CodeAnalysis.NotNullIfNotNullAttribute): Un valore restituito non è null se l'argomento di input per il parametro specificato non è null.

## <a name="generic-definitions-and-nullability"></a>Definizioni generiche e supporto dei valori null

La comunicazione corretta dello stato null dei tipi generici e dei metodi generici richiede particolare attenzione. Questo deriva dal fatto che un tipo di valore nullable e un tipo di riferimento nullable sono fondamentalmente diversi. Un `int?` è un sinonimo di `Nullable<int>`, mentre `string?` è `string` con un attributo aggiunto dal compilatore. Il risultato è che il compilatore non può generare codice corretto per `T?` senza sapere se `T` è un `class` o un `struct`. 

Ciò non significa che non è possibile usare un tipo Nullable (tipo di valore o tipo di riferimento) come argomento di tipo per un tipo generico chiuso. @No__t-0 e `List<int?>` sono istanze valide di `List<T>`. 

Ciò significa che non è possibile usare `T?` in una dichiarazione di classe o metodo generica senza vincoli. Ad esempio, <xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable%7B%60%600%7D)?displayProperty=nameWithType> non verrà modificato per restituire `T?`. Per ovviare a questa limitazione, è possibile aggiungere il vincolo `struct` o `class`. Con uno di questi vincoli, il compilatore è in grado di generare il codice per `T` e `T?`.

Potrebbe essere necessario limitare i tipi utilizzati per un argomento di tipo generico in modo che siano tipi non nullable. A tale scopo, è possibile aggiungere il vincolo `notnull` a tale argomento di tipo. Quando viene applicato il vincolo, l'argomento di tipo non deve essere un tipo Nullable.

## <a name="conclusions"></a>Conclusioni

L'aggiunta di tipi di riferimento Nullable fornisce un vocabolario iniziale per descrivere le aspettative delle API per le variabili che potrebbero essere `null`. Gli attributi aggiuntivi forniscono un vocabolario più completo per descrivere lo stato null delle variabili come precondizioni e postcondizioni. Questi attributi descrivono in modo più chiaro le aspettative e offrono un'esperienza migliore per gli sviluppatori che usano le API.

Quando si aggiornano le librerie per un contesto Nullable, aggiungere questi attributi per guidare gli utenti delle API all'uso corretto. Questi attributi consentono di descrivere completamente lo stato null degli argomenti di input e dei valori restituiti:

- [AllowNull](xref:System.Diagnostics.CodeAnalysis.AllowNullAttribute): Un argomento di input che non ammette i valori null può essere null.
- [DisallowNull](xref:System.Diagnostics.CodeAnalysis.DisallowNullAttribute): Un argomento di input nullable non deve mai essere null.
- [MaybeNull](xref:System.Diagnostics.CodeAnalysis.MaybeNullAttribute): Un valore restituito non nullable può essere null.
- [NotNull](xref:System.Diagnostics.CodeAnalysis.NotNullAttribute): Un valore restituito nullable non sarà mai null.
- [MaybeNullWhen](xref:System.Diagnostics.CodeAnalysis.MaybeNullWhenAttribute): Un argomento `out` o `ref` non nullable può essere null se il valore restituito soddisfa una condizione.
- [NotNullWhen](xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute): Un argomento nullable `out` o `ref` non può essere null se il valore restituito soddisfa una condizione.
- [NotNullIfNotNull](xref:System.Diagnostics.CodeAnalysis.NotNullIfNotNullAttribute): Un valore restituito non è null se l'argomento di input per il parametro specificato non è null.
