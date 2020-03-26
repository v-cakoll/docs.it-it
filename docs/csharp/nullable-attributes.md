---
title: API di aggiornamento per i tipi di riferimento nullable con attributi che definiscono le aspettative per i valori nullUpgrade APIs for nullable reference types with attributes that define expectations for null values
description: Informazioni su come usare gli attributi descrittivi AllowNull, DisallowNull, MaybeNull, NotNull e altro ancora per descrivere completamente lo stato null delle API.
ms.technology: csharp-null-safety
ms.date: 07/31/2019
ms.openlocfilehash: ca04db800271b9b01b5b9f1482dd5a0db2cc1c35
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249244"
---
# <a name="update-libraries-to-use-nullable-reference-types-and-communicate-nullable-rules-to-callers"></a>Aggiornare le librerie per utilizzare tipi di riferimento nullable e comunicare regole nullable ai chiamantiUpdate libraries to use nullable reference types and communicate nullable rules to callers

L'aggiunta di tipi di [riferimento nullable](nullable-references.md) `null` significa che è possibile dichiarare se un valore è consentito o previsto per ogni variabile. Inoltre, è possibile applicare una `AllowNull`serie `DisallowNull` `MaybeNull`di `NotNull` `NotNullWhen`attributi: , , , , `MaybeNullWhen`, e `NotNullWhenNotNull` per descrivere completamente gli stati null dei valori argument e return . Ciò offre un'esperienza eccezionale durante la scrittura del codice. Si ricevono avvisi se una variabile non `null`nullable può essere impostata su . Si ricevono avvisi se una variabile nullable non è sottoposta a controllo null prima di dereferenziarla. L'aggiornamento delle librerie può richiedere tempo, ma i payoff ne valgono la pena. Maggiore è il numero di informazioni `null` fornite al compilatore su *quando* un valore è consentito o non consentito, migliore sarà il otter degli utenti dell'API. Iniziamo con un esempio familiare. Si supponga che la libreria disponga dell'API seguente per recuperare una stringa di risorsa:Imagine your library has the following API to retrieve a resource string:

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

Le regole per le API sono probabilmente più `TryGetValue` complicate, come si è visto con lo scenario API. Molte delle API hanno regole più complesse per quando le `null`variabili possono o non possono essere . In questi casi, si utilizzerà uno dei seguenti attributi per esprimere tali regole:

- [AllowNull](xref:System.Diagnostics.CodeAnalysis.AllowNullAttribute): Un argomento di input non nullable può essere null.
- [DisallowNull](xref:System.Diagnostics.CodeAnalysis.DisallowNullAttribute): un argomento di input nullable non deve mai essere null.
- [MaybeNull:](xref:System.Diagnostics.CodeAnalysis.MaybeNullAttribute)un valore restituito non nullable può essere null.
- [NotNull:](xref:System.Diagnostics.CodeAnalysis.NotNullAttribute)un valore restituito nullable non sarà mai null.
- [ForseNullWhen](xref:System.Diagnostics.CodeAnalysis.MaybeNullWhenAttribute): un argomento di input non nullable può `bool` essere null quando il metodo restituisce il valore specificato.
- [NotNullWhen](xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute): un argomento di input nullable non `bool` sarà null quando il metodo restituisce il valore specificato.
- [NotNullIfNotNull:](xref:System.Diagnostics.CodeAnalysis.NotNullIfNotNullAttribute)un valore restituito non è null se l'argomento per il parametro specificato non è null.

Le descrizioni precedenti sono un riferimento rapido alle operazioni eseguite da ogni attributo. Ogni sezione seguente descrive il comportamento e il significato in modo più approfondito.

L'aggiunta di questi attributi fornisce al compilatore ulteriori informazioni sulle regole per l'API. Quando il codice chiamante viene compilato in un contesto abilitato nullable, il compilatore avviserà i chiamanti quando violano tali regole. Questi attributi non abilitano controlli aggiuntivi sull'implementazione.

## <a name="specify-preconditions-allownull-and-disallownull"></a>Specificare le `AllowNull` precondizioni: e`DisallowNull`

Si consideri una proprietà `null` di lettura/scrittura che non restituisce mai perché ha un valore predefinito ragionevole. I chiamanti passano `null` alla funzione di accesso set quando lo impostano sul valore predefinito. Si consideri, ad esempio, un sistema di messaggistica che richiede un nome di schermata in una chat room. Se non viene fornito alcun nome, il sistema genera un nome casuale:If noe is provided, the system generates a random name:

