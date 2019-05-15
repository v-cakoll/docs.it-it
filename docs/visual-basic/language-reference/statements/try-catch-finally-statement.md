---
title: Try... Catch... Istruzione finally - Visual Basic
description: Informazioni su come usare Gestione delle eccezioni con le istruzioni di Visual Basic Try/Catch/Finally.
ms.date: 12/07/2018
f1_keywords:
- vb.Try...Catch...Finally
- vb.when
- vb.Finally
- vb.Catch
- vb.Try
helpviewer_keywords:
- Try...Catch...Finally statements
- Try statement [Visual Basic]
- try-catch exception handling, Try...Catch...Finally statements
- error handling, while running code
- Try statement [Visual Basic], Try...Catch...Finally
- Finally keyword [Visual Basic], Try...Catch...Finally
- Catch statement [Visual Basic]
- When keyword [Visual Basic]
- Visual Basic code, handling errors while running
- structured exception handling, Try...Catch...Finally statements
ms.assetid: d6488026-ccb3-42b8-a810-0d97b9d6472b
ms.custom: seodec18
ms.openlocfilehash: 126f20c86bb47e8002382e069ce6236600394aba
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "65638777"
---
# <a name="trycatchfinally-statement-visual-basic"></a>Istruzione Try...Catch...Finally (Visual Basic)

Fornisce un modo per gestire alcuni o tutti i possibili errori che possono verificarsi in un determinato blocco di codice, codice in esecuzione.

## <a name="syntax"></a>Sintassi

```vb
Try
    [ tryStatements ]
    [ Exit Try ]
[ Catch [ exception [ As type ] ] [ When expression ]
    [ catchStatements ]
    [ Exit Try ] ]
[ Catch ... ]
[ Finally
    [ finallyStatements ] ]
End Try
```

## <a name="parts"></a>Parti

|Termine|Definizione|
|---|---|
|`tryStatements`|Facoltativo. Una o più istruzioni in cui può verificarsi un errore. Può essere un'istruzione composta.|
|`Catch`|Facoltativo. Più `Catch` blocchi consentiti. Se si verifica un'eccezione durante l'elaborazione di `Try` blocchi, ognuno `Catch` istruzione viene esaminata in ordine testuale per determinare se l'eccezione, viene gestita con `exception` che rappresenta l'eccezione che è stata generata.|
|`exception`|Facoltativo. Qualsiasi nome di variabile. Il valore iniziale di `exception` corrisponde al valore dell'errore generato. Utilizzato con `Catch` per specificare l'errore intercettato. Se omesso, il `Catch` istruzione genera un'eccezione.|
|`type`|Facoltativo. Specifica il tipo di filtro di classe. Se il valore di `exception` è di tipo specificato dal `type` o di un tipo derivato, l'identificatore viene associato all'oggetto eccezione.|
|`When`|Facoltativo. Oggetto `Catch` istruzione con un `When` clausola rileva le eccezioni solo quando `expression` restituisce `True`. Oggetto `When` clausola viene applicata solo dopo aver verificato il tipo dell'eccezione, e `expression` può fare riferimento a un identificatore che rappresenta l'eccezione.|
|`expression`|Facoltativo. Deve essere convertibile in modo implicito in `Boolean`. Qualsiasi espressione che descrive un filtro di generico. In genere utilizzato per filtrare in base al numero di errore. Utilizzato con `When` parola chiave per specificare le circostanze in cui viene intercettato l'errore.|
|`catchStatements`|Facoltativo. Una o più istruzioni per la gestione degli errori che si verificano in associato `Try` blocco. Può essere un'istruzione composta.|
|`Exit Try`|Facoltativo. Parola chiave che viene interrotta la `Try...Catch...Finally` struttura. Con il codice subito dopo l'esecuzione riprende il `End Try` istruzione. Il `Finally` verrà eseguita l'istruzione. Non è consentito in `Finally` blocchi.|
|`Finally`|Facoltativo. Oggetto `Finally` blocco viene eseguito quando l'esecuzione esce da qualsiasi parte del `Try...Catch` istruzione.|
|`finallyStatements`|Facoltativo. Una o più istruzioni che vengono eseguite dopo che tutte le altre elaborazioni di errore si sono verificato.|
|`End Try`|Termina il `Try...Catch...Finally` struttura.|

## <a name="remarks"></a>Note

Se si prevede che una particolare eccezione potrebbe verificarsi durante una particolare sezione di codice, inserire il codice in un `Try` bloccare e usare un `Catch` blocco per mantenere il controllo e gestire l'eccezione, se si verifica.

