---
title: Aggiornare la codebase per utilizzare tipi di riferimento nullableUpdate your codebase to use nullable reference types
description: Scegliere la strategia migliore per l'aggiornamento della codebase per l'utilizzo di tipi di riferimento nullable.
ms.technology: csharp-null-safety
ms.date: 07/31/2019
ms.openlocfilehash: b4a10863aea5c47b47c2a017afb20786b1e67528
ms.sourcegitcommit: 73aa9653547a1cd70ee6586221f79cc29b588ebd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2020
ms.locfileid: "82103527"
---
# <a name="update-libraries-to-use-nullable-reference-types-and-communicate-nullable-rules-to-callers"></a>Aggiornare le librerie per utilizzare tipi di riferimento nullable e comunicare regole nullable ai chiamantiUpdate libraries to use nullable reference types and communicate nullable rules to callers

L'aggiunta di tipi di [riferimento nullable](nullable-references.md) `null` significa che è possibile dichiarare se un valore è consentito o previsto per ogni variabile. Inoltre, è possibile applicare una `AllowNull`serie `DisallowNull` `MaybeNull`di `NotNull` `NotNullWhen`attributi: , , , , `MaybeNullWhen`, e `NotNullIfNotNull` per descrivere completamente gli stati null dei valori argument e return . Ciò offre un'esperienza eccezionale durante la scrittura del codice. Si ricevono avvisi se una variabile non `null`nullable può essere impostata su . Si ricevono avvisi se una variabile nullable non è sottoposta a controllo null prima di dereferenziarla. L'aggiornamento delle librerie può richiedere tempo, ma i payoff ne valgono la pena. Maggiore è il numero di informazioni `null` fornite al compilatore su *quando* un valore è consentito o non consentito, migliore sarà il otter degli utenti dell'API. Iniziamo con un esempio familiare. Si supponga che la libreria disponga dell'API seguente per recuperare una stringa di risorsa:Imagine your library has the following API to retrieve a resource string:

```csharp
bool TryGetMessage(string key, out string message)
```

L'esempio precedente segue `Try*` il modello familiare in .NET. Esistono due argomenti di riferimento `key` per `message` questa API: il e il parametro. Questa API ha le seguenti regole relative al nullo di questi argomenti:

- I chiamanti non `null` devono passare `key`come argomento per .
- I chiamanti possono passare `null` una variabile `message`il cui valore è come argomento per .
- Se `TryGetMessage` il `true`metodo restituisce `message` , il valore di non è null. Se il valore `false,` restituito `message` è il valore di (e il relativo stato null) è null.

La regola `key` per può essere completamente `key` espressa dal tipo di variabile: deve essere un tipo di riferimento non nullable. Il `message` parametro è più complesso. Permette `null` come argomento, ma garantisce che, `out` in caso di esito positivo, tale argomento non sia null. Per questi scenari, è necessario un vocabolario più ricco per descrivere le aspettative.

L'aggiornamento della libreria per i riferimenti nullable richiede più di spolverare `?` alcune delle variabili e dei nomi di tipo. L'esempio precedente mostra che è necessario esaminare le API e considerare le aspettative per ogni argomento di input. Considerare le garanzie per il `out` valore `ref` restituito e qualsiasi o argomenti al momento della restituzione del metodo. Comunicare quindi tali regole al compilatore e il compilatore fornirà avvisi quando i chiamanti non rispettano tali regole.

Questo lavoro richiede tempo. Iniziamo con strategie per rendere la libreria o l'applicazione compatibile con i valori Null, bilanciando al contempo altri requisiti e risultati finali. Verrà illustrato come bilanciare lo sviluppo in corso abilitando i tipi di riferimento nullable. Si apprenderanno le sfide per le definizioni di tipo generico. Imparerai ad applicare gli attributi per descrivere le pre e post-condizioni sulle singole API.