```csharp
public string ScreenName
{
   get => screenName;
   set => screenName = value ?? GenerateRandomScreenName();
}
private string screenName;
```

Quando si compila il codice precedente in un contesto ignario nullable, tutto va bene. Dopo aver abilitato i tipi `ScreenName` di riferimento nullable, la proprietà diventa un riferimento non nullable. Questo è corretto `get` per la funzione `null`di accesso: non restituisce mai . I chiamanti non devono controllare la `null`proprietà restituita per . Ma ora l'impostazione della proprietà su `null` genera un avviso. Per continuare a supportare questo tipo di <xref:System.Diagnostics.CodeAnalysis.AllowNullAttribute?displayProperty=nameWithType> codice, aggiungere l'attributo alla proprietà, come illustrato nel codice seguente:

```csharp
[AllowNull]
public string ScreenName
{
   get => screenName;
   set => screenName = value ?? GenerateRandomScreenName();
}
private string screenName = GenerateRandomScreenName();
```

Potrebbe essere necessario `using` aggiungere <xref:System.Diagnostics.CodeAnalysis> una direttiva per utilizzare questo e altri attributi illustrati in questo articolo. L'attributo viene applicato alla `set` proprietà, non alla funzione di accesso. L'attributo `AllowNull` specifica le *precondizioni*e si applica solo agli input. La `get` funzione di accesso ha un valore restituito, ma nessun argomento di input. Pertanto, `AllowNull` l'attributo `set` si applica solo alla funzione di accesso.

Nell'esempio precedente viene illustrato cosa `AllowNull` cercare quando si aggiunge l'attributo su un argomento:The preceding example demonstrates what to look for when adding the attribute on an argument:

1. Il contratto generale per tale variabile è `null`che non deve essere , pertanto si desidera un tipo di riferimento non nullable.
1. Esistono scenari affinché la `null`variabile di input sia , anche se non sono l'utilizzo più comune.

Molto spesso questo attributo è necessario `in` `out`per `ref` le proprietà o , e gli argomenti . L'attributo `AllowNull` è la scelta migliore quando una variabile è `null` in genere non null, ma è necessario consentire come precondizione.

A differenza di `DisallowNull`ciò con gli scenari per l'utilizzo: questo attributo viene `null`utilizzato per specificare che una variabile di input di un tipo di riferimento nullable non deve essere . Si consideri `null` una proprietà in cui è il valore predefinito, ma i client possono impostarla solo su un valore non null. Esaminare il codice seguente:

```csharp
public string ReviewComment
{
    get => _comment;
    set => _comment = value ?? throw new ArgumentNullException(nameof(value), "Cannot set to null");
}
string _comment;
```

Il codice precedente è il modo migliore `ReviewComment` per `null`esprimere il progetto che `null`potrebbe essere , ma non può essere impostato su . Una volta che questo codice è nullable in grado di <xref:System.Diagnostics.CodeAnalysis.DisallowNullAttribute?displayProperty=nameWithType>riconoscere, è possibile esprimere questo concetto in modo più chiaro ai chiamanti utilizzando il:

```csharp
[DisallowNull]
public string? ReviewComment
{
    get => _comment;
    set => _comment = value ?? throw new ArgumentNullException(nameof(value), "Cannot set to null");
}
string? _comment;
```

In un contesto `ReviewComment` `get` nullable, la funzione `null`di accesso potrebbe restituire il valore predefinito di . Il compilatore avverte che deve essere controllato prima dell'accesso. Inoltre, avvisa i chiamanti che, anche `null`se potrebbe essere , i `null`chiamanti non devono impostarlo in modo esplicito su . L'attributo `DisallowNull` specifica anche una *precondizione*, `get` non influisce sulla funzione di accesso. È consigliabile scegliere `DisallowNull` di utilizzare l'attributo quando si osservano queste caratteristiche su:

1. La variabile `null` potrebbe essere in scenari principali, spesso quando viene creata la prima istanza.
1. La variabile non deve essere `null`impostata in modo esplicito su .

Queste situazioni sono comuni nel codice che in origine era *null oblio .* È possibile che le proprietà dell'oggetto siano impostate in due operazioni di inizializzazione distinte. È possibile che alcune proprietà vengano impostate solo dopo il completamento di alcune operazioni asincrone.

