---
title: Novità di C# 6 - Guida a C#
description: Informazioni sulle nuove funzionalità di C# versione 6
ms.date: 12/12/2018
ms.openlocfilehash: da40b4c9d4af0094fdd907c542e971ba55086e0f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79399392"
---
# <a name="whats-new-in-c-6"></a>Novità di C# 6

La versione 6.0 di C# contiene molte funzionalità che consentono agli sviluppatori di migliorare la produttività. L'effetto generale di queste funzionalità è che il codice che si scrive è più conciso e anche più leggibile. La sintassi è più semplice e lineare per molte delle procedure più comuni. È più facile visualizzare le finalità di progettazione se la sintassi è più snella. L'apprendimento approfondito di queste funzionalità consentirà di ottenere una maggiore produttività e di scrivere codice più leggibile, concentrandosi più sulle funzionalità da sviluppare che sui costrutti del linguaggio.

Il resto di questo articolo offre una panoramica di ognuna di queste funzionalità, con un collegamento per esplorare ciascuna di esse più in dettaglio. È anche possibile esplorare le funzionalità in un'[esplorazione interattiva di C# 6](../tutorials/exploration/csharp-6.yml) nella sezione delle esercitazioni.

## <a name="read-only-auto-properties"></a>Proprietà automatiche di sola lettura

Le *proprietà automatiche di sola lettura* offrono una sintassi più concisa per creare i tipi non modificabili. Si dichiara la proprietà automatica solo con una funzione di accesso get:

