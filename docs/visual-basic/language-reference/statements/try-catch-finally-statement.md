---
title: Prova... Rileva... Finally (istruzione)
description: Informazioni su come usare la gestione delle eccezioni con Visual Basic istruzioni try/catch/finally.
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
ms.openlocfilehash: 22f1611786a3da512632b5b547b7ef141c8f65c6
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84391768"
---
# <a name="trycatchfinally-statement-visual-basic"></a>Istruzione Try...Catch...Finally (Visual Basic)

Consente di gestire alcuni o tutti i possibili errori che possono verificarsi in un blocco di codice specifico, mentre è ancora in esecuzione il codice.

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
|`tryStatements`|Facoltativa. Istruzioni in cui può verificarsi un errore. Può essere un'istruzione composta.|
|`Catch`|Facoltativa. Sono `Catch` consentiti più blocchi. Se si verifica un'eccezione durante l'elaborazione del `Try` blocco, ogni `Catch` istruzione viene esaminata in ordine testuale per determinare se gestisce l'eccezione, con `exception` la rappresentazione dell'eccezione generata.|
|`exception`|Facoltativa. Qualsiasi nome di variabile. Il valore iniziale di `exception` corrisponde al valore dell'errore generato. Utilizzato con `Catch` per specificare l'errore rilevato. Se omesso, l' `Catch` istruzione rileva qualsiasi eccezione.|
|`type`|Facoltativa. Specifica il tipo di filtro di classe. Se il valore di `exception` è del tipo specificato da `type` o di un tipo derivato, l'identificatore viene associato all'oggetto Exception.|
|`When`|Facoltativa. Un' `Catch` istruzione con una `When` clausola intercetta le eccezioni solo quando `expression` restituisce `True` . Una `When` clausola viene applicata solo dopo avere verificato il tipo di eccezione e `expression` può fare riferimento all'identificatore che rappresenta l'eccezione.|
|`expression`|Facoltativa. Deve essere convertibile in modo implicito in `Boolean` . Qualsiasi espressione che descrive un filtro generico. Usato in genere per filtrare in base al numero di errore. Usato con `When` la parola chiave per specificare le circostanze in cui viene rilevato l'errore.|
|`catchStatements`|Facoltativa. Istruzioni per gestire gli errori che si verificano nel blocco associato `Try` . Può essere un'istruzione composta.|
|`Exit Try`|Facoltativa. Parola chiave che si interrompe dalla `Try...Catch...Finally` struttura. L'esecuzione riprende con il codice immediatamente successivo all' `End Try` istruzione. L' `Finally` istruzione verrà comunque eseguita. Non consentito nei `Finally` blocchi.|
|`Finally`|Facoltativa. Un `Finally` blocco viene sempre eseguito quando l'esecuzione lascia una parte dell' `Try...Catch` istruzione.|
|`finallyStatements`|Facoltativa. Istruzioni che vengono eseguite dopo l'elaborazione di tutti gli altri errori.|
|`End Try`|Termina la `Try...Catch...Finally` struttura.|

## <a name="remarks"></a>Commenti

Se si prevede che una particolare eccezione possa verificarsi durante una particolare sezione di codice, inserire il codice in un `Try` blocco e usare un `Catch` blocco per mantenere il controllo e gestire l'eccezione, se si verifica.

Un' `Try…Catch` istruzione è costituita `Try` da un blocco seguito da una o più `Catch` clausole, che specificano i gestori per varie eccezioni. Quando viene generata un'eccezione in un `Try` blocco, Visual Basic cerca l' `Catch` istruzione che gestisce l'eccezione. Se `Catch` non viene trovata alcuna istruzione corrispondente, Visual Basic esamina il metodo che ha chiamato il metodo corrente e così via fino allo stack di chiamate. Se non `Catch` viene trovato alcun blocco, Visual Basic Visualizza un messaggio di eccezione non gestita per l'utente e interrompe l'esecuzione del programma.

In un'istruzione è possibile utilizzare più di un' `Catch` istruzione `Try…Catch` . In tal caso, l'ordine delle `Catch` clausole è significativo perché vengono esaminate in ordine. Intercettare le eccezioni più specifiche prima di quelle meno specifiche.

Le `Catch` condizioni dell'istruzione seguenti sono le meno specifiche e intercettano tutte le eccezioni che derivano dalla <xref:System.Exception> classe. In genere, è consigliabile usare una di queste varianti come ultimo `Catch` blocco nella `Try...Catch...Finally` struttura, dopo avere intercettato tutte le eccezioni specifiche previste. Il flusso di controllo non può mai raggiungere un `Catch` blocco che segue una di queste varianti.

