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
ms.custom: seodec18
ms.openlocfilehash: eb04b6cff0847009407e38a3696e9be7c700356c
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75337337"
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

## <a name="parts"></a>Componenti

|Termine|Definizione|
|---|---|
|`tryStatements`|Parametro facoltativo. Istruzioni in cui può verificarsi un errore. Può essere un'istruzione composta.|
|`Catch`|Parametro facoltativo. Sono consentiti più blocchi di `Catch`. Se si verifica un'eccezione durante l'elaborazione del blocco di `Try`, ogni istruzione `Catch` viene esaminata in ordine testuale per determinare se gestisce l'eccezione, con `exception` che rappresenta l'eccezione generata.|
|`exception`|Parametro facoltativo. Qualsiasi nome di variabile. Il valore iniziale di `exception` corrisponde al valore dell'errore generato. Utilizzato con `Catch` per specificare l'errore rilevato. Se omesso, l'istruzione `Catch` intercetta qualsiasi eccezione.|
|`type`|Parametro facoltativo. Specifica il tipo di filtro di classe. Se il valore di `exception` è del tipo specificato da `type` o di un tipo derivato, l'identificatore viene associato all'oggetto Exception.|
|`When`|Parametro facoltativo. Un'istruzione `Catch` con una clausola `When` rileva le eccezioni solo quando `expression` restituisce `True`. Una clausola `When` viene applicata solo dopo avere verificato il tipo di eccezione e `expression` può fare riferimento all'identificatore che rappresenta l'eccezione.|
|`expression`|Parametro facoltativo. Deve essere convertibile in modo implicito in `Boolean`. Qualsiasi espressione che descrive un filtro generico. Usato in genere per filtrare in base al numero di errore. Utilizzato con `When` parola chiave per specificare le circostanze in cui viene rilevato l'errore.|
|`catchStatements`|Parametro facoltativo. Istruzioni per gestire gli errori che si verificano nel blocco `Try` associato. Può essere un'istruzione composta.|
|`Exit Try`|Parametro facoltativo. Parola chiave che si interrompe dalla struttura `Try...Catch...Finally`. L'esecuzione riprende con il codice immediatamente successivo all'istruzione `End Try`. L'istruzione `Finally` verrà comunque eseguita. Non consentito nei blocchi di `Finally`.|
|`Finally`|Parametro facoltativo. Un blocco `Finally` viene sempre eseguito quando l'esecuzione lascia una parte dell'istruzione `Try...Catch`.|
|`finallyStatements`|Parametro facoltativo. Istruzioni che vengono eseguite dopo l'elaborazione di tutti gli altri errori.|
|`End Try`|Termina la struttura del `Try...Catch...Finally`.|

## <a name="remarks"></a>Note

Se si prevede che una particolare eccezione possa verificarsi durante una particolare sezione di codice, inserire il codice in un blocco `Try` e usare un blocco `Catch` per mantenere il controllo e gestire l'eccezione, se si verifica.

Un'istruzione `Try…Catch` è costituita da un blocco `Try` seguito da una o più clausole `Catch`, che specificano i gestori per varie eccezioni. Quando viene generata un'eccezione in un blocco di `Try`, Visual Basic cerca l'istruzione `Catch` che gestisce l'eccezione. Se non viene trovata un'istruzione `Catch` corrispondente, Visual Basic esamina il metodo che ha chiamato il metodo corrente e così via fino allo stack di chiamate. Se non viene trovato alcun blocco `Catch`, Visual Basic Visualizza un messaggio di eccezione non gestita per l'utente e interrompe l'esecuzione del programma.

In un'istruzione `Try…Catch` è possibile utilizzare più di un'istruzione `Catch`. In tal caso, l'ordine delle clausole `Catch` è significativo perché vengono esaminate in ordine. Intercettare le eccezioni più specifiche prima di quelle meno specifiche.

Le seguenti condizioni di istruzione `Catch` sono le meno specifiche e intercettano tutte le eccezioni derivate dalla classe <xref:System.Exception>. In genere, è consigliabile usare una di queste varianti come ultimo blocco `Catch` nella struttura `Try...Catch...Finally`, dopo aver intercettato tutte le eccezioni specifiche previste. Il flusso di controllo non può mai raggiungere un blocco di `Catch` che segue una di queste varianti.

- Il `type` è `Exception`, ad esempio: `Catch ex As Exception`