[!code-csharp[ReadOnlyAutoProperty](../../../samples/snippets/csharp/new-in-6/newcode.cs#ReadOnlyAutoProperty)]

Le proprietà `FirstName` e `LastName` possono essere impostate solo nel corpo del costruttore della stessa classe:

[!code-csharp[ReadOnlyAutoPropertyConstructor](../../../samples/snippets/csharp/new-in-6/newcode.cs#ReadOnlyAutoPropertyConstructor)]

Tentare di impostare `LastName` in un altro metodo genera un errore di compilazione `CS0200`:

```csharp
public class Student
{
    public string LastName { get;  }

    public void ChangeName(string newLastName)
    {
        // Generates CS0200: Property or indexer cannot be assigned to -- it is read only
        LastName = newLastName;
    }
}
```

Questa funzionalità abilita il supporto effettivo del linguaggio per la creazione di tipi non modificabili e per l'uso di sintassi più concisa e pratica per le proprietà automatiche.

Se l'aggiunta di questa sintassi non rimuove un metodo accessibile, si tratta di una [modifica compatibile a livello binario](version-update-considerations.md#binary-compatible-changes).

## <a name="auto-property-initializers"></a>Inizializzatori di proprietà automatiche

Gli *inizializzatori di proprietà automatiche* permettono di dichiarare il valore iniziale per una proprietà automatica come parte della dichiarazione di proprietà.

[!code-csharp[Initialization](../../../samples/snippets/csharp/new-in-6/newcode.cs#Initialization)]

Il membro `Grades` viene inizializzato quando viene dichiarato. Ciò rende più semplice eseguire l'inizializzazione esattamente una sola volta. L'inizializzazione fa parte della dichiarazione di proprietà e rende più semplice l'equivalenza tra l'allocazione della memoria e l'interfaccia pubblica per gli oggetti `Student`.

## <a name="expression-bodied-function-members"></a>Membri di funzione con corpo di espressione

Molti membri scritti dall'utente sono singole istruzioni che possono essere singole espressioni. Scrivere invece un membro con corpo di espressione. Funziona per i metodi e le proprietà di sola lettura. Ad esempio, un override di `ToString()` è spesso un ottimo candidato:

[!code-csharp[ToStringExpressionMember](../../../samples/snippets/csharp/new-in-6/newcode.cs#ToStringExpressionMember)]

È anche possibile usare questa sintassi per le proprietà di sola lettura:

[!code-csharp[FullNameExpressionMember](../../../samples/snippets/csharp/new-in-6/newcode.cs#FullNameExpressionMember)]

La modifica di un membro esistente in un membro con corpo di espressione è una [modifica compatibile a livello binario](version-update-considerations.md#binary-compatible-changes).

## <a name="using-static"></a>using static

L'elemento *using static* consente di importare i metodi statici di una singola classe. Specificare la classe in uso:

[!code-csharp[UsingStaticMath](../../../samples/snippets/csharp/new-in-6/newcode.cs#UsingStaticMath)]

<xref:System.Math> non contiene alcun metodo di istanza. È possibile usare `using static` anche per importare i metodi statici di una classe per una classe con metodi sia statici che di istanza. Uno degli esempi più utili è <xref:System.String>:

[!code-csharp[UsingStatic](../../../samples/snippets/csharp/new-in-6/newcode.cs#UsingStatic)]

> [!NOTE]
> In un'istruzione using static è necessario usare il nome completo della classe, `System.String`.  Non è invece possibile usare la parola chiave `string`.

Se importati da un'istruzione `static using`, i metodi di estensione sono inclusi nell'ambito solo se vengono chiamati usando la sintassi di chiamata del metodo di estensione, non se vengono chiamati come metodi statici. Questa situazione si verifica spesso nelle query LINQ. È possibile importare il modello LINQ importando <xref:System.Linq.Enumerable> o <xref:System.Linq.Queryable>.

[!code-csharp[UsingStaticLinq](../../../samples/snippets/csharp/new-in-6/newcode.cs#usingStaticLinq)]

In genere i metodi di estensione vengono chiamati usando espressioni di chiamata del metodo di estensione. Nei rari casi in cui vengono chiamati tramite la sintassi di chiamata del metodo statico, l'aggiunta del nome della classe risolve l'ambiguità.

La direttiva `static using` importa anche tutti i tipi annidati. È possibile fare riferimento a tutti i tipi nidificati senza qualifica.

## <a name="null-conditional-operators"></a>Operatori condizionali Null

L'*operatore condizionale Null* rende i controlli Null molto più semplici e fluidi. Sostituire l'operatore di accesso ai membri `.` con `?.`:

[!code-csharp[NullConditional](../../../samples/snippets/csharp/new-in-6/program.cs#NullConditional)]

Nell'esempio precedente alla variabile `first` è assegnato `null` se l'oggetto person è `null`. In caso contrario, viene assegnato il valore della proprietà `FirstName`. In particolare, l'operatore `?.` indica che questa riga di codice non genera un'eccezione `NullReferenceException` se la variabile `person` è `null`. Provoca invece un corto circuito e restituisce `null`. È anche possibile usare un operatore condizionale Null per l'accesso a una matrice o a un indicizzatore. Sostituire `[]` con `?[]` nell'espressione di indice.

L'espressione seguente restituisce un oggetto `string`, indipendentemente dal valore di `person`. Spesso questo costrutto viene usato con l'operatore *Null ridondante* per assegnare valori predefiniti quando una delle proprietà è `null`. Se l'espressione genera un corto circuito, il valore `null` restituito è tipizzato in modo da corrispondere all'espressione completa.

[!code-csharp[NullCoalescing](../../../samples/snippets/csharp/new-in-6/program.cs#NullCoalescing)]

È possibile usare `?.` anche per chiamare i metodi in modo condizionale. L'uso più comune delle funzioni membro con l'operatore condizionale Null è chiamare in modo sicuro i delegati (o i gestori degli eventi) che possono essere `null`.  A tale scopo si chiama il metodo `Invoke` del delegato usando l'operatore `?.` per accedere al membro. È possibile vedere un esempio nell'articolo sui [criteri per i delegati](../delegates-patterns.md#handling-null-delegates).

Le regole dell'operatore `?.` garantiscono che il lato sinistro dell'operatore venga valutato una sola volta. Questo abilita molti idiomi, incluso l'esempio seguente che usa i gestori degli eventi:

```csharp
// preferred in C# 6:
this.SomethingHappened?.Invoke(this, eventArgs);
```

Se ci si assicura che il lato sinistro venga valutato una sola volta, è anche possibile usare qualsiasi espressione, incluse le chiamate a metodi, nel lato sinistro dell'operatore `?.`

## <a name="string-interpolation"></a>Interpolazione di stringhe

Con C# 6 la nuova funzionalità di [interpolazione di stringhe](../language-reference/tokens/interpolated.md) consente di incorporare espressioni in una stringa. È sufficiente anteporre `$` alla stringa e usare espressioni tra `{` e `}`, anziché ordinali:

[!code-csharp[stringInterpolation](../../../samples/snippets/csharp/new-in-6/newcode.cs#FullNameExpressionMember)]

Questo esempio usa proprietà per le espressioni sostituite. È possibile usare qualsiasi espressione. Ad esempio, è possibile calcolare la media dei voti di uno studente come parte dell'interpolazione:

[!code-csharp[stringInterpolationFormat](../../../samples/snippets/csharp/new-in-6/newcode.cs#stringInterpolationFormat)]

La riga di codice precedente formatta il valore per `Grades.Average()` come numero a virgola mobile con due cifre decimali.

Spesso può essere necessario formattare la stringa prodotta usando impostazioni cultura specifiche, sfruttando il fatto che l'oggetto prodotto da un'interpolazione di stringhe può essere convertito in modo implicito in <xref:System.FormattableString?displayProperty=nameWithType>. L'istanza <xref:System.FormattableString> contiene la stringa di formato composito e i risultati della valutazione delle espressioni prima della loro conversione in stringhe. Usare i metodi <xref:System.FormattableString.ToString(System.IFormatProvider)?displayProperty=nameWithType> per specificare le impostazioni cultura quando si formatta una stringa. L'esempio seguente produce una stringa con impostazioni cultura tedesche (de-DE). Per impostazione predefinita, le impostazioni cultura tedesche usano il carattere ',' come separatore decimale e il carattere '.' come separatore delle migliaia.

```csharp
FormattableString str = $"Average grade is {s.Grades.Average()}";
var gradeStr = str.ToString(new System.Globalization.CultureInfo("de-DE"));
```

Per iniziare a usare l'interpolazione di stringhe, vedere l'esercitazione interattiva [Interpolazione di stringhe in C# ](../tutorials/exploration/interpolated-strings.yml), l'articolo [Interpolazione di stringhe](../language-reference/tokens/interpolated.md) e l'esercitazione [Interpolazione di stringhe in C#](../tutorials/string-interpolation.md).

## <a name="exception-filters"></a>Filtri eccezioni

I *filtri eccezioni* sono clausole che determinano quando deve essere applicata una clausola catch specifica. Se l'espressione usata per un filtro eccezioni restituisce `true`, la clausola catch esegue la normale elaborazione per un'eccezione. Se l'espressione restituisce `false`, la clausola `catch` viene ignorata. Un utilizzo consiste nell'esaminare le informazioni relative a un'eccezione per determinare se una clausola `catch` può elaborare l'eccezione:

[!code-csharp[ExceptionFilter](../../../samples/snippets/csharp/new-in-6/NetworkClient.cs#ExceptionFilter)]

## <a name="the-nameof-expression"></a>Espressione `nameof`

L'espressione [nameof](../language-reference/operators/nameof.md) restituisce il nome di un simbolo. È un sistema efficace per garantire il funzionamento degli strumenti ogni volta che è necessario il nome di una variabile, una proprietà o un campo membro. Uno degli usi più comuni di `nameof` è specificare il nome di un simbolo che ha causato un'eccezione:

[!code-csharp[nameof](../../../samples/snippets/csharp/new-in-6/NewCode.cs#UsingStaticString)]

Un altro uso riguarda le applicazioni basate su XAML che implementano l'interfaccia `INotifyPropertyChanged`:

[!code-csharp[nameofNotify](../../../samples/snippets/csharp/new-in-6/viewmodel.cs#nameofNotify)]

## <a name="await-in-catch-and-finally-blocks"></a>Await nei blocchi catch e finally

C# 5 presentava diverse limitazioni riguardo al punto in cui posizionare le espressioni `await`. Con C# 6 è ora possibile usare `await` nelle espressioni `catch` o `finally`. Questo uso è più frequente negli scenari di registrazione:

[!code-csharp[AwaitFinally](../../../samples/snippets/csharp/new-in-6/NetworkClient.cs#AwaitFinally)]

I dettagli sull'implementazione per l'aggiunta del supporto di `await` all'interno delle clausole `catch` e `finally` assicura che il comportamento sia coerente con il comportamento per il codice sincrono. Quando il codice eseguito in una clausola `catch` o `finally` genera un elemento, l'esecuzione cerca una clausola `catch` appropriata nel successivo blocco circostante. Se si è verificata un'eccezione, tale eccezione viene persa. Lo stesso accade con le espressioni attese nelle clausole `catch` e `finally`: viene cercato un valore `catch` appropriato e l'eccezione corrente, se presente, viene persa.  

> [!NOTE]
> Questo comportamento è il motivo per cui è consigliabile scrivere le clausole `catch` e `finally` con attenzione, per evitare l'introduzione di nuove eccezioni.

## <a name="initialize-associative-collections-using-indexers"></a>Inizializzare le raccolte associative tramite gli indicizzatori

Gli *inizializzatori di indice* sono una delle due funzionalità che rendono gli inizializzatori di insieme più coerenti con l'uso degli indici. Nelle versioni precedenti di C# gli *inizializzatori di insieme* potevano essere usati con le raccolte di stili di sequenza, includendo <xref:System.Collections.Generic.Dictionary%602>, mediante l'aggiunta di coppie chiave/valore racchiuse tra parentesi graffe:

[!code-csharp[ListInitializer](../../../samples/snippets/csharp/new-in-6/initializers.cs#CollectionInitializer)]

È possibile usare gli indicizzatori con raccolte <xref:System.Collections.Generic.Dictionary%602> e altri tipi, nei casi in cui il metodo `Add` accessibile accetta più argomenti. La nuova sintassi supporta l'assegnazione mediante l'uso di un indice nella raccolta:

[!code-csharp[DictionaryInitializer](../../../samples/snippets/csharp/new-in-6/initializers.cs#DictionaryInitializer)]

Questa funzionalità significa che i contenitori associativi possono essere inizializzati usando una sintassi simile a ciò che è stato usato per i contenitori sequenziali in diverse versioni.

## <a name="extension-add-methods-in-collection-initializers"></a>Metodi di estensione `Add` negli inizializzatori di insieme

Un'altra funzionalità che semplifica l'inizializzazione della raccolta è la possibilità di usare un *metodo di estensione* per il metodo `Add`. Questa funzionalità è stata aggiunta per la parità con Visual Basic. La funzionalità è particolarmente utile quando si usa una classe di raccolta personalizzata con un metodo di nome diverso per aggiungere semanticamente nuovi elementi.

## <a name="improved-overload-resolution"></a>Risoluzione dell'overload migliorata

Quest'ultima funzionalità probabilmente non viene notata. Esistevano costrutti in cui la versione precedente del compilatore C# poteva rilevare alcune chiamate al metodo che includevano espressioni lambda ambigue. Si consideri il metodo seguente:

[!code-csharp[AsyncMethod](../../../samples/snippets/csharp/new-in-6/overloads.cs#AsyncMethod)]

Nelle versioni precedenti di C# una chiamata a tale metodo usando la sintassi del gruppo di metodi avrebbe esito negativo:

[!code-csharp[MethodGroup](../../../samples/snippets/csharp/new-in-6/overloads.cs#MethodGroup)]

Il compilatore precedente non era in grado di distinguere correttamente `Task.Run(Action)` da `Task.Run(Func<Task>())`. Nelle versioni precedenti è necessario usare un'espressione lambda come argomento:

[!code-csharp[Lambda](../../../samples/snippets/csharp/new-in-6/overloads.cs#Lambda)]

Il compilatore C# 6 determina correttamente che `Task.Run(Func<Task>())` è una scelta migliore.

### <a name="deterministic-compiler-output"></a>Output del compilatore deterministico

L'opzione `-deterministic` indica al compilatore di produrre un assembly di output identico byte per byte per le compilazioni successive degli stessi file di origine.

Per impostazione predefinita, ogni compilazione produce un output univoco in ogni compilazione. Il compilatore aggiunge un timestamp e un GUID generato da numeri casuali. Usare questa opzione se si vuole confrontare l'output byte per byte per garantire coerenza tra le compilazioni.

Per altre informazioni, vedere l'articolo [Opzione del compilatore -deterministic](../language-reference/compiler-options/deterministic-compiler-option.md).