- `type`È `Exception` , ad esempio:`Catch ex As Exception`

- L'istruzione non ha alcuna `exception` variabile, ad esempio:`Catch`

Quando un' `Try…Catch…Finally` istruzione è annidata in un altro `Try` blocco, Visual Basic esamina prima ogni `Catch` istruzione nel blocco più interno `Try` . Se non `Catch` viene trovata alcuna istruzione corrispondente, la ricerca procede alle `Catch` istruzioni del `Try…Catch…Finally` blocco esterno.

Le variabili locali di un `Try` blocco non sono disponibili in un `Catch` blocco perché sono blocchi separati. Se si desidera utilizzare una variabile in più di un blocco, dichiarare la variabile all'esterno della `Try...Catch...Finally` struttura.

> [!TIP]
> L' `Try…Catch…Finally` istruzione è disponibile come frammento di codice IntelliSense. In Gestione frammenti di codice espandere modelli di **codice-if, for each, try catch, Property e così via**, quindi **gestione degli errori (eccezioni)**. Per altre informazioni, vedere [Code Snippets](/visualstudio/ide/code-snippets) (Frammenti di codice).

## <a name="finally-block"></a>Blocco finally

Se si dispone di una o più istruzioni che devono essere eseguite prima di uscire dalla `Try` struttura, utilizzare un `Finally` blocco. Il controllo passa al `Finally` blocco immediatamente prima che venga passato all'esterno della `Try…Catch` struttura. Questo vale anche se si verifica un'eccezione in qualsiasi punto all'interno della `Try` struttura.

Un `Finally` blocco è utile per l'esecuzione di codice che deve essere eseguito anche se si verifica un'eccezione. Il controllo viene passato al `Finally` blocco indipendentemente dal modo in cui il `Try...Catch` blocco viene chiuso.

Il codice in un `Finally` blocco viene eseguito anche se il codice rileva un' `Return` istruzione in un `Try` blocco o `Catch` . Il controllo non passa da un `Try` `Catch` blocco o al blocco corrispondente `Finally` nei casi seguenti:

- Nel blocco o viene rilevata un' [istruzione End](end-statement.md) `Try` `Catch` .

- <xref:System.StackOverflowException>Viene generata un'eccezione nel `Try` `Catch` blocco o.

Non è possibile trasferire in modo esplicito l'esecuzione in un `Finally` blocco. Il trasferimento dell'esecuzione da un `Finally` blocco non è valido, ad eccezione di un'eccezione.

Se un' `Try` istruzione non contiene almeno un `Catch` blocco, deve contenere un `Finally` blocco.

> [!TIP]
> Se non è necessario intercettare eccezioni specifiche, l' `Using` istruzione si comporta come un `Try…Finally` blocco e garantisce l'eliminazione delle risorse, indipendentemente dalla modalità di uscita dal blocco. Questo vale anche con un'eccezione non gestita. Per ulteriori informazioni, vedere [istruzione using](using-statement.md).

## <a name="exception-argument"></a>Argomento Exception

L' `Catch` `exception` argomento Block è un'istanza della <xref:System.Exception> classe o una classe che deriva dalla `Exception` classe. L' `Exception` istanza della classe corrisponde all'errore che si è verificato nel `Try` blocco.

Le proprietà dell' `Exception` oggetto consentono di identificare la ragione e la posizione di un'eccezione. Ad esempio, la <xref:System.Exception.StackTrace%2A> proprietà elenca i metodi chiamati che hanno generato l'eccezione, consentendo di individuare la posizione in cui si è verificato l'errore nel codice. <xref:System.Exception.Message%2A>Restituisce un messaggio che descrive l'eccezione. <xref:System.Exception.HelpLink%2A>Restituisce un collegamento a un file della Guida associato. <xref:System.Exception.InnerException%2A>Restituisce l' `Exception` oggetto che ha causato l'eccezione corrente oppure restituisce `Nothing` se non è presente alcun oggetto originale `Exception` .

## <a name="considerations-when-using-a-trycatch-statement"></a>Considerazioni sull'utilizzo di un try... Istruzione catch

Utilizzare un' `Try…Catch` istruzione solo per segnalare l'occorrenza di eventi di programma insoliti o imprevisti. Di seguito sono riportati alcuni motivi:

- Il rilevamento delle eccezioni in fase di esecuzione comporta un sovraccarico aggiuntivo ed è probabilmente più lento rispetto al controllo preliminare per evitare eccezioni.