## <a name="choose-a-strategy-for-nullable-reference-types"></a>Scegliere una strategia per i tipi di riferimento nullableChoose a strategy for nullable reference types

La prima scelta è se i tipi di riferimento nullable devono essere attivati o disattivati per impostazione predefinita. Sono disponibili due strategie:

- Abilitare i tipi di riferimento nullable per l'intero progetto e disabilitarlo nel codice che non è pronto.
- Abilitare i tipi di riferimento nullable solo per il codice che è stato annotato per i tipi di riferimento nullable.

La prima strategia funziona meglio quando si aggiungono altre funzionalità alla libreria quando viene aggiornata per i tipi di riferimento nullable. Tutto il nuovo sviluppo è nullable in grado di riconoscere. Quando si aggiorna il codice esistente, si abilitano i tipi di riferimento nullable in tali classi.

Attenendosi a questa prima strategia, eseguire le operazioni seguenti:Following this first strategy, you do the following:

1. Abilitare i tipi di riferimento nullable per l'intero progetto aggiungendo l'elemento `<Nullable>enable</Nullable>` ai file *csproj.*
1. Aggiungere `#nullable disable` il pragma a ogni file di origine nel progetto.
1. Mentre si lavora su ogni file, rimuovere il pragma e risolvere eventuali avvisi.

Questa prima strategia ha più lavoro iniziale per aggiungere il pragma a ogni file. Il vantaggio è che ogni nuovo file di codice aggiunto al progetto sarà nullable abilitato. Qualsiasi nuovo lavoro sarà nullable in grado di riconoscere; solo il codice esistente deve essere aggiornato.

La seconda strategia funziona meglio se la libreria è generalmente stabile e l'obiettivo principale dello sviluppo è quello di adottare tipi di riferimento nullable. Attivare i tipi di riferimento nullable durante l'annotazione API. Al termine, si abilitano i tipi di riferimento nullable per l'intero progetto.

Seguendo questa seconda strategia si fanno le seguenti operazioni:

1. Aggiungere `#nullable enable` il pragma al file che si desidera rendere nullable consapevole.
1. Risolvere eventuali avvisi.
1. Continuare questi primi due passaggi fino a quando non è stata resa l'intera libreria nullable in grado di riconoscere.
1. Abilitare i tipi nullable per `<Nullable>enable</Nullable>` l'intero progetto aggiungendo l'elemento ai file *csproj.*
1. Rimuovere `#nullable enable` i pragma, in quanto non sono più necessari.

Questa seconda strategia ha meno lavoro in anticipo. Il compromesso è che la prima attività quando si crea un nuovo file consiste nell'aggiungere il pragma e renderlo nullable. Se gli sviluppatori del team dimenticano, che il nuovo codice è ora nel backlog del lavoro per rendere tutto il codice nullable in grado di riconoscere.

Quale di queste strategie si sceglie dipende da quanto sviluppo attivo sta avvenendo nel vostro progetto. Più il tuo progetto è maturo e stabile, migliore è la seconda strategia. Più caratteristiche vengono sviluppate, migliore è la prima strategia.

## <a name="should-nullable-warnings-introduce-breaking-changes"></a>Gli avvisi nullable devono introdurre modifiche di rilievo?

Prima di abilitare i tipi di riferimento nullable, le variabili vengono considerate *nullable oblio .* Dopo aver abilitato i tipi di riferimento nullable, tutte queste variabili non sono *nullable.* Il compilatore rilascerà avvisi se tali variabili non vengono inizializzate su valori non null.

Un'altra probabile origine di avvisi è restituire valori quando il valore non è stato inizializzato.