- L'istruzione non ha `exception` variabile, ad esempio: `Catch`

Quando un'istruzione `Try…Catch…Finally` è annidata in un altro blocco di `Try`, Visual Basic esamina prima di tutto `Catch` istruzione nel blocco di `Try` più interno. Se non viene trovata alcuna istruzione `Catch` corrispondente, la ricerca procede con le istruzioni `Catch` del blocco `Try…Catch…Finally` esterno.

Le variabili locali da un blocco di `Try` non sono disponibili in un blocco `Catch` perché sono blocchi separati. Se si desidera utilizzare una variabile in più di un blocco, dichiarare la variabile all'esterno della struttura `Try...Catch...Finally`.

> [!TIP]
> L'istruzione `Try…Catch…Finally` è disponibile come frammento di codice IntelliSense. In Gestione frammenti di codice espandere modelli di **codice-if, for each, try catch, Property e così via**, quindi **gestione degli errori (eccezioni)** . Per altre informazioni, vedere [Code Snippets](/visualstudio/ide/code-snippets).

## <a name="finally-block"></a>Blocco finally

Se si dispone di una o più istruzioni che devono essere eseguite prima di uscire dalla struttura `Try`, utilizzare un blocco di `Finally`. Il controllo passa al blocco `Finally` immediatamente prima che venga passato dalla struttura di `Try…Catch`. Questo vale anche se si verifica un'eccezione in qualsiasi punto all'interno della struttura `Try`.

Un blocco `Finally` è utile per l'esecuzione di codice che deve essere eseguito anche se si verifica un'eccezione. Il controllo viene passato al blocco `Finally` indipendentemente dalla modalità di uscita del blocco di `Try...Catch`.

Il codice in un blocco di `Finally` viene eseguito anche se il codice rileva un'istruzione `Return` in un blocco `Try` o `Catch`. Il controllo non passa da un blocco `Try` o `Catch` al blocco `Finally` corrispondente nei casi seguenti:

- Un' [istruzione End](end-statement.md) viene rilevata nel blocco `Try` o `Catch`.

- Viene generata un'<xref:System.StackOverflowException> nel blocco `Try` o `Catch`.

Non è possibile trasferire in modo esplicito l'esecuzione in un blocco `Finally`. Il trasferimento dell'esecuzione da un blocco di `Finally` non è valido, ad eccezione di un'eccezione.

Se un'istruzione `Try` non contiene almeno un blocco di `Catch`, deve contenere un blocco di `Finally`.

> [!TIP]
> Se non è necessario intercettare eccezioni specifiche, l'istruzione `Using` si comporta come un blocco di `Try…Finally` e garantisce l'eliminazione delle risorse, indipendentemente dalla modalità di uscita dal blocco. Questo vale anche con un'eccezione non gestita. Per altre informazioni, vedere [Istruzione using](using-statement.md).

## <a name="exception-argument"></a>Argomento Exception

L'argomento `Catch` Block `exception` è un'istanza della classe <xref:System.Exception> o una classe che deriva dalla classe `Exception`. L'istanza della classe `Exception` corrisponde all'errore che si è verificato nel blocco di `Try`.

Le proprietà dell'oggetto `Exception` consentono di identificare la ragione e la posizione di un'eccezione. Ad esempio, la proprietà <xref:System.Exception.StackTrace%2A> elenca i metodi chiamati che hanno generato l'eccezione, consentendo di individuare la posizione in cui si è verificato l'errore nel codice. <xref:System.Exception.Message%2A> restituisce un messaggio in cui viene descritta l'eccezione. <xref:System.Exception.HelpLink%2A> restituisce un collegamento a un file della Guida associato. <xref:System.Exception.InnerException%2A> restituisce l'oggetto `Exception` che ha causato l'eccezione corrente oppure restituisce `Nothing` se non sono presenti `Exception`originali.

## <a name="considerations-when-using-a-trycatch-statement"></a>Considerazioni sull'utilizzo di un try... Istruzione catch

Utilizzare un'istruzione `Try…Catch` solo per segnalare l'occorrenza di eventi di programma insoliti o imprevisti. Di seguito sono riportati alcuni motivi:

- Il rilevamento delle eccezioni in fase di esecuzione comporta un sovraccarico aggiuntivo ed è probabilmente più lento rispetto al controllo preliminare per evitare eccezioni.

- Se un blocco di `Catch` non viene gestito correttamente, l'eccezione potrebbe non essere segnalata correttamente agli utenti.