- Se un `Catch` blocco non viene gestito correttamente, l'eccezione potrebbe non essere segnalata correttamente agli utenti.

- La gestione delle eccezioni rende un programma più complesso.

Non è sempre necessaria un' `Try…Catch` istruzione per verificare la presenza di una condizione che potrebbe verificarsi. Nell'esempio seguente viene verificata l'esistenza di un file prima di tentare di aprirlo. In questo modo si riduce la necessità di intercettare un'eccezione generata dal <xref:System.IO.File.OpenText%2A> metodo.

[!code-vb[VbVbalrStatements#94](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#94)]

Verificare che il codice in `Catch` blocchi possa segnalare correttamente le eccezioni agli utenti, sia tramite la registrazione thread-safe che i messaggi appropriati. In caso contrario, le eccezioni potrebbero rimanere sconosciute.

## <a name="async-methods"></a>Metodi asincroni

Se si contrassegna un metodo con il modificatore [Async](../modifiers/async.md) , è possibile usare l'operatore [await](../operators/await-operator.md) nel metodo. Un'istruzione con l' `Await` operatore sospende l'esecuzione del metodo fino al completamento dell'attività attesa. L'attività rappresenta il lavoro attualmente in fase di esecuzione. Quando l'attività associata all' `Await` operatore termina, l'esecuzione riprende nello stesso metodo. Per altre informazioni, vedere [flusso di controllo in programmi asincroni](../../programming-guide/concepts/async/control-flow-in-async-programs.md).

Un'attività restituita da un metodo asincrono può terminare con uno stato di errore, a indicare che è stata completata a causa di un'eccezione non gestita. Un'attività può inoltre terminare con uno stato annullato, il che comporta la generazione `OperationCanceledException` di un'eccezione dall'espressione await. Per intercettare entrambi i tipi di eccezione, inserire l' `Await` espressione associata all'attività in un `Try` blocco e intercettare l'eccezione nel `Catch` blocco. Un esempio è disponibile più avanti in questo argomento.

Un'attività può essere in uno stato di errore perché più eccezioni erano responsabili dell'errore. Ad esempio, l'attività può essere il risultato di una chiamata a <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType>. Quando si attende tale attività, l'eccezione rilevata è solo una delle eccezioni e non è possibile prevedere quale eccezione verrà rilevata. Un esempio è disponibile più avanti in questo argomento.

Un' `Await` espressione non può trovarsi all'interno di un `Catch` blocco o di un `Finally` blocco.

## <a name="iterators"></a>Iterators

Una funzione o una funzione di accesso iteratore `Get` esegue un'iterazione personalizzata su una raccolta. Un iteratore usa un'istruzione [yield](yield-statement.md) per restituire ogni elemento della raccolta uno alla volta. Si chiama una funzione iteratore usando un [per ogni... Istruzione successiva](for-each-next-statement.md).

Un' `Yield` istruzione può trovarsi all'interno di un `Try` blocco. Un `Try` blocco che contiene un' `Yield` istruzione può contenere `Catch` blocchi e può avere un `Finally` blocco. Per un esempio, vedere la sezione "blocchi try in Visual Basic" degli [iteratori](../../programming-guide/concepts/iterators.md) .

Un' `Yield` istruzione non può trovarsi all'interno di un `Catch` blocco o di un `Finally` blocco.

Se il `For Each` corpo (all'esterno della funzione iteratore) genera un'eccezione, un `Catch` blocco nella funzione iteratore non viene eseguito, ma `Finally` viene eseguito un blocco nella funzione iteratore. Un `Catch` blocco all'interno di una funzione iteratore intercetta solo le eccezioni che si verificano all'interno della funzione iteratore.

## <a name="partial-trust-situations"></a>Situazioni di attendibilità parziale

In situazioni di attendibilità parziale, ad esempio un'applicazione ospitata in una condivisione di rete, non `Try...Catch...Finally` rileva le eccezioni di sicurezza che si verificano prima che venga richiamato il metodo che contiene la chiamata. Nell'esempio seguente, quando lo si inserisce in una condivisione server e si esegue da questa posizione, viene generato l'errore "System. Security. SecurityException: request failed". Per ulteriori informazioni sulle eccezioni di sicurezza, vedere la <xref:System.Security.SecurityException> classe.

[!code-vb[VbVbalrStatements#85](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#85)]

In una situazione di attendibilità parziale, è necessario inserire l' `Process.Start` istruzione in un oggetto separato `Sub` . La chiamata iniziale a `Sub` avrà esito negativo. In questo modo, è possibile `Try...Catch` intercettarlo prima `Sub` che venga avviato l'oggetto che contiene `Process.Start` e l'eccezione di sicurezza prodotta.

## <a name="examples"></a>Esempi

### <a name="the-structure-of-trycatchfinally"></a>Struttura di try... Rileva... Infine

Nell'esempio seguente viene illustrata la struttura dell' `Try...Catch...Finally` istruzione.

[!code-vb[VbVbalrStatements#86](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#86)]  

### <a name="exception-in-a-method-called-from-a-try-block"></a>Eccezione in un metodo chiamato da un blocco try

Nell'esempio seguente, il `CreateException` metodo genera un'eccezione `NullReferenceException` . Il codice che genera l'eccezione non si trova in un `Try` blocco. Pertanto, il `CreateException` metodo non gestisce l'eccezione. Il `RunSample` metodo gestisce l'eccezione perché la chiamata al `CreateException` metodo si trova in un `Try` blocco.

Nell'esempio sono incluse `Catch` istruzioni per diversi tipi di eccezioni, ordinate dal più specifico al più generale.

[!code-vb[VbVbalrStatements#91](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#91)]

### <a name="the-catch-when-statement"></a>Istruzione catch when

Nell'esempio seguente viene illustrato come utilizzare un' `Catch When` istruzione per filtrare in un'espressione condizionale. Se l'espressione condizionale restituisce `True` , viene eseguito il codice nel `Catch` blocco.

[!code-vb[VbVbalrStatements#92](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#92)]

### <a name="nested-try-statements"></a>Istruzioni try nidificate

Nell'esempio seguente è `Try…Catch` presente un'istruzione contenuta in un `Try` blocco. Il `Catch` blocco interno genera un'eccezione la cui `InnerException` proprietà è impostata sull'eccezione originale. Il `Catch` blocco esterno segnala la propria eccezione e l'eccezione interna.

[!code-vb[VbVbalrStatements#93](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#93)]

### <a name="exception-handling-for-async-methods"></a>Gestione delle eccezioni per i metodi asincroni

L'esempio seguente illustra la gestione delle eccezioni per i metodi asincroni. Per intercettare un'eccezione che si applica a un'attività asincrona, l' `Await` espressione si trova in un `Try` blocco del chiamante e l'eccezione viene rilevata nel `Catch` blocco.

Rimuovere il commento dalla riga `Throw New Exception` nell'esempio per illustrare la gestione delle eccezioni. L'eccezione viene rilevata nel `Catch` blocco, la proprietà dell'attività `IsFaulted` viene impostata su `True` e la proprietà dell'attività `Exception.InnerException` viene impostata sull'eccezione.

Rimuovere il commento dalla riga `Throw New OperationCancelledException` per illustrare cosa accade quando si annulla un processo asincrono. L'eccezione viene rilevata nel `Catch` blocco e la proprietà dell'attività `IsCanceled` viene impostata su `True` . Tuttavia, in alcune condizioni che non si applicano a questo esempio, `IsFaulted` è impostato su `True` e `IsCanceled` è impostato su `False` .

[!code-vb[csAsyncExceptions#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/csasyncexceptions/vb/class1.vb#1)]

### <a name="handling-multiple-exceptions-in-async-methods"></a>Gestione di più eccezioni nei metodi asincroni

Il seguente esempio illustra la gestione delle eccezioni dove più attività possono restituire più eccezioni. Il `Try` blocco include l' `Await` espressione per l'attività <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> restituita. L'attività viene completata quando vengono completate le tre attività a cui <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> viene applicato.

Ognuna delle tre attività genera un'eccezione. Il `Catch` blocco scorre le eccezioni presenti nella `Exception.InnerExceptions` proprietà dell'attività `Task.WhenAll` restituita.

[!code-vb[csAsyncExceptions#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/csasyncexceptions/vb/class1.vb#3)]

## <a name="see-also"></a>Vedere anche

- <xref:Microsoft.VisualBasic.Information.Err%2A>
- <xref:System.Exception>
- [Istruzione Exit](exit-statement.md)
- [Istruzione On Error](on-error-statement.md)
- [Procedure consigliate per l'uso dei frammenti di codice](/visualstudio/ide/best-practices-for-using-code-snippets)
- [Gestione delle eccezioni](../../../standard/parallel-programming/exception-handling-task-parallel-library.md)
- [Istruzione throw](throw-statement.md)