Oggetto `Try…Catch` istruzione costituita da un `Try` blocco seguito da uno o più `Catch` clausole, che specificano i gestori per eccezioni diverse. Quando viene generata un'eccezione un `Try` bloccare, Visual Basic cerca il `Catch` istruzione che gestisce l'eccezione. Se un oggetto corrispondente `Catch` istruzione non viene trovata, Visual Basic viene esaminato il metodo che ha chiamato il metodo corrente, e così via fino allo stack di chiamate. Se nessun `Catch` blocco viene trovato, viene visualizzato un messaggio di eccezione non gestita all'utente di Visual Basic e interrompe l'esecuzione del programma.

È possibile usare più di uno `Catch` istruzione in un `Try…Catch` istruzione. In tal caso, l'ordine dei `Catch` clausole è significativo poiché vengono esaminate nell'ordine. Intercettare le eccezioni più specifiche prima di quelle meno specifiche.

Quanto segue `Catch` sono quelle meno specifiche condizioni dell'istruzione e rileverà tutte le eccezioni che derivano dal <xref:System.Exception> classe. È in genere deve usare una di queste variazioni come l'ultimo `Catch` blocco il `Try...Catch...Finally` struttura, dopo l'intercettazione si prevede che tutte le eccezioni specifiche. Flusso di controllo non può raggiungere mai una `Catch` blocco che segue una di queste variazioni.

- Il `type` è `Exception`, ad esempio: `Catch ex As Exception`

- L'istruzione non ha alcun `exception` variabile, ad esempio: `Catch`

Quando un `Try…Catch…Finally` istruzione è annidata in un'altra `Try` innanzitutto esaminato ogni blocco di Visual Basic `Catch` istruzione in più interna `Try` blocco. Se non corrisponde ad alcuna `Catch` istruzione viene trovata, la ricerca procede per il `Catch` rapporti di esterna `Try…Catch…Finally` blocco.

Le variabili locali da un `Try` blocchi non sono disponibili in un `Catch` bloccarsi, in quanto sono blocchi separati. Se si desidera utilizzare una variabile in più di un blocco, dichiarare la variabile all'esterno di `Try...Catch...Finally` struttura.

> [!TIP]
> Il `Try…Catch…Finally` informativa è disponibile come frammento di codice IntelliSense. In Gestione frammenti di codice, espandere **modelli di codice - se, For Each, Try Catch, proprietà, e così via**e quindi **Error Handling (eccezioni)**. Per altre informazioni, vedere [Code Snippets](/visualstudio/ide/code-snippets) (Frammenti di codice).

## <a name="finally-block"></a>Blocco finally

Se si dispone di uno o più istruzioni da eseguano prima di uscire il `Try` struttura, utilizzare un `Finally` blocco. Il controllo passa al `Finally` bloccare solo prima di passare fuori il `Try…Catch` struttura. Questo vale anche se si verifica un'eccezione in un punto qualsiasi all'interno di `Try` struttura.

Oggetto `Finally` blocco è utile per eseguire qualsiasi codice che deve eseguire anche se si verifica un'eccezione. Il controllo viene passato per il `Finally` indipendentemente dal modo in cui il blocco `Try...Catch` uscita dal blocco.

Il codice in un `Finally` bloccare l'esecuzione anche se il codice rileva una `Return` istruzione in un `Try` o `Catch` blocco. Controllo non viene passato da un `Try` oppure `Catch` block ai corrispondenti `Finally` bloccare nei casi seguenti:

- Un' [istruzione End](end-statement.md) viene rilevata nel `Try` o `Catch` blocco.

- Oggetto <xref:System.StackOverflowException> viene generata nel `Try` o `Catch` blocco.

Non è valido per trasferire in modo esplicito l'esecuzione in un `Finally` blocco. Trasferire l'esecuzione di un `Finally` blocco non è valido, ad eccezione di un'eccezione.

Se un `Try` istruzione non contiene almeno uno `Catch` blocco, deve contenere un `Finally` blocco.

> [!TIP]
> Se non è necessario intercettare eccezioni specifiche, il `Using` istruzione si comporta come un `Try…Finally` blocco e garantisce l'eliminazione delle risorse, indipendentemente dal modo in cui si esce dal blocco. Ciò è vero anche con un'eccezione non gestita. Per altre informazioni, vedere [Istruzione using](using-statement.md).

## <a name="exception-argument"></a>Argomento di eccezione

Il `Catch` block `exception` argomento è un'istanza del <xref:System.Exception> classe o una classe che deriva dal `Exception` classe. Il `Exception` istanza della classe corrispondente all'errore di cui si è verificata la `Try` blocco.

Le proprietà del `Exception` oggetto della Guida per identificare la causa e la posizione di un'eccezione. Ad esempio, il <xref:System.Exception.StackTrace%2A> proprietà sono elencati i metodi di chiamata che ha causato l'eccezione, consentendo di individuare dove si è verificato l'errore nel codice. <xref:System.Exception.Message%2A> Restituisce un messaggio che descrive l'eccezione. <xref:System.Exception.HelpLink%2A> Restituisce un collegamento a un file della Guida associato. <xref:System.Exception.InnerException%2A> Restituisce il `Exception` oggetto che ha causato l'eccezione corrente oppure restituisce `Nothing` se è presente alcun originale `Exception`.