Il primo passaggio nell'indirizzamento `?` degli avvisi del compilatore consiste nell'utilizzare le annotazioni sui tipi parameter e return per indicare quando gli argomenti o i valori restituiti possono essere null. Quando le variabili di riferimento non devono essere null, la dichiarazione originale è corretta. In questo modo, l'obiettivo non è solo quello di correggere gli avvisi. L'obiettivo più importante è quello di rendere il compilatore comprendere l'intento per i potenziali valori null. Mentre esamini gli avvisi, raggiungi la tua prossima decisione importante per la tua biblioteca. Si vuole prendere in considerazione la modifica delle firme API per comunicare in modo più chiaro le finalità di progettazione? Una migliore firma `TryGetMessage` API per il metodo esaminato in precedenza potrebbe essere:A better API signature for the method examined earlier could be:

```csharp
string? TryGetMessage(string key);
```

Il valore restituito indica l'esito positivo o negativo e contiene il valore se il valore è stato trovato. In molti casi, la modifica delle firme API può migliorare il modo in cui comunicano valori null.

Tuttavia, per le librerie pubbliche o le librerie con basi di utenti di grandi dimensioni, è preferibile non introdurre modifiche alla firma API. In questi casi e altri modelli comuni, è possibile applicare attributi per `null`definire in modo più chiaro quando un argomento o un valore restituito può essere . Indipendentemente dal fatto che si consideri o meno la modifica della superficie dell'API, è probabile che le annotazioni di tipo da sole non sono sufficienti per descrivere `null` i valori per gli argomenti o i valori restituiti. In questi casi, è possibile applicare attributi per descrivere in modo più chiaro un'API.

## <a name="attributes-extend-type-annotations"></a>Gli attributi estendono le annotazioni di tipo

Sono stati aggiunti diversi attributi per esprimere informazioni aggiuntive sullo stato null delle variabili. Tutto il codice scritto prima dell'introduzione di tipi di riferimento nullable in C, 8, era *null oblio.* Ciò significa che qualsiasi variabile di tipo riferimento può essere null, ma i controlli null non sono necessari. Una volta che il codice è *nullable in grado di riconoscere*, tali regole cambiano. I tipi di `null` riferimento non devono mai essere il `null` valore e i tipi di riferimento nullable devono essere confrontati prima di essere dereferenziati.

Le regole per le API sono probabilmente più `TryGetValue` complicate, come si è visto con lo scenario API. Molte delle API hanno regole più complesse per quando le `null`variabili possono o non possono essere . In questi casi, userai gli attributi per esprimere tali regole. Gli attributi che descrivono la semantica dell'API sono disponibili nell'articolo [Attributi che influiscono sull'analisi nullable.](./language-reference/attributes/nullable-analysis.md)

## <a name="generic-definitions-and-nullability"></a>Definizioni generiche e supporto di valori NullGeneric definitions and nullability

La comunicazione corretta dello stato null dei tipi generici e dei metodi generici richiede particolare attenzione. Ciò deriva dal fatto che un tipo di valore nullable e un tipo di riferimento nullable sono fondamentalmente diversi. Un `int?` è un sinonimo di `Nullable<int>`, `string?` `string` mentre è con un attributo aggiunto dal compilatore. Il risultato è che il compilatore `T?` non `T` può `class` generare `struct`codice corretto per senza sapere se è un o un oggetto .

Ciò non significa che non è possibile utilizzare un tipo nullable (tipo di valore o tipo di riferimento) come argomento di tipo per un tipo generico chiuso. Entrambi `List<string?>` `List<int?>` e sono valide `List<T>`istanze di .

Ciò significa che non è `T?` possibile utilizzare in una classe generica o una dichiarazione di metodo senza vincoli. Ad esempio, <xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable%7B%60%600%7D)?displayProperty=nameWithType> non verrà modificato `T?`in modo da restituire . È possibile superare questa `struct` limitazione aggiungendo il vincolo o `class` . Con uno di questi vincoli, il compilatore sa come generare codice per entrambi `T` e `T?`.

È possibile limitare i tipi utilizzati per un argomento di tipo generico come tipi non nullable. È possibile farlo aggiungendo `notnull` il vincolo su tale argomento di tipo. Quando viene applicato tale vincolo, l'argomento di tipo non deve essere un tipo nullable.
