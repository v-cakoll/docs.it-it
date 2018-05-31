---
title: Novità di C# 6 - Guida a C#
description: Informazioni sulle nuove funzionalità di C# versione 6
ms.date: 09/22/2016
ms.assetid: 4d879f69-f889-4d3f-a781-75194e143400
ms.openlocfilehash: c23d4f45441451fbf8a2ad2f939bdb1ed6144154
ms.sourcegitcommit: b7763f3435635850a76d4cbcf09bdce6c019208a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2018
ms.locfileid: "34483489"
---
# <a name="whats-new-in-c-6"></a>Novità di C# 6

La versione 6.0 di C# contiene molte funzionalità che consentono agli sviluppatori di migliorare la produttività. Di seguito sono riportate alcune funzionalità incluse in questa versione:

* [Proprietà automatiche di sola lettura](#read-only-auto-properties):
    - È possibile creare proprietà automatiche di sola che possono essere impostate solo nei costruttori.
* [Inizializzatori di proprietà automatiche](#auto-property-initializers):
    - È possibile scrivere espressioni di inizializzazione per impostare il valore iniziale di una proprietà automatica.
* [Membri di funzione con corpo di espressione](#expression-bodied-function-members):
    - È possibile creare metodi di una riga usando le espressioni lambda.
* [using static](#using-static):
    - È possibile importare tutti i metodi di una singola classe nello spazio dei nomi corrente.
* [Operatori condizionali Null](#null-conditional-operators):
    - È possibile accedere ai membri di un oggetto in modo conciso e sicuro durante la ricerca di Null con l'operatore condizionale Null.
* [Interpolazione di stringhe](#string-interpolation):
    - È possibile scrivere espressioni di formattazione delle stringhe usando espressioni inline anziché argomenti posizionali.
* [Filtri eccezioni](#exception-filters):
    - È possibile intercettare le espressioni in base alle proprietà dell'eccezione o di un altro stato del programma. 
* [Espressioni nameof](#nameof-expressions):
    - È possibile consentire al compilatore di generare rappresentazioni di stringa dei simboli.
* [Await nei blocchi catch e finally](#await-in-catch-and-finally-blocks):
    - È possibile usare le espressioni `await` in posizioni che in precedenza non le consentivano.
* [Inizializzatori di indice](#index-initializers):
    - È possibile creare espressioni di inizializzazione per i contenitori associativi, nonché per i contenitori sequenziali.
* [Metodi di estensione per gli inizializzatori di insieme](#extension-add-methods-in-collection-initializers):
    - Gli inizializzatori di insieme possono basarsi su metodi di estensione accessibili, oltre ai metodi membro.
* [Risoluzione dell'overload migliorata](#improved-overload-resolution):
    - Alcuni costrutti che in precedenza generavano chiamate ambigue al metodo ora risolvono correttamente.

L'effetto generale di queste funzionalità è che il codice che si scrive è più conciso e anche più leggibile. La sintassi è più semplice e lineare per molte delle procedure più comuni. È più facile visualizzare le finalità di progettazione se la sintassi è più snella. È importante acquisire dimestichezza con queste funzionalità per essere più produttivi, scrivere codice più leggibile e concentrarsi maggiormente sulle funzionalità principali e meno sui costrutti del linguaggio.

Nelle altre sezioni di questo argomento sono disponibili informazioni dettagliate su ognuna di queste funzionalità.

## <a name="auto-property-enhancements"></a>Miglioramenti delle proprietà automatiche 

La sintassi per le proprietà implementate automaticamente, in genere definite "proprietà automatiche", ha semplificato notevolmente la creazione delle proprietà con semplici funzioni di accesso get e set:

[!code-csharp[ClassicAutoProperty](../../../samples/snippets/csharp/new-in-6/oldcode.cs#ClassicAutoProperty)]

Tuttavia, la sintassi semplice ha limitato i tipi di progetti che è possibile supportare usando le proprietà automatiche. C# 6 migliora le funzionalità delle proprietà automatiche in modo che sia possibile usarle in più situazioni. Non è necessario ricorrere spesso alla sintassi più dettagliata per la dichiarazione e la modifica manuale del campo sottostante.

La nuova sintassi consente di gestire scenari per le proprietà di sola lettura e per l'inizializzazione dell'archiviazione delle variabili dietro una proprietà automatica.

### <a name="read-only-auto-properties"></a>Proprietà automatiche di sola lettura

Le *proprietà automatiche di sola lettura* offrono una sintassi più concisa per creare i tipi non modificabili. Nelle versioni precedenti di C# il massimo che è possibile ottenere per i tipi non modificabili è dichiarare setter privati:

[!code-csharp[ClassicReadOnlyAutoProperty](../../../samples/snippets/csharp/new-in-6/oldcode.cs#ClassicReadOnlyAutoProperty)]
 
Con questa sintassi il compilatore non verifica che il tipo sia effettivamente non modificabile. Si limita a imporre che le proprietà `FirstName` e `LastName` non vengano modificate da qualsiasi codice all'esterno della classe.

Le proprietà automatiche di sola lettura abilitano un vero comportamento di sola lettura. Si dichiara la proprietà automatica solo con una funzione di accesso get:

[!code-csharp[ReadOnlyAutoProperty](../../../samples/snippets/csharp/new-in-6/newcode.cs#ReadOnlyAutoProperty)]

Le proprietà `FirstName` e `LastName` possono essere impostate solo nel corpo di un costruttore:

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

Questa funzionalità abilita un effettivo supporto del linguaggio per la creazione di tipi non modificabili e l'uso della sintassi più concisa e pratica per le proprietà automatiche.

### <a name="auto-property-initializers"></a>Inizializzatori di proprietà automatiche

Gli *inizializzatori di proprietà automatiche* consentono di dichiarare il valore iniziale per una proprietà automatica come parte della dichiarazione di proprietà.  Nelle versioni precedenti queste proprietà dovevano avere dei setter che era necessario usare per inizializzare l'archiviazione dei dati usata dal campo sottostante. La classe dell'esempio seguente contiene il nome di uno studente e un elenco dei suoi voti:

[!code-csharp[Construction](../../../samples/snippets/csharp/new-in-6/oldcode.cs#Construction)]
 
Man mano che la classe aumenta, è possibile includere altri costruttori. Ogni costruttore deve inizializzare questo campo oppure verranno introdotti errori.

C# 6 consente di assegnare un valore iniziale per la memoria usata da una proprietà automatica nella dichiarazione di proprietà automatica:

[!code-csharp[Initialization](../../../samples/snippets/csharp/new-in-6/newcode.cs#Initialization)]

Il membro `Grades` viene inizializzato dove è dichiarato. Ciò rende più semplice eseguire l'inizializzazione esattamente una sola volta. L'inizializzazione fa parte della dichiarazione di proprietà e rende più semplice l'equivalenza tra l'allocazione di memoria e l'interfaccia pubblica per gli oggetti `Student`.

Gli inizializzatori di proprietà possono essere usati con proprietà di lettura/scrittura, nonché con proprietà di sola lettura, come illustrato di seguito.

[!code-csharp[ReadWriteInitialization](../../../samples/snippets/csharp/new-in-6/newcode.cs#ReadWriteInitialization)]

## <a name="expression-bodied-function-members"></a>Membri di funzione con corpo di espressione

Il corpo di molti membri che si scrivono è costituito da un'unica istruzione che può essere rappresentata come un'espressione. È possibile ridurre la sintassi scrivendo in alternativa un membro con corpo di espressione. Funziona per i metodi e le proprietà di sola lettura. Ad esempio, un override di `ToString()` è spesso un ottimo candidato:

[!code-csharp[ToStringExpressionMember](../../../samples/snippets/csharp/new-in-6/newcode.cs#ToStringExpressionMember)]

È possibile usare membri con corpo di espressione anche nelle proprietà di sola lettura:

[!code-csharp[FullNameExpressionMember](../../../samples/snippets/csharp/new-in-6/newcode.cs#FullNameExpressionMember)]

## <a name="using-static"></a>using static

L'elemento *using static* consente di importare i metodi statici di una singola classe. In precedenza l'istruzione `using` importava tutti i tipi in uno spazio dei nomi. 

Spesso i metodi statici di una classe vengono usati in tutto il codice. Digitare ripetutamente il nome della classe può nascondere il significato del codice. Un esempio comune è quando si scrivono le classi che eseguono molti calcoli numerici.
Il codice verrà riempito di <xref:System.Math.Sin%2A>, <xref:System.Math.Sqrt%2A> e altre chiamate a metodi diversi nella classe <xref:System.Math>. La nuova sintassi di `using static` può rendere le classi molto più facili da leggere. Specificare la classe in uso:

[!code-csharp[UsingStaticMath](../../../samples/snippets/csharp/new-in-6/newcode.cs#UsingStaticMath)]

A questo punto è possibile usare qualsiasi metodo statico nella classe <xref:System.Math> senza qualificare la classe <xref:System.Math>. La classe <xref:System.Math> è un caso di utilizzo ideale per questa funzionalità perché non contiene alcun metodo di istanza. È possibile usare `using static` anche per importare i metodi statici di una classe per una classe con metodi sia statici che di istanza. Uno degli esempi più utili è <xref:System.String>:

[!code-csharp[UsingStatic](../../../samples/snippets/csharp/new-in-6/newcode.cs#UsingStatic)]

> [!NOTE]
> È necessario usare il nome completo della classe, `System.String`, in un'istruzione static using. Non è invece possibile usare la parola chiave `string`. 

È ora possibile chiamare i metodi statici definiti nella classe <xref:System.String> senza qualificare tali metodi come membri della classe:

[!code-csharp[UsingStaticString](../../../samples/snippets/csharp/new-in-6/newcode.cs#UsingStaticString)]

La funzionalità `static using` e i metodi di estensione interagiscono in modi interessanti e la progettazione del linguaggio include alcune regole che riguardano espressamente tali interazioni. L'obiettivo è ridurre al minimo le probabilità di modifiche di rilievo nelle codebase esistenti, inclusa quella in uso.

I metodi di estensione sono nell'ambito solo se vengono chiamati usando la sintassi di chiamata al metodo di estensione, non se vengono chiamati come metodo statico.
Questa situazione si verifica spesso nelle query LINQ. È possibile importare il modello LINQ importando <xref:System.Linq.Enumerable>.

[!code-csharp[UsingStaticLinq](../../../samples/snippets/csharp/new-in-6/newcode.cs#usingStaticLinq)]

In questo modo tutti i metodi vengono importati nella classe <xref:System.Linq.Enumerable>.
Tuttavia, i metodi di estensione sono nell'ambito solo quando vengono chiamati come metodi di estensione. Non sono nell'ambito se vengono chiamati usando la sintassi del metodo statico:

[!code-csharp[UsingStaticLinqMethod](../../../samples/snippets/csharp/new-in-6/newcode.cs#UsingStaticLinkMethod)]

Questa decisione è dovuta al fatto che i metodi di estensione di solito vengono chiamati usando espressioni di chiamata al metodo di estensione. Nel caso improbabile in cui vengano chiamati usando la sintassi di chiamata al metodo statico il motivo è che deve essere risolta l'ambiguità.
Richiedere il nome della classe come parte della chiamata è una scelta opportuna.

Esiste un'ultima funzionalità di `static using`. La direttiva `static using` importa anche tutti i tipi annidati. Ciò consente di fare riferimento a tutti i tipi annidati senza qualifica.

## <a name="null-conditional-operators"></a>Operatori condizionali Null

I valori Null complicano il codice. È necessario controllare ogni accesso delle variabili per verificare che non vi sia dereferenziazione di `null`. L'*operatore condizionale Null* rende tali controlli molto più semplici e fluidi.

È sufficiente sostituire l'accesso ai membri `.` con `?.`:

[!code-csharp[NullConditional](../../../samples/snippets/csharp/new-in-6/program.cs#NullConditional)]

Nell'esempio precedente alla variabile `first` è assegnato `null` se l'oggetto person è `null`. In caso contrario, viene assegnato il valore della proprietà `FirstName`. In particolare, il carattere `?.` indica che questa riga di codice non genera `NullReferenceException` quando la variabile `person` è `null`. Provoca invece un corto circuito e produce `null`.

Inoltre, tenere presente che questa espressione restituisce un oggetto `string`, indipendentemente dal valore di `person`.
In caso di operazioni di corto circuito, il valore `null` restituito è tipizzato in modo da corrispondere all'espressione completa.

Spesso è possibile usare questo costrutto con l'operatore *Null ridondante* per assegnare valori predefiniti quando una delle proprietà è `null`:

[!code-csharp[NullCoalescing](../../../samples/snippets/csharp/new-in-6/program.cs#NullCoalescing)]

L'operando di destra dell'operatore `?.` non è limitato ai campi o alle proprietà.
È possibile usarlo anche per richiamare i metodi in modo condizionale. L'uso più comune delle funzioni membro con l'operatore condizionale Null è richiamare in modo sicuro i delegati (o i gestori di eventi) che possono essere `null`.  Questa operazione si esegue chiamando il metodo `Invoke` del delegato usando l'operatore `?.` per accedere al membro. È disponibile un esempio nell'argomento  
relativo ai [modelli di delegato](../delegates-patterns.md#handling-null-delegates).

Le regole dell'operatore `?.` garantiscono che il lato sinistro dell'operatore venga valutato una sola volta. Questo è importante e abilita molti idiomi, incluso l'esempio che usa i gestori eventi. Iniziamo con l'uso del gestore eventi. Nelle versioni precedenti di C# l'utente era invitato a scrivere codice simile al seguente:

```csharp
var handler = this.SomethingHappened;
if (handler != null)
    handler(this, eventArgs);
```

Si preferiva questo codice a una sintassi più semplice:

```csharp
// Not recommended
if (this.SomethingHappened != null)
    this.SomethingHappened(this, eventArgs);
```

> [!IMPORTANT]
> L'esempio precedente introduce una race condition. L'evento `SomethingHappened` può presentare dei sottoscrittori quando viene confrontato con `null` e tali sottoscrittori possono essere stati rimossi prima della generazione dell'evento. Questo può causare la generazione di <xref:System.NullReferenceException>.

In questa seconda versione il gestore dell'evento `SomethingHappened` potrebbe non essere Null durante il test, ma se un altro codice rimuove un gestore, potrebbe essere ancora Null quando viene chiamato il gestore dell'evento.

Il compilatore genera codice per l'operatore `?.` che garantisce che il lato sinistro (`this.SomethingHappened`) dell'espressione `?.` venga valutato una sola volta e che il risultato sia memorizzato nella cache:

```csharp
// preferred in C# 6:
this.SomethingHappened?.Invoke(this, eventArgs);
```

Verificare che il lato sinistro venga valutato una sola volta consente inoltre di usare qualsiasi espressione, comprese le chiamate ai metodi, sul lato sinistro di `?.` Anche se hanno effetti collaterali, i valori vengono valutati una volta, quindi gli effetti collaterali si verificano una sola volta. È possibile vedere un esempio nell'argomento relativo agli [eventi](../events-overview.md#language-support-for-events).

## <a name="string-interpolation"></a>Interpolazione di stringhe

C# 6 contiene una nuova sintassi per la composizione di stringhe da una stringa di formato e di espressioni che vengono valutate per produrre altri valori di stringa.

Di solito era necessario usare parametri posizionali in un metodo come `string.Format`:

[!code-csharp[stringFormat](../../../samples/snippets/csharp/new-in-6/oldcode.cs#stringFormat)]

Con C# 6 la nuova funzionalità di [interpolazione delle stringhe](../language-reference/tokens/interpolated.md) consente di incorporare le espressioni nella stringa di formato. Basta far precedere la stringa da `$`:

[!code-csharp[stringInterpolation](../../../samples/snippets/csharp/new-in-6/newcode.cs#FullNameExpressionMember)]

Questo esempio usa espressioni di proprietà per le espressioni sostituite. È possibile espandere questa sintassi per usare qualsiasi espressione. Ad esempio, è possibile calcolare la media dei voti di uno studente come parte dell'interpolazione:

[!code-csharp[stringInterpolationExpression](../../../samples/snippets/csharp/new-in-6/newcode.cs#stringInterpolationExpression)]

Eseguendo l'esempio precedente si può vedere che l'output per `Grades.Average()` potrebbe avere più posizioni decimali del necessario. La sintassi di interpolazione delle stringhe supporta tutte le stringhe di formato disponibili usando i metodi di formattazione precedenti. Aggiungere le stringhe di formato tra parentesi graffe. Aggiungere `:` dopo l'espressione da formattare:

[!code-csharp[stringInterpolationFormat](../../../samples/snippets/csharp/new-in-6/newcode.cs#stringInterpolationFormat)]

La riga di codice precedente formatta il valore per `Grades.Average()` come numero a virgola mobile con due cifre decimali.

Il carattere `:` viene sempre interpretato come separatore tra l'espressione da formattare e la stringa di formato. Questo può causare problemi quando l'espressione usa il carattere `:` in altro modo, ad esempio come operatore condizionale:

```csharp
public string GetGradePointPercentages() =>
    $"Name: {LastName}, {FirstName}. G.P.A: {Grades.Any() ? Grades.Average() : double.NaN:F2}";
```

Nell'esempio precedente il carattere `:` viene analizzato come inizio della stringa di formato, non come parte dell'operatore condizionale. In tutti i casi in cui ciò accade è possibile racchiudere l'espressione tra parentesi per indurre il compilatore a interpretare l'espressione come previsto:

[!code-csharp[stringInterpolationConditional](../../../samples/snippets/csharp/new-in-6/newcode.cs#stringInterpolationConditional)]

Non vi sono limitazioni per le espressioni che si possono inserire tra parentesi graffe. È possibile eseguire una query LINQ complessa all'interno di una stringa interpolata per effettuare calcoli e visualizzare il risultato:

[!code-csharp[stringInterpolationLinq](../../../samples/snippets/csharp/new-in-6/newcode.cs#stringInterpolationLinq)]

Da questo esempio risulta che è anche possibile annidare un'espressione di interpolazione di stringhe all'interno di un'altra espressione di interpolazione di stringhe. Questo esempio è probabilmente più complesso del necessario nel codice di produzione,
ma illustra in modo efficace la portata della funzionalità. Qualsiasi espressione C# può essere inserita tra parentesi graffe in una stringa interpolata.

### <a name="string-interpolation-and-specific-cultures"></a>Interpolazione delle stringhe e impostazioni cultura specifiche

Tutti gli esempi illustrati nella sezione precedente formattano le stringhe usando la lingua e le impostazioni cultura correnti del computer in cui viene eseguito il codice. Spesso può essere necessario formattare la stringa prodotta usando impostazioni cultura specifiche.
A tale scopo, sfruttare il fatto che l'oggetto prodotto da un'interpolazione di stringhe può essere convertito in modo implicito in <xref:System.FormattableString>.

L'istanza di <xref:System.FormattableString> contiene la stringa di formato e i risultati della valutazione delle espressioni prima della conversione di queste in stringhe. È possibile usare i metodi pubblici di <xref:System.FormattableString> per specificare le impostazioni cultura quando si formatta una stringa. L'esempio seguente, ad esempio, produce una stringa con impostazioni cultura tedesche. Usa il carattere ',' come separatore decimale e il carattere '.' come separatore delle migliaia.

```csharp
FormattableString str = $"Average grade is {s.Grades.Average()}";
var gradeStr = str.ToString(new System.Globalization.CultureInfo("de-DE"));
```

Per altre informazioni, vedere [Interpolazione di stringhe](../language-reference/tokens/interpolated.md).

## <a name="exception-filters"></a>Filtri eccezioni

Un'altra nuova funzionalità di C# 6 sono i *filtri eccezioni*. I filtri eccezioni sono clausole che determinano quando deve essere applicata una determinata clausola catch.
Se l'espressione usata per un filtro eccezioni restituisce `true`, la clausola catch esegue la normale elaborazione per un'eccezione. Se l'espressione restituisce `false`, la clausola `catch` viene ignorata.

Un utilizzo consiste nell'esaminare le informazioni relative a un'eccezione per determinare se una clausola `catch` può elaborare l'eccezione:

[!code-csharp[ExceptionFilter](../../../samples/snippets/csharp/new-in-6/NetworkClient.cs#ExceptionFilter)]

Il codice generato dai filtri eccezioni offre informazioni più complete su un'eccezione generata e non elaborata. Prima di aggiungere filtri eccezioni al linguaggio, è necessario creare un codice simile al seguente:

[!code-csharp[ExceptionFilterOld](../../../samples/snippets/csharp/new-in-6/NetworkClient.cs#ExceptionFilterOld)]

Il punto in cui viene generata l'eccezione cambia da un esempio all'altro.
Nel codice precedente, dove viene usata una clausola `throw`, qualsiasi analisi dello stack o esame dei dettagli di arresto anomalo del sistema indicherà che l'eccezione è stata generata dall'istruzione `throw` nella clausola catch. L'oggetto eccezione effettivo contiene lo stack di chiamate originale, ma tutte le altre informazioni sulle variabili dello stack di chiamate tra questo punto di generazione e la posizione del punto di generazione originale sono state perse. 

Se si confronta questa situazione con il modo in cui viene elaborato il codice che usa un filtro eccezioni, si vedrà che l'espressione del filtro eccezioni restituisce `false`. Di conseguenza, l'esecuzione non usa mai la clausola `catch`. Poiché la clausola `catch` non viene eseguita, non avviene alcuna rimozione dello stack. Ciò significa che il percorso di generazione originale viene mantenuto per tutte le attività di debug eseguite successivamente.

Ogni volta che è necessario valutare i campi o le proprietà di un'eccezione, anziché basarsi esclusivamente sul tipo di eccezione, usare un filtro eccezioni per conservare più informazioni di debug.

Un altro modello consigliato con i filtri eccezioni è l'uso dei filtri per la registrazione delle routine. In questo caso si sfrutta anche il modo in cui viene mantenuto il punto di generazione delle eccezioni quando un filtro eccezioni restituisce `false`.

Un metodo di registrazione sarebbe un metodo il cui argomento è l'eccezione che restituisce in modo non condizionale `false`:

[!code-csharp[ExceptionFilterLogging](../../../samples/snippets/csharp/new-in-6/ExceptionFilterHelpers.cs#ExceptionFilterLogging)]

Ogni volta che si vuole registrare un'eccezione, è possibile aggiungere una clausola catch e usare questo metodo come filtro eccezioni:

[!code-csharp[LogException](../../../samples/snippets/csharp/new-in-6/program.cs#LogException)]

Le eccezioni non vengono mai intercettate perché il metodo `LogException` restituisce sempre `false`. Il filtro eccezioni sempre false indica che è possibile inserire questo gestore di registrazione prima di eventuali altri gestori di eccezioni:

[!code-csharp[LogExceptionRecovery](../../../samples/snippets/csharp/new-in-6/program.cs#LogExceptionRecovery)]

Nell'esempio precedente viene evidenziato un aspetto molto importante dei filtri eccezioni.
I filtri eccezioni consentono scenari in cui una clausola catch delle eccezioni più generale può apparire prima di una clausola più specifica. È anche possibile visualizzare lo stesso tipo di eccezione in più clausole catch:

[!code-csharp[HandleNotChanged](../../../samples/snippets/csharp/new-in-6/NetworkClient.cs#HandleNotChanged)]

Un altro modello consigliato consente di impedire alle clausole catch di elaborare le eccezioni quando viene collegato un debugger. Questa tecnica consente di eseguire un'applicazione con il debugger e arrestare l'esecuzione quando viene generata un'eccezione.

Nel codice aggiungere un filtro eccezioni in modo tale che l'eventuale codice di ripristino venga eseguito solo quando non è collegato un debugger:

[!code-csharp[LogExceptionDebugger](../../../samples/snippets/csharp/new-in-6/program.cs#LogExceptionDebugger)]

Dopo aver aggiunto questo elemento al codice impostare il debugger in modo da interrompere tutte le eccezioni non gestite. Eseguire il programma nel debugger e il debugger si interrompe ogni volta che `PerformFailingOperation()` genera `RecoverableException`.
Il debugger interrompe il programma perché la clausola catch non verrà eseguita a causa del filtro eccezioni che restituisce false.

## <a name="nameof-expressions"></a>Espressioni `nameof`

L'espressione `nameof` restituisce il nome di un simbolo. È un sistema efficace per garantire il funzionamento degli strumenti ogni volta che è necessario il nome di una variabile, una proprietà o un campo membro.

Uno degli usi più comuni di `nameof` è specificare il nome di un simbolo che ha causato un'eccezione:

[!code-csharp[nameof](../../../samples/snippets/csharp/new-in-6/NewCode.cs#UsingStaticString)]

Un altro uso è con le applicazioni basate su XAML che implementano l'interfaccia `INotifyPropertyChanged`:

[!code-csharp[nameofNotify](../../../samples/snippets/csharp/new-in-6/viewmodel.cs#nameofNotify)]

Il vantaggio dell'uso dell'operatore `nameof` per una stringa costante è che gli strumenti sono in grado di interpretare il simbolo. Se si usano strumenti di refactoring per rinominare il simbolo, verrà rinominato nell'espressione `nameof`. Le stringhe costanti non offrono tale vantaggio. Provare a rinominare una variabile nell'editor preferito: tutte le espressioni `nameof` verranno a loro volta aggiornate.

L'espressione `nameof` produce il nome non qualificato del proprio argomento (`LastName` negli esempi precedenti) anche se si usa il nome completo dell'argomento:

[!code-csharp[QualifiedNameofNotify](../../../samples/snippets/csharp/new-in-6/viewmodel.cs#QualifiedNameofNotify)]

Questa espressione `nameof` produce `FirstName`, non `UXComponents.ViewModel.FirstName`.

## <a name="await-in-catch-and-finally-blocks"></a>Await nei blocchi catch e finally

C# 5 presentava diverse limitazioni riguardo al punto in cui posizionare le espressioni `await`.
Una di esse è stata rimossa in C# 6. È ora possibile usare `await` nelle espressioni `catch` o `finally`. 

Può sembrare che l'aggiunta di espressioni await nei blocchi catch e finally complichi il modo in cui i blocchi vengono elaborati. Vediamo un esempio per chiarire questo aspetto. In qualsiasi metodo asincrono è possibile usare un'espressione await in una clausola finally.

Con C# 6 è anche possibile usare await nelle espressioni catch. Questo uso è più frequente negli scenari di registrazione:

[!code-csharp[AwaitFinally](../../../samples/snippets/csharp/new-in-6/NetworkClient.cs#AwaitFinally)]

I dettagli sull'implementazione per l'aggiunta del supporto `await` all'interno delle clausole `catch` e `finally` assicura che il comportamento sia coerente con il comportamento per il codice sincrono. Quando il codice eseguito in una clausola `catch` o `finally` genera un elemento, l'esecuzione cerca una clausola `catch` appropriata nel successivo blocco circostante. Se si è verificata un'eccezione, tale eccezione viene persa. Lo stesso accade con le espressioni attese nelle clausole `catch` e `finally`: viene cercato un valore `catch` appropriato e l'eccezione corrente, se presente, viene persa.  

> [!NOTE]
> Questo comportamento è il motivo per cui è consigliabile scrivere le clausole `catch` e `finally` con attenzione, per evitare l'introduzione di nuove eccezioni.

## <a name="index-initializers"></a>Inizializzatori di indice.

Gli *inizializzatori di indice* sono una delle due funzionalità che rendono gli inizializzatori di insieme più coerenti con l'uso degli indici. Nelle versioni precedenti di C# gli *inizializzatori di insieme* potevano essere usati solo con le raccolte di stili di sequenza, includendo <xref:System.Collections.Generic.Dictionary%602> mediante l'aggiunta di coppie chiave/valore racchiuse tra parentesi graffe:

[!code-csharp[ListInitializer](../../../samples/snippets/csharp/new-in-6/initializers.cs#ListInitializer)]

Ora è possibile usarli con le raccolte <xref:System.Collections.Generic.Dictionary%602> e tipi simili. La nuova sintassi supporta l'assegnazione mediante l'uso di un indice nella raccolta:

[!code-csharp[DictionaryInitializer](../../../samples/snippets/csharp/new-in-6/initializers.cs#DictionaryInitializer)]

Questa funzionalità significa che i contenitori associativi possono essere inizializzati usando una sintassi simile a ciò che è stato usato per i contenitori sequenziali in diverse versioni.

## <a name="extension-add-methods-in-collection-initializers"></a>Metodi di estensione `Add` negli inizializzatori di insieme

Un'altra funzionalità che semplifica l'inizializzazione della raccolta è la possibilità di usare un *metodo di estensione* per il metodo `Add`. Questa funzionalità è stata aggiunta per la parità con Visual Basic. 

La funzionalità è particolarmente utile quando si usa una classe di raccolta personalizzata con un metodo di nome diverso per aggiungere semanticamente nuovi elementi.

Si consideri ad esempio una raccolta di studenti come questa:

[!code-csharp[Enrollment](../../../samples/snippets/csharp/new-in-6/enrollment.cs#Enrollment)]

Il metodo `Enroll` aggiunge uno studente. Ma non è conforme al modello `Add`.
Nelle versioni precedenti di C# non era possibile usare gli inizializzatori di insieme con un oggetto `Enrollment`:

[!code-csharp[InitializeEnrollment](../../../samples/snippets/csharp/new-in-6/classList.cs#InitializeEnrollment)]

Ora è possibile, ma solo se si crea un metodo di estensione che esegue il mapping di `Add` a `Enroll`:

[!code-csharp[ExtensionAdd](../../../samples/snippets/csharp/new-in-6/classList.cs#ExtensionAdd)]

L'uso di questa funzionalità consente di eseguire il mapping di qualsiasi metodo che aggiunge elementi a una raccolta a un metodo denominato `Add` creando un metodo di estensione.

## <a name="improved-overload-resolution"></a>Risoluzione dell'overload migliorata

Quest'ultima funzionalità probabilmente non viene notata. Esistevano costrutti in cui la versione precedente del compilatore C# poteva rilevare alcune chiamate al metodo che includevano espressioni lambda ambigue. Si consideri il metodo seguente:

[!code-csharp[AsyncMethod](../../../samples/snippets/csharp/new-in-6/overloads.cs#AsyncMethod)]

Nelle versioni precedenti di C# una chiamata a tale metodo usando la sintassi del gruppo di metodi avrebbe esito negativo:

[!code-csharp[MethodGroup](../../../samples/snippets/csharp/new-in-6/overloads.cs#MethodGroup)]
 
Il compilatore precedente non era in grado di distinguere correttamente `Task.Run(Action)` da `Task.Run(Func<Task>())`. Nelle versioni precedenti è necessario usare un'espressione lambda come argomento:

[!code-csharp[Lambda](../../../samples/snippets/csharp/new-in-6/overloads.cs#Lambda)]

Il compilatore C# 6 determina correttamente che `Task.Run(Func<Task>())` è una scelta migliore.