Gli `AllowNull` `DisallowNull` attributi e consentono di specificare che le precondizioni sulle variabili potrebbero non corrispondere alle annotazioni nullable in tali variabili. Questi forniscono maggiori dettagli sulle caratteristiche dell'API. Queste informazioni aggiuntive consentono ai chiamanti di utilizzare correttamente l'API. Tenere presente che si specificano le precondizioni utilizzando i seguenti attributi:

- [AllowNull](xref:System.Diagnostics.CodeAnalysis.AllowNullAttribute): Un argomento di input non nullable può essere null.
- [DisallowNull](xref:System.Diagnostics.CodeAnalysis.DisallowNullAttribute): un argomento di input nullable non deve mai essere null.

## <a name="specify-post-conditions-maybenull-and-notnull"></a>Specificare le `MaybeNull` post-condizioni: e`NotNull`

Si supponga di disporre di un metodo con la firma seguente:

```csharp
public Customer FindCustomer(string lastName, string firstName)
```

Probabilmente hai scritto un metodo `null` come questo per restituire quando il nome cercato non è stato trovato. Indica `null` chiaramente che il record non è stato trovato. In questo esempio, è probabile che `Customer` si `Customer?`modifichi il tipo restituito da a . La dichiarazione del valore restituito come tipo di riferimento nullable specifica chiaramente lo scopo di questa API.

