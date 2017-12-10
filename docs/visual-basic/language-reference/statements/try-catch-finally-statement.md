---
title: Istruzione Try...Catch...Finally (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "69"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 56dd7fc339c452d64eb18211337b9a7674a83e1c
ms.sourcegitcommit: 685143b62385500f59bc36274b8adb191f573a16
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2017
---
# <a name="trycatchfinally-statement-visual-basic"></a>Istruzione Try...Catch...Finally (Visual Basic)
Fornisce un modo per gestire alcuni o tutti i possibili errori che possono verificarsi in un determinato blocco di codice, codice in esecuzione.  
  
## <a name="syntax"></a>Sintassi  
  
```  
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
|`tryStatements`|Parametro facoltativo. Istruzioni in cui può verificarsi un errore. Può essere un'istruzione composta.|  
|`Catch`|Parametro facoltativo. Più `Catch` blocchi consentiti. Se si verifica un'eccezione durante l'elaborazione di `Try` blocco, ogni `Catch` istruzione viene esaminata in ordine testuale per stabilire se gestisce l'eccezione, con `exception` che rappresenta l'eccezione che è stata generata.|  
|`exception`|Parametro facoltativo. Qualsiasi nome di variabile. Il valore iniziale di `exception` corrisponde al valore dell'errore generato. Utilizzato con `Catch` per specificare l'errore rilevato. Se omesso, il `Catch` istruzione genera un'eccezione.|  
|`type`|Parametro facoltativo. Specifica il tipo di filtro di classe. Se il valore di `exception` è di tipo specificato dal `type` o di un tipo derivato, l'identificatore viene associato all'oggetto eccezione.|  
|`When`|Parametro facoltativo. Oggetto `Catch` istruzione con un `When` clausola intercetta le eccezioni solo quando `expression` restituisce `True`. Oggetto `When` clausola viene applicata solo dopo il tipo di eccezione, il controllo e `expression` possono fare riferimento a un identificatore che rappresenta l'eccezione.|  
|`expression`|Parametro facoltativo. Deve essere convertibile in modo implicito in `Boolean`. Qualsiasi espressione che descrive un filtro generico. In genere utilizzato per filtrare in base al numero di errore. Utilizzato con `When` (parola chiave) per specificare le circostanze in cui viene rilevato l'errore.|  
|`catchStatements`|Parametro facoltativo. Le istruzioni per gestire gli errori che si verificano in associato `Try` blocco. Può essere un'istruzione composta.|  
|`Exit Try`|Parametro facoltativo. Parola chiave che viene interrotta la `Try...Catch...Finally` struttura. Riprende l'esecuzione con il codice che segue immediatamente il `End Try` istruzione. Il `Finally` verrà eseguita l'istruzione. Non è consentito in `Finally` blocchi.|  
|`Finally`|Parametro facoltativo. Oggetto `Finally` blocco viene eseguito quando l'esecuzione lascia qualsiasi parte di `Try...Catch` istruzione.|  
|`finallyStatements`|Parametro facoltativo. Istruzioni che vengono eseguite dopo ogni altra elaborazione errore si è verificato.|  
|`End Try`|Termina il `Try...Catch...Finally` struttura.|  
  
## <a name="remarks"></a>Note  
 Se si prevede che una particolare eccezione potrebbe verificarsi durante una particolare sezione di codice, inserire il codice in un `Try` blocco e utilizzare un `Catch` blocco per mantenere il controllo e gestire l'eccezione, se si verifica.  
  
 Oggetto `Try…Catch` costituita da un `Try` blocco seguito da uno o più `Catch` clausole che specificano i gestori per eccezioni diverse. Quando viene generata un'eccezione un `Try` blocco [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] Cerca il `Catch` istruzione che gestisce l'eccezione. Se un oggetto corrispondente `Catch` istruzione non viene trovata, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] esamina il metodo che ha chiamato il metodo corrente, e così via lungo lo stack di chiamate. Se non `Catch` blocco viene trovato, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] Visualizza un messaggio di eccezione non gestita all'utente e interrompe l'esecuzione del programma.  
  
 È possibile utilizzare più `Catch` istruzione in un `Try…Catch` istruzione. In tal caso, l'ordine dei `Catch` clausole è importante in quanto vengono esaminate nell'ordine. Intercettare le eccezioni più specifiche prima di quelle meno specifiche.  
  
 Le operazioni seguenti `Catch` sono quelle meno specifiche condizioni dell'istruzione e intercetterà tutte le eccezioni che derivano dalla <xref:System.Exception> classe. È in genere necessario utilizzare una di queste variazioni come l'ultimo `Catch` blocco il `Try...Catch...Finally` struttura, dopo il rilevamento si prevede che tutte le eccezioni specifiche. Flusso di controllo non può mai raggiungere un `Catch` blocco che segue una di queste variazioni.  
  
-   Il `type` è `Exception`, ad esempio:`Catch ex As Exception`  
  
-   L'istruzione non ha alcun `exception` variabile, ad esempio:`Catch`  
  
 Quando un `Try…Catch…Finally` istruzione è annidata in un'altra `Try` blocco [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] esamina innanzitutto ogni `Catch` istruzione in più interna `Try` blocco. Se non corrisponde ad alcuna `Catch` istruzione viene trovata, la ricerca procede al `Catch` istruzioni esterna `Try…Catch…Finally` blocco.  
  
 Le variabili locali di un `Try` blocco non sono disponibili in un `Catch` bloccarsi, in quanto rappresentano blocchi separati. Se si desidera utilizzare una variabile in più di un blocco, dichiarare la variabile all'esterno di `Try...Catch...Finally` struttura.  
  
> [!TIP]
>  Il `Try…Catch…Finally` istruzione è disponibile come un frammento di codice IntelliSense. In Gestione frammenti di codice, espandere **modelli di codice - se, For Each, Try Catch, proprietà, e così via**e quindi **Error Handling (eccezioni)**. Per altre informazioni, vedere [Code Snippets](/visualstudio/ide/code-snippets) (Frammenti di codice).  
  
## <a name="finally-block"></a>Blocco finally  
 Se si dispone di uno o più istruzioni da eseguire prima di chiudere il `Try` struttura, utilizzare un `Finally` blocco. Il controllo passa al `Finally` blocco appena prima di passare fuori il `Try…Catch` struttura. Questo vale anche se si verifica un'eccezione in un punto qualsiasi all'interno di `Try` struttura.  
  
 Oggetto `Finally` blocco è utile per l'esecuzione di qualsiasi codice che deve essere eseguito anche se si verifica un'eccezione. Per il controllo viene passato il `Finally` blocco indipendentemente dal modo in cui il `Try...Catch` uscita dal blocco.  
  
 Il codice in un `Finally` blocco viene eseguito anche se il codice rileva una `Return` istruzione in un `Try` o `Catch` blocco. Il controllo viene passato da un `Try` o `Catch` blocco corrispondente `Finally` blocco nei casi seguenti:  
  
-   Un [istruzione End](../../../visual-basic/language-reference/statements/end-statement.md) nella viene rilevato il `Try` o `Catch` blocco.  
  
-   Oggetto <xref:System.StackOverflowException> viene generata `Try` o `Catch` blocco.  
  
 Non è valido per trasferire in modo esplicito l'esecuzione in un `Finally` blocco. Trasferimento di esecuzione all'esterno di un `Finally` blocco non è valido, ad eccezione di tramite un'eccezione.  
  
 Se un `Try` istruzione non contiene almeno un `Catch` blocco, deve contenere un `Finally` blocco.  
  
> [!TIP]
>  Se non si dispone di rilevare eccezioni specifiche, il `Using` istruzione si comporta come un `Try…Finally` blocco e garantisce l'eliminazione delle risorse, indipendentemente dalla modalità di uscita dal blocco. Ciò è vero anche con un'eccezione non gestita. Per altre informazioni, vedere [Istruzione using](../../../visual-basic/language-reference/statements/using-statement.md).  
  
## <a name="exception-argument"></a>Argomento di eccezione  
 Il `Catch` blocco `exception` argomento è un'istanza di <xref:System.Exception> classe o una classe che deriva dal `Exception` classe. Il `Exception` istanza della classe corrisponde all'errore che si è verificato durante il `Try` blocco.  
  
 Le proprietà del `Exception` oggetto consentono di identificare la causa e la posizione di un'eccezione. Ad esempio, il <xref:System.Exception.StackTrace%2A> proprietà sono elencati i metodi chiamati che ha causato l'eccezione, consentendo di individuare dove si è verificato l'errore nel codice. <xref:System.Exception.Message%2A>Restituisce un messaggio che descrive l'eccezione. <xref:System.Exception.HelpLink%2A>Restituisce un collegamento a un file della Guida associato. <xref:System.Exception.InnerException%2A>Restituisce il `Exception` oggetto che ha causato l'eccezione corrente o restituisce `Nothing` se è presente alcun originale `Exception`.  
  
## <a name="considerations-when-using-a-trycatch-statement"></a>Considerazioni sull'uso di un blocco Try... Istruzione catch  
 Utilizzare un `Try…Catch` istruzione solo per segnalare la presenza di eventi anomali o imprevisti. Per motivi includono:  
  
-   Intercettare le eccezioni in fase di esecuzione viene creato un ulteriore sovraccarico e probabilmente più lento rispetto alla verifica preliminare per evitare le eccezioni.  
  
-   Se un `Catch` blocco non viene gestito correttamente, l'eccezione potrebbe non essere segnalata correttamente agli utenti.  
  
-   Gestione delle eccezioni rende più complesso un programma.  
  
 Non è sempre necessario un `Try…Catch` istruzione per verificare la presenza di una condizione che è probabile che si verifichi. Nell'esempio seguente verifica l'esistenza di un file prima di tentare di aprirlo. Questo riduce la necessità di rilevare un'eccezione generata dal <xref:System.IO.File.OpenText%2A> metodo.  
  
 [!code-vb[VbVbalrStatements#94](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/try-catch-finally-statement_1.vb)]  
  
 Verificare che il codice `Catch` blocchi possono segnalare correttamente le eccezioni per gli utenti, tramite registrazione thread-safe o i messaggi appropriati. In caso contrario, le eccezioni potrebbero rimanere sconosciute.  
  
## <a name="async-methods"></a>Metodi asincroni  
 Se si contrassegna un metodo con il [Async](../../../visual-basic/language-reference/modifiers/async.md) modificatore, è possibile utilizzare il [Await](../../../visual-basic/language-reference/operators/await-operator.md) operatore nel metodo. Un'istruzione con il `Await` operatore sospende l'esecuzione del metodo fino al completamento dell'attività attesa. L'attività rappresenta il lavoro attualmente in fase di esecuzione. Quando l'attività che è associato il `Await` operatore al termine, esecuzione riprende nello stesso metodo. Per ulteriori informazioni, vedere [flusso di controllo in programmi asincroni](../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md).  
  
 Un'attività restituita da un metodo asincrono può terminare con uno stato di errore che indica che è stata completata a causa di un'eccezione non gestita. Un'attività può inoltre terminare in uno stato annullato, determinando un `OperationCanceledException` viene generata un'eccezione all'esterno dell'espressione await. Per intercettare qualsiasi tipo di eccezione, inserire il `Await` espressione associata con l'attività in un `Try` bloccare e intercettare l'eccezione nel `Catch` blocco. Un esempio è disponibile più avanti in questo argomento.  
  
 Un'attività può essere in uno stato di errore perché più eccezioni sono stati responsabile per il tipo di errore. Ad esempio, l'attività può essere il risultato di una chiamata a <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType>. Quando si attende tale attività, l'eccezione rilevata è solo una delle eccezioni e non è possibile prevedere quale eccezione verrà rilevata. Un esempio è disponibile più avanti in questo argomento.  
  
 Un `Await` espressione non può essere all'interno di un `Catch` blocco o `Finally` blocco.  
  
## <a name="iterators"></a>Iteratori  
 Una funzione iterator o `Get` della funzione di accesso esegue un'iterazione personalizzata su una raccolta. Un iteratore Usa un [Yield](../../../visual-basic/language-reference/statements/yield-statement.md) istruzione per restituire ogni elemento della raccolta uno alla volta. Per chiamare una funzione iterator un [For Each... Istruzione successiva](../../../visual-basic/language-reference/statements/for-each-next-statement.md).  
  
 Oggetto `Yield` istruzione può essere presenti in un `Try` blocco. Oggetto `Try` blocco che contiene un `Yield` istruzione possono essere presenti `Catch` blocchi e può avere un `Finally` blocco. Vedere la sezione "provare a blocchi in Visual Basic" [iteratori](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7) per un esempio.  
  
 Oggetto `Yield` istruzione non può essere all'interno di un `Catch` blocco o un `Finally` blocco.  
  
 Se il `For Each` corpo (all'esterno della funzione di iteratore) genera un'eccezione, un `Catch` blocco nella funzione iteratore non viene eseguita, ma un `Finally` blocco nella funzione iteratore viene eseguito. Oggetto `Catch` blocco all'interno di una funzione iterator intercetta solo le eccezioni che si verificano all'interno della funzione iteratore.  
  
## <a name="partial-trust-situations"></a>Situazioni di attendibilità parziale  
 In situazioni di attendibilità parziale, ad esempio un'applicazione ospitata in una condivisione di rete, `Try...Catch...Finally` non intercetta le eccezioni di sicurezza che si verificano prima che venga richiamato il metodo che contiene la chiamata. L'esempio seguente, quando si posiziona su una condivisione server ed eseguita da qui, produce l'errore "System.Security.SecurityException: richiesta non riuscita." Per ulteriori informazioni sulle eccezioni di sicurezza, vedere la <xref:System.Security.SecurityException> classe.  
  
 [!code-vb[VbVbalrStatements#85](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/try-catch-finally-statement_2.vb)]  
  
 In una situazione di attendibilità parziale di questo tipo, è necessario inserire il `Process.Start` istruzione in un apposito `Sub`. La chiamata iniziale al `Sub` avrà esito negativo. In questo modo `Try...Catch` per intercettare, prima di `Sub` contenente `Process.Start` viene avviato e ha causato l'eccezione di sicurezza.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrata la struttura del `Try...Catch...Finally` istruzione.  
  
 [!code-vb[VbVbalrStatements#86](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/try-catch-finally-statement_3.vb)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente, il `CreateException` metodo genera un `NullReferenceException`. Il codice che genera l'eccezione non si trova in un `Try` blocco. Pertanto, il `CreateException` metodo gestisce l'eccezione. Il `RunSample` metodo gestisce l'eccezione perché la chiamata al `CreateException` metodo è incluso un `Try` blocco.  
  
 L'esempio include `Catch` istruzioni per diversi tipi di eccezioni, ordinate dalle più specifica alla più generale.  
  
 [!code-vb[VbVbalrStatements#91](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/try-catch-finally-statement_4.vb)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come utilizzare un `Catch When` istruzione da filtrare un'espressione condizionale. Se l'espressione condizionale restituisce `True`, il codice di `Catch` blocco viene eseguito.  
  
 [!code-vb[VbVbalrStatements#92](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/try-catch-finally-statement_5.vb)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente è presente un `Try…Catch` istruzione contenuta in un `Try` blocco. Interna `Catch` blocco genera un'eccezione che ha il `InnerException` impostata per l'eccezione originale. Esterna `Catch` blocco segnala la propria eccezione e l'eccezione interna.  
  
 [!code-vb[VbVbalrStatements#93](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/try-catch-finally-statement_6.vb)]  
  
## <a name="example"></a>Esempio  
 L'esempio seguente illustra la gestione delle eccezioni per i metodi asincroni. Per intercettare un'eccezione che si applica a un'attività asincrona, il `Await` l'espressione ha un `Try` blocco del chiamante e l'eccezione viene intercettata nel `Catch` blocco.  
  
 Rimuovere il commento dalla riga `Throw New Exception` nell'esempio per illustrare la gestione delle eccezioni. L'eccezione viene intercettata nel `Catch` blocco, l'attività `IsFaulted` è impostata su `True`e l'attività `Exception.InnerException` proprietà è impostata sull'eccezione.  
  
 Rimuovere il commento dalla riga `Throw New OperationCancelledException` per illustrare cosa accade quando si annulla un processo asincrono. L'eccezione viene intercettata nel `Catch` blocco e l'attività `IsCanceled` è impostata su `True`. Tuttavia, in alcune condizioni che non si applicano a questo esempio, `IsFaulted` è impostato su `True` e `IsCanceled` è impostato su `False`.  
  
 [!code-vb[csAsyncExceptions#1](../../../csharp/language-reference/keywords/codesnippet/VisualBasic/try-catch-finally-statement_7.vb)]  
  
## <a name="example"></a>Esempio  
 Il seguente esempio illustra la gestione delle eccezioni dove più attività possono restituire più eccezioni. Il `Try` blocco ha la `Await` espressione per l'attività che <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> restituito. L'attività viene completata quando le tre attività a cui <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> viene applicato sono state completate.  
  
 Ognuna delle tre attività genera un'eccezione. Il `Catch` blocco scorre le eccezioni, che si trovano nel `Exception.InnerExceptions` proprietà dell'attività che `Task.WhenAll` restituito.  
  
 [!code-vb[csAsyncExceptions#3](../../../csharp/language-reference/keywords/codesnippet/VisualBasic/try-catch-finally-statement_8.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:Microsoft.VisualBasic.Information.Err%2A>  
 <xref:System.Exception>  
 [Istruzione Exit](../../../visual-basic/language-reference/statements/exit-statement.md)  
 [Istruzione On Error](../../../visual-basic/language-reference/statements/on-error-statement.md)  
 [Procedure consigliate per l'uso dei frammenti di codice](/visualstudio/ide/best-practices-for-using-code-snippets)  
 [Gestione delle eccezioni](../../../../docs/standard/parallel-programming/exception-handling-task-parallel-library.md)  
 [Istruzione Throw](../../../visual-basic/language-reference/statements/throw-statement.md)
