---
title: 'Attributi riservati di C: analisi statica nullable'
ms.date: 04/14/2020
description: Questi attributi vengono interpretati dal compilatore per fornire un'analisi statica migliore per i tipi di riferimento nullable e non nullable.
ms.openlocfilehash: 0315d78db7517541efe578d8675c0f2fe45f5aea
ms.sourcegitcommit: c91110ef6ee3fedb591f3d628dc17739c4a7071e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/15/2020
ms.locfileid: "81389863"
---
# <a name="reserved-attributes-contribute-to-the-compilers-null-state-static-analysis"></a>Gli attributi riservati contribuiscono all'analisi statica dello stato null del compilatore

In un contesto nullable, il compilatore esegue l'analisi statica del codice per determinare lo stato null di tutte le variabili di tipo riferimento:In a nullable context, the compiler performs static analysis of code to determine the null state of all reference type variables:

- *non null*: l'analisi statica ha determinato che la variabile viene assegnata a un valore non null.
- *forse null*: L'analisi statica non può determinare che a una variabile sia assegnato un valore non null.

È possibile applicare un numero di attributi che forniscono informazioni al compilatore sulla semantica delle API. Tali informazioni consentono al compilatore di eseguire l'analisi statica e determinare quando una variabile non è null. In questo articolo viene fornita una breve descrizione di ognuno di questi attributi e di come utilizzarli. Tutti gli esempi presuppongono che il linguaggio c'è 8.0 o più recente e il codice si trova in un contesto nullable.

Iniziamo con un esempio familiare. Si supponga che la libreria disponga dell'API seguente per recuperare una stringa di risorsa:Imagine your library has the following API to retrieve a resource string:

```csharp
bool TryGetMessage(string key, out string message)
```

L'esempio precedente segue `Try*` il modello familiare in .NET. Esistono due argomenti di riferimento `key` per `message` questa API: il e il parametro. Questa API ha le seguenti regole relative al nullo di questi argomenti:

- I chiamanti non `null` devono passare `key`come argomento per .
- I chiamanti possono passare `null` una variabile `message`il cui valore è come argomento per .
- Se `TryGetMessage` il `true`metodo restituisce `message` , il valore di non è null. Se il valore `false,` restituito `message` è il valore di (e il relativo stato null) è null.

La regola `key` per può essere espressa `key` dal tipo di variabile: deve essere un tipo di riferimento non nullable. Il `message` parametro è più complesso. Permette `null` come argomento, ma garantisce che, `out` in caso di esito positivo, tale argomento non sia null. Per questi scenari, è necessario un vocabolario più ricco per descrivere le aspettative.

Sono stati aggiunti diversi attributi per esprimere informazioni aggiuntive sullo stato null delle variabili. Tutto il codice scritto prima dell'introduzione di tipi di riferimento nullable in C, 8, era *null oblio.* Ciò significa che qualsiasi variabile di tipo riferimento può essere null, ma i controlli null non sono necessari. Una volta che il codice è *nullable in grado di riconoscere*, tali regole cambiano. I tipi di `null` riferimento non devono mai essere il `null` valore e i tipi di riferimento nullable devono essere confrontati prima di essere dereferenziati.

Le regole per le API sono probabilmente più `TryGetValue` complicate, come si è visto con lo scenario API. Molte delle API hanno regole più complesse per quando le `null`variabili possono o non possono essere . In questi casi, si utilizzerà uno dei seguenti attributi per esprimere tali regole:

- [AllowNull](xref:System.Diagnostics.CodeAnalysis.AllowNullAttribute): Un argomento di input non nullable può essere null.
- [DisallowNull](xref:System.Diagnostics.CodeAnalysis.DisallowNullAttribute): un argomento di input nullable non deve mai essere null.
- [MaybeNull:](xref:System.Diagnostics.CodeAnalysis.MaybeNullAttribute)un valore restituito non nullable può essere null.
- [NotNull:](xref:System.Diagnostics.CodeAnalysis.NotNullAttribute)un valore restituito nullable non sarà mai null.
- [ForseNullWhen](xref:System.Diagnostics.CodeAnalysis.MaybeNullWhenAttribute): un argomento di input non nullable può `bool` essere null quando il metodo restituisce il valore specificato.
- [NotNullWhen](xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute): un argomento di input nullable non `bool` sarà null quando il metodo restituisce il valore specificato.
- [NotNullIfNotNull:](xref:System.Diagnostics.CodeAnalysis.NotNullIfNotNullAttribute)un valore restituito non è null se l'argomento per il parametro specificato non è null.
- [DoesNotReturn:](xref:System.Diagnostics.CodeAnalysis.DoesNotReturnAttribute)un metodo non restituisce mai . In altre parole, genera sempre un'eccezione.
- [DoesNotReturnIf](xref:System.Diagnostics.CodeAnalysis.DoesNotReturnIfAttribute): questo metodo non `bool` restituisce mai se il parametro associato ha il valore specificato.

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