Per i motivi trattati in [Definizioni generiche e supporto di valori Null,](#generic-definitions-and-nullability) tale tecnica non funziona con i metodi generici. Si può avere un metodo generico che segue un modello simile:You may have a generic method that follows a similar pattern:

```csharp
public T Find<T>(IEnumerable<T> sequence, Func<T, bool> match)
```

Non è possibile specificare che `T?`il valore restituito sia . Il metodo `null` restituisce quando l'elemento cercato non viene trovato. Poiché non è `T?` possibile dichiarare un `MaybeNull` tipo restituito, aggiungere l'annotazione al metodo restituito:Since you can't declare a return type, you add the annotation to the method return:

```csharp
[return: MaybeNull]
public T Find<T>(IEnumerable<T> sequence, Func<T, bool> match)
```

Il codice precedente informa i chiamanti che il contratto implica un tipo non nullable, ma il valore restituito *può* effettivamente essere null.  Usare `MaybeNull` l'attributo quando l'API deve essere un tipo non nullable, `null` in genere un parametro di tipo generico, ma possono essere presenti istanze in cui verrebbero restituite.

È inoltre possibile specificare che `out` `ref` un valore restituito o un argomento o non è null anche se il tipo è un tipo di riferimento nullable. Si consideri un metodo che garantisce che una matrice sia sufficientemente grande da contenere un numero di elementi. Se l'argomento di input non dispone di capacità, la routine allocherebbe una nuova matrice e copia tutti gli elementi esistenti in essa. Se l'argomento `null`input è , la routine allocherà nuova risorsa di archiviazione. Se la capacità è sufficiente, la routine non esegue alcuna operazione:If there's sufficient capacity, the routine does nothing:

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

Dopo aver abilitato i tipi di riferimento null, si desidera assicurarsi che il codice precedente venga compilato senza avvisi. Quando il metodo `storage` restituisce , l'argomento è garantito non essere null. Tuttavia, è accettabile `EnsureCapacity` chiamare con un riferimento null. È possibile `storage` creare un tipo di `NotNull` riferimento nullable e aggiungere la post-condizione alla dichiarazione del parametro:You can make a nullable reference type, and add the post-condition to the parameter declaration:

```csharp
public void EnsureCapacity<T>([NotNull]ref T[]? storage, int size)
```

Il codice precedente esprime chiaramente il contratto esistente: i `null` chiamanti possono passare una variabile con il valore , ma il valore restituito è garantito per non essere mai null. `NotNull` L'attributo è `ref` `out` più `null` utile per e argomenti in cui può essere passato come argomento, ma tale argomento è garantito per essere non null quando il metodo restituisce.

Le condizioni postcondizionali incondizionate vengono specificate utilizzando i seguenti attributi:

- [MaybeNull:](xref:System.Diagnostics.CodeAnalysis.MaybeNullAttribute)un valore restituito non nullable può essere null.
- [NotNull:](xref:System.Diagnostics.CodeAnalysis.NotNullAttribute)un valore restituito nullable non sarà mai null.

## <a name="specify-conditional-post-conditions-notnullwhen-maybenullwhen-and-notnullifnotnull"></a>Specificare post-condizioni condizionali: `NotNullWhen`, `MaybeNullWhen`, e`NotNullIfNotNull`

È probabile che si `string` <xref:System.String.IsNullOrEmpty(System.String)?DisplayProperty=nameWithType>abbia familiarità con il metodo . Questo metodo `true` restituisce quando l'argomento è null o una stringa vuota. È una forma di controllo null: i chiamanti non devono controllare i `false`valori Null dell'argomento se il metodo restituisce . Per rendere un metodo come questo nullable aware, è necessario impostare l'argomento su un tipo di riferimento nullable e aggiungere l'attributo:To make a method like this nullable aware, you'd set the argument to a nullable reference type, and add the `NotNullWhen` attribute:

```csharp
bool IsNullOrEmpty([NotNullWhen(false)]string? value);
```

In questo modo viene informa il `false` compilatore che qualsiasi codice in cui il valore restituito non deve essere controllato con null. L'aggiunta dell'attributo informa l'analisi statica del compilatore che `IsNullOrEmpty` esegue il controllo null necessario: quando restituisce `false`, l'argomento di input non `null`è .

```csharp
string? userInput = GetUserInput();
if (!string.IsNullOrEmpty(userInput))
{
   int messageLength = userInput.Length; // no null check needed.
}
// null check needed on userInput here.
```

Il <xref:System.String.IsNullOrEmpty(System.String)?DisplayProperty=nameWithType> metodo verrà annotato come illustrato in precedenza per .NET Core 3.0. È possibile disporre di metodi simili nella codebase che controllano lo stato degli oggetti per i valori null. Il compilatore non riconoscerà i metodi di controllo null personalizzati e sarà necessario aggiungere le annotazioni manualmente. Quando si aggiunge l'attributo, l'analisi statica del compilatore sa quando la variabile testata è stata controllata con null.

Un altro utilizzo per `Try*` questi attributi è il modello. Le postcondizioni per `ref` e `out` le variabili vengono comunicate tramite il valore restituito. Si consideri questo metodo illustrato in precedenza:Consider this method shown earlier:

```csharp
bool TryGetMessage(string key, out string message)
```

Il metodo precedente segue un tipico linguaggio .NET: il `message` valore restituito indica se è stato impostato sul valore trovato o, se non viene trovato alcun messaggio, sul valore predefinito. Se il `true`metodo restituisce `message` , il valore di non è null; in caso contrario, il metodo imposta `message` su null.

È possibile comunicare tale idioma utilizzando l'attributo `NotNullWhen` . Quando si aggiorna la firma per `message` i `string?` tipi di riferimento nullable, creare un attributo e aggiungere un attributo:

```csharp
bool TryGetMessage(string key, [NotNullWhen(true)] out string? message)
```

Nell'esempio precedente, il `message` valore di è noto per essere non null quando `TryGetMessage` restituisce `true`. È necessario annotare metodi simili nella codebase nello `null`stesso modo: gli argomenti potrebbero essere `true`, e sono noti per non essere null quando il metodo restituisce .

C'è un attributo finale che potrebbe anche essere necessario. Talvolta lo stato null di un valore restituito dipende dallo stato null di uno o più argomenti di input. Questi metodi restituiranno un valore non null ogni `null`volta che determinati argomenti di input non sono . Per annotare correttamente questi `NotNullIfNotNull` metodi, utilizzare l'attributo . Si consideri il metodo seguente:Consider the following method:

```csharp
string GetTopLevelDomainFromFullUrl(string url);
```

Se `url` l'argomento non è null, `null`l'output non è . Una volta abilitati i riferimenti nullable, tale firma funziona correttamente, a condizione che l'API non accetti mai un input null. Tuttavia, se l'input potrebbe essere null, quindi valore restituito potrebbe anche essere null. Pertanto, è possibile modificare la firma nel codice seguente:Therefore, you could change the signature to the following code:

```csharp
string? GetTopLevelDomainFromFullUrl(string? url);
```

Anche questo funziona, ma spesso costringe `null` i chiamanti a implementare controlli aggiuntivi. Il contratto è che `null` il valore restituito `url` `null`sarebbe solo quando l'argomento di input è . Per esprimere tale contratto, è necessario annotare questo metodo come illustrato nel codice seguente:To express that contract, you would annotate this method as shown in the following code:

```csharp
[return: NotNullIfNotNull("url")]
string? GetTopLevelDomainFromFullUrl(string? url);
```

Il valore restituito e l'argomento sono stati `?` entrambi annotati con l'indicazione che uno dei due potrebbe essere `null`. L'attributo chiarisce inoltre che il valore `url` restituito non `null`sarà null quando l'argomento non è .

Le condizioni postcondizioni condizionali vengono specificate utilizzando questi attributi:

- [ForseNullWhen](xref:System.Diagnostics.CodeAnalysis.MaybeNullWhenAttribute): un argomento di input non nullable può `bool` essere null quando il metodo restituisce il valore specificato.
- [NotNullWhen](xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute): un argomento di input nullable non `bool` sarà null quando il metodo restituisce il valore specificato.
- [NotNullIfNotNull:](xref:System.Diagnostics.CodeAnalysis.NotNullIfNotNullAttribute)un valore restituito non è null se l'argomento di input per il parametro specificato non è null.

## <a name="generic-definitions-and-nullability"></a>Definizioni generiche e supporto di valori NullGeneric definitions and nullability

La comunicazione corretta dello stato null dei tipi generici e dei metodi generici richiede particolare attenzione. Ciò deriva dal fatto che un tipo di valore nullable e un tipo di riferimento nullable sono fondamentalmente diversi. Un `int?` è un sinonimo di `Nullable<int>`, `string?` `string` mentre è con un attributo aggiunto dal compilatore. Il risultato è che il compilatore `T?` non `T` può `class` generare `struct`codice corretto per senza sapere se è un o un oggetto .

Ciò non significa che non è possibile utilizzare un tipo nullable (tipo di valore o tipo di riferimento) come argomento di tipo per un tipo generico chiuso. Entrambi `List<string?>` `List<int?>` e sono valide `List<T>`istanze di .

Ciò significa che non è `T?` possibile utilizzare in una classe generica o una dichiarazione di metodo senza vincoli. Ad esempio, <xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable%7B%60%600%7D)?displayProperty=nameWithType> non verrà modificato `T?`in modo da restituire . È possibile superare questa `struct` limitazione aggiungendo il vincolo o `class` . Con uno di questi vincoli, il compilatore sa come generare codice per entrambi `T` e `T?`.