- La gestione delle eccezioni rende un programma più complesso.

Non è sempre necessaria un'istruzione `Try…Catch` per verificare la presenza di una condizione che potrebbe verificarsi. Nell'esempio seguente viene verificata l'esistenza di un file prima di tentare di aprirlo. In questo modo si riduce la necessità di intercettare un'eccezione generata dal metodo <xref:System.IO.File.OpenText%2A>.

[!code-vb[VbVbalrStatements#94](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#94)]

Verificare che il codice nei blocchi di `Catch` possa segnalare correttamente le eccezioni agli utenti, sia tramite la registrazione thread-safe che i messaggi appropriati. In caso contrario, le eccezioni potrebbero rimanere sconosciute.

## <a name="async-methods"></a>Metodi asincroni

Se si contrassegna un metodo con il modificatore [Async](../modifiers/async.md) , è possibile usare l'operatore [await](../operators/await-operator.md) nel metodo. Un'istruzione con l'operatore `Await` sospende l'esecuzione del metodo fino al completamento dell'attività attesa. L'attività rappresenta il lavoro attualmente in fase di esecuzione. Quando l'attività associata all'operatore `Await` termina, l'esecuzione riprende nello stesso metodo. Per altre informazioni, vedere [flusso di controllo in programmi asincroni](../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md).

Un'attività restituita da un metodo asincrono può terminare con uno stato di errore, a indicare che è stata completata a causa di un'eccezione non gestita. Un'attività può inoltre terminare con uno stato annullato, il che comporta la generazione di un `OperationCanceledException` fuori dall'espressione await. Per intercettare entrambi i tipi di eccezione, inserire l'espressione `Await` associata all'attività in un blocco di `Try` e intercettare l'eccezione nel blocco `Catch`. Un esempio è disponibile più avanti in questo argomento.

Un'attività può essere in uno stato di errore perché più eccezioni erano responsabili dell'errore. Ad esempio, l'attività può essere il risultato di una chiamata a <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType>. Quando si attende tale attività, l'eccezione rilevata è solo una delle eccezioni e non è possibile prevedere quale eccezione verrà rilevata. Un esempio è disponibile più avanti in questo argomento.

Un'espressione `Await` non può trovarsi all'interno di un blocco di `Catch` o di `Finally`.

## <a name="iterators"></a>Iterators

Una funzione iteratore o una funzione di accesso `Get` esegue un'iterazione personalizzata su una raccolta. Un iteratore usa un'istruzione [yield](yield-statement.md) per restituire ogni elemento della raccolta uno alla volta. Si chiama una funzione iteratore usando un [per ogni... Istruzione successiva](for-each-next-statement.md).

Un'istruzione `Yield` può trovarsi all'interno di un blocco di `Try`. Un blocco di `Try` contenente un'istruzione `Yield` può includere `Catch` blocchi e può disporre di un blocco `Finally`. Per un esempio, vedere la sezione "blocchi try in Visual Basic" degli [iteratori](../../programming-guide/concepts/iterators.md) .

Un'istruzione `Yield` non può trovarsi all'interno di un blocco di `Catch` o di un blocco di `Finally`.

Se il corpo del `For Each` (all'esterno della funzione iteratore) genera un'eccezione, un blocco di `Catch` nella funzione iteratore non viene eseguito, ma viene eseguito un blocco `Finally` nella funzione iteratore. Un blocco `Catch` all'interno di una funzione iteratore intercetta solo le eccezioni che si verificano all'interno della funzione iteratore.

## <a name="partial-trust-situations"></a>Situazioni di attendibilità parziale

In situazioni di attendibilità parziale, ad esempio un'applicazione ospitata in una condivisione di rete, `Try...Catch...Finally` non rileva le eccezioni di sicurezza che si verificano prima che venga richiamato il metodo che contiene la chiamata. Nell'esempio seguente, quando lo si inserisce in una condivisione server e si esegue da questa posizione, viene generato l'errore "System. Security. SecurityException: request failed". Per ulteriori informazioni sulle eccezioni di sicurezza, vedere la classe <xref:System.Security.SecurityException>.

[!code-vb[VbVbalrStatements#85](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#85)]

In una situazione di attendibilità parziale, è necessario inserire l'istruzione `Process.Start` in un `Sub`separato. La chiamata iniziale al `Sub` avrà esito negativo. Questo consente `Try...Catch` di intercettarlo prima che venga avviata la `Sub` che contiene `Process.Start` e l'eccezione di sicurezza generata.

## <a name="examples"></a>Esempi

### <a name="the-structure-of-trycatchfinally"></a>Struttura di try... Rileva... Infine

Nell'esempio seguente viene illustrata la struttura dell'istruzione `Try...Catch...Finally`.

[!code-vb[VbVbalrStatements#86](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#86)]  

### <a name="exception-in-a-method-called-from-a-try-block"></a>Eccezione in un metodo chiamato da un blocco try

Nell'esempio seguente il metodo `CreateException` genera un'`NullReferenceException`. Il codice che genera l'eccezione non si trova in un blocco `Try`. Pertanto, il metodo `CreateException` non gestisce l'eccezione. Il metodo `RunSample` gestisce l'eccezione perché la chiamata al metodo `CreateException` si trova in un blocco di `Try`.

Nell'esempio sono incluse istruzioni `Catch` per diversi tipi di eccezioni, ordinate dal più specifico al più generale.

[!code-vb[VbVbalrStatements#91](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#91)]

### <a name="the-catch-when-statement"></a>Istruzione catch when

Nell'esempio seguente viene illustrato come utilizzare un'istruzione `Catch When` per filtrare in un'espressione condizionale. Se l'espressione condizionale restituisce `True`, viene eseguito il codice nel blocco di `Catch`.

[!code-vb[VbVbalrStatements#92](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#92)]

### <a name="nested-try-statements"></a>Istruzioni try nidificate

Nell'esempio seguente è presente un'istruzione `Try…Catch` contenuta in un blocco di `Try`. Il blocco `Catch` interno genera un'eccezione con la relativa proprietà `InnerException` impostata sull'eccezione originale. Il blocco `Catch` esterno segnala la propria eccezione e l'eccezione interna.

[!code-vb[VbVbalrStatements#93](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#93)]

### <a name="exception-handling-for-async-methods"></a>Gestione delle eccezioni per i metodi asincroni

L'esempio seguente illustra la gestione delle eccezioni per i metodi asincroni. Per intercettare un'eccezione che si applica a un'attività asincrona, l'espressione `Await` si trova in un blocco `Try` del chiamante e l'eccezione viene rilevata nel blocco `Catch`.

Rimuovere il commento dalla riga `Throw New Exception` nell'esempio per illustrare la gestione delle eccezioni. L'eccezione viene rilevata nel blocco `Catch`, la proprietà `IsFaulted` dell'attività è impostata su `True`e la proprietà `Exception.InnerException` dell'attività viene impostata sull'eccezione.

Rimuovere il commento dalla riga `Throw New OperationCancelledException` per illustrare cosa accade quando si annulla un processo asincrono. L'eccezione viene rilevata nel blocco `Catch` e la proprietà `IsCanceled` dell'attività è impostata su `True`. Tuttavia, in alcune condizioni che non si applicano a questo esempio, `IsFaulted` è impostato su `True` e `IsCanceled` è impostato su `False`.

[!code-vb[csAsyncExceptions#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/csasyncexceptions/vb/class1.vb#1)]

### <a name="handling-multiple-exceptions-in-async-methods"></a>Gestione di più eccezioni nei metodi asincroni

Il seguente esempio illustra la gestione delle eccezioni dove più attività possono restituire più eccezioni. Il blocco `Try` dispone dell'espressione `Await` per l'attività che <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> restituita. L'attività viene completata quando sono state completate le tre attività a cui <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> viene applicato.

Ognuna delle tre attività genera un'eccezione. Il blocco `Catch` scorre le eccezioni presenti nella proprietà `Exception.InnerExceptions` dell'attività che `Task.WhenAll` restituita.

[!code-vb[csAsyncExceptions#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/csasyncexceptions/vb/class1.vb#3)]

## <a name="see-also"></a>Vedere anche

- <xref:Microsoft.VisualBasic.Information.Err%2A>
- <xref:System.Exception>
- [Istruzione Exit](exit-statement.md)
- [Istruzione On Error](on-error-statement.md)
- [Procedure consigliate per l'uso dei frammenti di codice](/visualstudio/ide/best-practices-for-using-code-snippets)
- [Gestione delle eccezioni](../../../standard/parallel-programming/exception-handling-task-parallel-library.md)
- [Istruzione Throw](throw-statement.md)