In un contesto `ReviewComment` `get` nullable, la funzione `null`di accesso potrebbe restituire il valore predefinito di . Il compilatore avverte che deve essere controllato prima dell'accesso. Inoltre, avvisa i chiamanti che, anche `null`se potrebbe essere , i `null`chiamanti non devono impostarlo in modo esplicito su . L'attributo `DisallowNull` specifica anche una *precondizione*, `get` non influisce sulla funzione di accesso. Utilizzare l'attributo `DisallowNull` quando si osservano queste caratteristiche su:

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

Per i motivi trattati in [Definizioni generiche e supporto di valori Null,](../../nullable-attributes.md#generic-definitions-and-nullability) tale tecnica non funziona con i metodi generici. Si può avere un metodo generico che segue un modello simile:You may have a generic method that follows a similar pattern:

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

Il codice precedente esprime chiaramente il contratto esistente: `null` i chiamanti possono passare una variabile con il valore, ma il valore restituito è garantito per non essere mai null. `NotNull` L'attributo è `ref` `out` più `null` utile per e argomenti in cui può essere passato come argomento, ma tale argomento è garantito per essere non null quando il metodo restituisce.

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

## <a name="verify-unreachable-code"></a>Verificare il codice non raggiungibileVerify unreachable code

Alcuni metodi, in genere helper di eccezione o altri metodi di utilità, vengono sempre chiusi generando un'eccezione. In alternativa, un helper può generare un'eccezione in base al valore di un argomento booleano.

Nel primo caso, è `DoesNotReturn` possibile aggiungere l'attributo alla dichiarazione del metodo. Il compilatore ti aiuta in tre modi. In primo luogo, il compilatore genera un avviso se è presente un percorso in cui il metodo può uscire senza generare un'eccezione. In secondo luogo, il compilatore contrassegna qualsiasi codice dopo `catch` una chiamata a tale metodo come *irraggiungibile,* finché non viene rilevata una clausola appropriata. In terzo luogo, il codice non raggiungibile non influirà su eventuali stati null. Si consideri il metodo seguente:

```csharp
[DoesNotReturn]
private void FailFast()
{
   throw new InvalidOperationException();
}

public void SetState(object containedField)
{
   if (!isInitialized)
      FailFast();

   // unreachable code:
   this.field = containedField;
}
```

Nel secondo caso, aggiungere `DoesNotReturnIf` l'attributo a un parametro booleano del metodo. È possibile modificare l'esempio precedente come segue:

```csharp
private void FailFast([DoesNotReturnIf(false)]bool isValid)
{
   if (!isValid)
       throw new InvalidOperationException();
}

public void SetState(object containedField)
{
   FailFast(isInitialized);

   // unreachable code when "isInitialized" is false:
   this.field = containedField;
}
```

## <a name="summary"></a>Summary

L'aggiunta di tipi di riferimento nullable fornisce un vocabolario iniziale per descrivere le aspettative delle API per le variabili che potrebbero essere `null`. Gli attributi aggiuntivi forniscono un vocabolario più ricco per descrivere lo stato null delle variabili come precondizioni e postcondizioni. Questi attributi descrivono in modo più chiaro le aspettative e offrono un'esperienza migliore per gli sviluppatori che usano le API.

Quando si aggiornano le librerie per un contesto nullable, aggiungere questi attributi per guidare gli utenti delle API all'utilizzo corretto. Questi attributi consentono di descrivere completamente lo stato null degli argomenti di input e dei valori restituiti:These attributes help you fully describe the null-state of input arguments and return values:

- [AllowNull](xref:System.Diagnostics.CodeAnalysis.AllowNullAttribute): Un argomento di input non nullable può essere null.
- [DisallowNull](xref:System.Diagnostics.CodeAnalysis.DisallowNullAttribute): un argomento di input nullable non deve mai essere null.
- [MaybeNull:](xref:System.Diagnostics.CodeAnalysis.MaybeNullAttribute)un valore restituito non nullable può essere null.
- [NotNull:](xref:System.Diagnostics.CodeAnalysis.NotNullAttribute)un valore restituito nullable non sarà mai null.
- [ForseNullWhen](xref:System.Diagnostics.CodeAnalysis.MaybeNullWhenAttribute): un argomento di input non nullable può `bool` essere null quando il metodo restituisce il valore specificato.
- [NotNullWhen](xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute): un argomento di input nullable non `bool` sarà null quando il metodo restituisce il valore specificato.
- [NotNullIfNotNull:](xref:System.Diagnostics.CodeAnalysis.NotNullIfNotNullAttribute)un valore restituito non è null se l'argomento di input per il parametro specificato non è null.
- [DoesNotReturn:](xref:System.Diagnostics.CodeAnalysis.DoesNotReturnAttribute)un metodo non restituisce mai . In altre parole, genera sempre un'eccezione.
- [DoesNotReturnIf](xref:System.Diagnostics.CodeAnalysis.DoesNotReturnIfAttribute): questo metodo non `bool` restituisce mai se il parametro associato ha il valore specificato.