## <a name="considerations-when-using-a-trycatch-statement"></a>Considerazioni sull'uso di un blocco Try... Istruzione catch

Usare un `Try…Catch` istruzione solo per segnalare la presenza di eventi imprevisti o insoliti oppure elementi di programma. Le ragioni seguenti:

- Rilevamento delle eccezioni in fase di esecuzione comporta un sovraccarico aggiuntivo e problema essere più lento rispetto alla verifica preliminare per evitare eccezioni.

- Se un `Catch` blocco non viene gestito correttamente, l'eccezione potrebbe non essere segnalato in modo corretto per gli utenti.

- La gestione delle eccezioni esegue un programma più complesse.

Non è sempre necessario un `Try…Catch` istruzione per verificare la presenza di una condizione che è probabile che si verifichino. L'esempio seguente controlla se esiste un file prima di tentare di aprirlo. Ciò riduce la necessità di rilevare un'eccezione generata dal <xref:System.IO.File.OpenText%2A> (metodo).

[!code-vb[VbVbalrStatements#94](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#94)]

Assicurarsi che il codice `Catch` blocchi possono segnalare correttamente le eccezioni per gli utenti, tramite la registrazione di thread-safe o i messaggi appropriati. In caso contrario, le eccezioni potrebbero rimanere sconosciute.

## <a name="async-methods"></a>Metodi asincroni

Se si contrassegna un metodo con il [Async](../modifiers/async.md) modificatore, è possibile utilizzare il [Await](../operators/await-operator.md) operatore nel metodo. Un'istruzione con il `Await` operatore sospende l'esecuzione del metodo fino al completamento dell'attività attesa. L'attività rappresenta il lavoro attualmente in fase di esecuzione. Quando l'attività che è associato il `Await` operatore viene completata, l'esecuzione riprende nello stesso metodo. Per altre informazioni, vedere [flusso di controllo in programmi asincroni](../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md).

Un'attività restituita da un metodo asincrono può terminare con uno stato di errore, che indica che è stata completata a causa di un'eccezione non gestita. Un'attività potrebbe anche terminare in uno stato annullato, con conseguente un `OperationCanceledException` generata dall'espressione await. Per entrambi i tipi di eccezione, inserire il `Await` espressione associata con l'attività in un `Try` block e intercettare l'eccezione nel `Catch` blocco. Viene fornito un esempio più avanti in questo argomento.

Un'attività può essere in uno stato di errore perché più eccezioni sono stati responsabili per relativi eventi di errore. Ad esempio, l'attività può essere il risultato di una chiamata a <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType>. Quando si attende tale attività, l'eccezione rilevata è solo una delle eccezioni e non è possibile prevedere quale eccezione verrà rilevata. Viene fornito un esempio più avanti in questo argomento.

Un' `Await` espressione non può essere all'interno di un `Catch` blocco o `Finally` blocco.

## <a name="iterators"></a>Iterators

Una funzione iteratore o `Get` della funzione di accesso esegue un'iterazione personalizzata su una raccolta. Un iteratore Usa un' [Yield](yield-statement.md) istruzione per restituire ogni elemento della raccolta uno alla volta. Si chiama una funzione iteratore utilizzando un [For Each... Istruzione Next](for-each-next-statement.md).

Oggetto `Yield` istruzione può essere contenuta in un `Try` blocco. Oggetto `Try` blocco che contiene un `Yield` istruzione può avere `Catch` blocca e può avere un `Finally` blocco. Vedere la sezione "provare a blocchi in Visual Basic" [iteratori](../../programming-guide/concepts/iterators.md) per un esempio.

Oggetto `Yield` istruzione non può essere all'interno di un `Catch` blocco o un `Finally` blocco.

Se il `For Each` corpo (all'esterno della funzione iteratore) genera un'eccezione, una `Catch` blocco nella funzione iteratore non viene eseguita, ma un `Finally` try nella funzione iteratore. Oggetto `Catch` blocco all'interno di una funzione iteratore intercetta solo le eccezioni che si verificano all'interno della funzione iteratore.

## <a name="partial-trust-situations"></a>Situazioni di attendibilità parziale

In situazioni di attendibilità parziale, ad esempio un'applicazione ospitata in una condivisione di rete, `Try...Catch...Finally` non intercetta le eccezioni di sicurezza che si verificano prima che venga richiamato il metodo che contiene la chiamata. L'esempio seguente, quando è inserito in una condivisione server ed eseguire da qui, produce l'errore "SecurityException: Richiesta non riuscita." Per altre informazioni sulle eccezioni di sicurezza, vedere il <xref:System.Security.SecurityException> classe.

[!code-vb[VbVbalrStatements#85](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#85)]

In una situazione di attendibilità parziale di questo tipo, è necessario inserire il `Process.Start` istruzione in un oggetto separato `Sub`. La chiamata iniziale al `Sub` avrà esito negativo. In questo modo `Try...Catch` generarla prima il `Sub` che contiene `Process.Start` viene avviato e ha generato l'eccezione di sicurezza.

## <a name="examples"></a>Esempi

### <a name="the-structure-of-trycatchfinally"></a>La struttura del blocco Try... Catch... Infine

Nell'esempio seguente viene illustrata la struttura del `Try...Catch...Finally` istruzione.

[!code-vb[VbVbalrStatements#86](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#86)]  

### <a name="exception-in-a-method-called-from-a-try-block"></a>Eccezione in un metodo chiamato da un blocco Try

Nell'esempio seguente, il `CreateException` metodo genera un `NullReferenceException`. Il codice che genera l'eccezione non si trova in un `Try` blocco. Pertanto, il `CreateException` (metodo) non gestisce l'eccezione. Il `RunSample` metodo gestisce l'eccezione, perché la chiamata ai `CreateException` metodo si trova in un `Try` blocco.

L'esempio include `Catch` istruzioni per diversi tipi di eccezioni, ordinate dalla più specifica alla più generale.

[!code-vb[VbVbalrStatements#91](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#91)]

### <a name="the-catch-when-statement"></a>L'istruzione Catch quando

Nell'esempio seguente viene illustrato come utilizzare un `Catch When` istruzione per filtrare in base a un'espressione condizionale. Se l'espressione condizionale restituisce `True`, il codice di `Catch` bloccare l'esecuzione.

[!code-vb[VbVbalrStatements#92](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#92)]

### <a name="nested-try-statements"></a>Istruzioni Try annidate

L'esempio seguente contiene un `Try…Catch` istruzione contenuta in un `Try` blocco. Interna `Catch` blocco genera un'eccezione che ha il `InnerException` proprietà impostata sull'eccezione originale. L'outer `Catch` blocco segnala la propria eccezione e l'eccezione interna.

[!code-vb[VbVbalrStatements#93](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#93)]

### <a name="exception-handling-for-async-methods"></a>Gestione delle eccezioni per i metodi asincroni

L'esempio seguente illustra la gestione delle eccezioni per i metodi asincroni. Per rilevare un'eccezione che si applica a un'attività asincrona, il `Await` l'espressione ha un `Try` blocco di chiamante e l'eccezione viene intercettata nel `Catch` blocco.

Rimuovere il commento dalla riga `Throw New Exception` nell'esempio per illustrare la gestione delle eccezioni. L'eccezione viene intercettata nel `Catch` blocca, l'attività `IsFaulted` è impostata su `True`e l'attività `Exception.InnerException` viene impostata per l'eccezione.

Rimuovere il commento dalla riga `Throw New OperationCancelledException` per illustrare cosa accade quando si annulla un processo asincrono. L'eccezione viene intercettata nel `Catch` blocco e l'attività `IsCanceled` è impostata su `True`. Tuttavia, in alcune condizioni che non si applicano a questo esempio, `IsFaulted` è impostata su `True` e `IsCanceled` è impostata su `False`.

[!code-vb[csAsyncExceptions#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/csasyncexceptions/vb/class1.vb#1)]

### <a name="handling-multiple-exceptions-in-async-methods"></a>Gestione delle eccezioni più nei metodi asincroni

Il seguente esempio illustra la gestione delle eccezioni dove più attività possono restituire più eccezioni. Il `Try` blocco ha la `Await` espressione per l'attività che <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> restituito. L'attività viene completata quando le tre attività a cui <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> viene applicata sono state completate.

Ognuna delle tre attività genera un'eccezione. Il `Catch` blocco scorre le eccezioni che si trovano nella `Exception.InnerExceptions` proprietà dell'attività che `Task.WhenAll` restituito.

[!code-vb[csAsyncExceptions#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/csasyncexceptions/vb/class1.vb#3)]

## <a name="see-also"></a>Vedere anche

- <xref:Microsoft.VisualBasic.Information.Err%2A>
- <xref:System.Exception>
- [Istruzione Exit](exit-statement.md)
- [Istruzione On Error](on-error-statement.md)
- [Procedure consigliate per l'uso dei frammenti di codice](/visualstudio/ide/best-practices-for-using-code-snippets)
- [Gestione delle eccezioni](../../../standard/parallel-programming/exception-handling-task-parallel-library.md)
- [Istruzione Throw](throw-statement.md)