È possibile limitare i tipi utilizzati per un argomento di tipo generico come tipi non nullable. È possibile farlo aggiungendo `notnull` il vincolo su tale argomento di tipo. Quando viene applicato tale vincolo, l'argomento di tipo non deve essere un tipo nullable.

## <a name="conclusions"></a>Conclusioni

L'aggiunta di tipi di riferimento nullable fornisce un vocabolario iniziale per descrivere le aspettative delle API per le variabili che potrebbero essere `null`. Gli attributi aggiuntivi forniscono un vocabolario più ricco per descrivere lo stato null delle variabili come precondizioni e postcondizioni. Questi attributi descrivono in modo più chiaro le aspettative e offrono un'esperienza migliore per gli sviluppatori che usano le API.

Quando si aggiornano le librerie per un contesto nullable, aggiungere questi attributi per guidare gli utenti delle API all'utilizzo corretto. Questi attributi consentono di descrivere completamente lo stato null degli argomenti di input e dei valori restituiti:These attributes help you fully describe the null-state of input arguments and return values:

- [AllowNull](xref:System.Diagnostics.CodeAnalysis.AllowNullAttribute): Un argomento di input non nullable può essere null.
- [DisallowNull](xref:System.Diagnostics.CodeAnalysis.DisallowNullAttribute): un argomento di input nullable non deve mai essere null.
- [MaybeNull:](xref:System.Diagnostics.CodeAnalysis.MaybeNullAttribute)un valore restituito non nullable può essere null.
- [NotNull:](xref:System.Diagnostics.CodeAnalysis.NotNullAttribute)un valore restituito nullable non sarà mai null.
- [ForseNullWhen](xref:System.Diagnostics.CodeAnalysis.MaybeNullWhenAttribute): un argomento di input non nullable può `bool` essere null quando il metodo restituisce il valore specificato.
- [NotNullWhen](xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute): un argomento di input nullable non `bool` sarà null quando il metodo restituisce il valore specificato.
- [NotNullIfNotNull:](xref:System.Diagnostics.CodeAnalysis.NotNullIfNotNullAttribute)un valore restituito non è null se l'argomento di input per il parametro specificato non è null.
