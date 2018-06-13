---
title: Istruzione On Error (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.OnError
helpviewer_keywords:
- Visual Basic code, control flow
- Resume Next statement [Visual Basic]
- errors [Visual Basic], trapping
- error handling, On Error statement
- Next statement [Visual Basic], On Error
- control flow [Visual Basic], branching
- Error keyword [Visual Basic]
- execution [Visual Basic], conditional
- Resume statement [Visual Basic], and On Error statement
- Error statement [Visual Basic], and On Error statement
- GoTo statement [Visual Basic], and On Error statement
- branching [Visual Basic], on error
- conditional statements [Visual Basic], On Error
- On Error statement [Visual Basic], syntax
- On keyword [Visual Basic]
- run-time errors [Visual Basic], handling
- On Error statement [Visual Basic]
ms.assetid: ff947930-fb84-40cf-bd66-1ea219561d5c
ms.openlocfilehash: b2e32dcca2e29a178af6dc985da536b47f0ebae6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33605095"
---
# <a name="on-error-statement-visual-basic"></a>Istruzione On Error (Visual Basic)
Abilita una routine di gestione degli errori e specifica il percorso della routine all'interno di una routine. consente inoltre di disabilitare una routine di gestione degli errori.  
  
 Senza la gestione degli errori, qualsiasi errore di run-time che si verifica rappresenta un errore irreversibile: viene visualizzato un messaggio di errore e l'esecuzione viene arrestata.  
  
 Quando possibile, si consiglia di utilizzare nel codice, anziché utilizzare la gestione strutturata delle eccezioni strutturata e `On Error` istruzione. Per altre informazioni, vedere [Istruzione Try...Catch...Finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).  
  
> [!NOTE]
>  Il `Error` (parola chiave) viene usato anche nel [Error (istruzione)](../../../visual-basic/language-reference/statements/error-statement.md), che è supportato per compatibilità con le versioni precedenti.  
  
## <a name="syntax"></a>Sintassi  
  
```  
On Error { GoTo [ line | 0 | -1 ] | Resume Next }  
```  
  
## <a name="parts"></a>Parti  
  
|Termine|Definizione|  
|---|---|  
|`GoTo` `line`|Consente la routine di gestione degli errori che inizia alla riga specificata in obbligatorio `line` argomento. Il `line` argomento è un'etichetta di riga o un numero di riga. Se si verifica un errore di run-time, controllare i branch per la riga specificata, attivando il gestore di errori. La riga specificata deve trovarsi nella stessa routine come il `On Error` verrà eseguita l'istruzione o un errore in fase di compilazione.|  
|`GoTo` 0|Disabilita gestore errori abilitato nella procedura corrente e viene reimpostato su `Nothing`.|  
|`GoTo` -1|Disabilita l'eccezione abilitata nella procedura corrente e viene reimpostato su `Nothing`.|  
|`Resume Next`|Specifica che quando si verifica un errore di run-time, controllo passa all'istruzione immediatamente successiva all'istruzione in cui si è verificato l'errore e l'esecuzione continua da tale punto. Utilizzare questo modulo anziché `On Error GoTo` quando l'accesso agli oggetti.|  
  
## <a name="remarks"></a>Note  
  
> [!NOTE]
>  È consigliabile utilizzare Gestione strutturata delle eccezioni nel codice ogni volta che è possibile, anziché utilizzare la gestione delle eccezioni non strutturata e `On Error` istruzione. Per altre informazioni, vedere [Istruzione Try...Catch...Finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).  
  
 Un gestore di errori "abilitato" è quello che viene attivato da un `On Error` istruzione. Un gestore degli errori "attivo" è un gestore abilitato che sta per la gestione di un errore.  
  
 Se si verifica un errore mentre un gestore degli errori è attivo (tra l'occorrenza dell'errore e un `Resume`, `Exit Sub`, `Exit Function`, o `Exit Property` istruzione), il gestore di errori della routine corrente non è possibile gestire l'errore. Controllo viene restituito alla routine chiamante.  
  
 Se la routine chiamante dispone di un gestore errori abilitato, verrà attivato per gestire gli errori. Se il gestore di errori della routine chiamata anche è attivo, il controllo passa attraverso la routine chiamate precedente finché non viene trovato un gestore errori abilitato ma inattivo. Se il gestore errori non viene trovato, l'errore è irreversibile nel punto in cui si è effettivamente verificato.  
  
 Ogni volta che il gestore degli errori passa il controllo torna a una routine chiamante, che diventa la routine corrente. Dopo l'errore viene gestito da un gestore di errori in tutte le procedure, nella routine corrente, dal punto indicato dall'esecuzione riprende il `Resume` istruzione.  
  
> [!NOTE]
>  Una routine di gestione degli errori non è un `Sub` stored procedure o un `Function` stored procedure. È una sezione di codice contrassegnato da un'etichetta di riga o un numero di riga.  
  
## <a name="number-property"></a>Proprietà Number  
 Routine di gestione degli errori si basano sul valore di `Number` proprietà del `Err` oggetto per determinare la causa dell'errore. La routine deve testare o salvare i valori di proprietà pertinenti di `Err` oggetto qualsiasi altro errore può verificarsi prima o una routine che potrebbe causare un errore viene richiamato. I valori delle proprietà di `Err` oggetto riflettono solo l'errore più recente. Il messaggio di errore associata a `Err.Number` è contenuto in `Err.Description`.  
  
## <a name="throw-statement"></a>Istruzione Throw  
 Un errore viene generato con il `Err.Raise` metodo imposta la `Exception` proprietà a un'istanza appena creata del <xref:System.Exception> classe. Per supportare la generazione di eccezioni di tipi derivati, un `Throw` nel linguaggio è supportata l'istruzione. Questo ha un singolo parametro che rappresenta l'istanza di eccezione viene generata. Nell'esempio seguente viene illustrato come utilizzare queste funzioni con il supporto di gestione delle eccezioni esistenti:  
  
 [!code-vb[VbVbalrErrorHandling#17](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/on-error-statement_1.vb)]  
  
 Si noti che il `On Error GoTo` istruzione vengono intercettati tutti gli errori, indipendentemente dalla classe di eccezione.  
  
## <a name="on-error-resume-next"></a>On Error Resume Next  
 `On Error Resume Next` fa sì che l'esecuzione continuare con l'istruzione immediatamente successiva all'istruzione che ha causato l'errore di run-time, o con l'istruzione immediatamente successiva all'ultima chiamata effettuata la stored procedure che contiene il `On Error Resume Next` istruzione. Questa istruzione consente di continuare nonostante sia stato un errore di run-time. È possibile inserire la routine di gestione degli errori in cui si verificherà l'errore, anziché trasferire il controllo in un'altra posizione all'interno della routine. Un `On Error Resume Next` istruzione diventa inattiva quando viene chiamata un'altra routine, pertanto è consigliabile eseguire un `On Error Resume Next` istruzione in ogni chiamata di routine se si desidera tale routine di gestione degli errori inline.  
  
> [!NOTE]
>  Il `On Error Resume Next` costrutto può essere preferibile `On Error GoTo` la gestione degli errori generati durante l'accesso ad altri oggetti. Controllo `Err` dopo ogni interazione con un oggetto, Elimina l'ambiguità sulla quale oggetto ha effettuato l'accesso dal codice. È possibile essere certi che l'oggetto inserito il codice di errore in `Err.Number`, nonché quale oggetto ha generato l'errore (l'oggetto specificato `Err.Source`).  
  
## <a name="on-error-goto-0"></a>On Error GoTo 0  
 `On Error GoTo 0` Disabilita la gestione degli errori in routine corrente. Riga 0 non specifica come l'inizio del codice di gestione degli errori, anche se la routine contiene una riga numerata da 0. Senza un `On Error GoTo 0` istruzione, un gestore degli errori viene disattivato automaticamente quando si esce da una routine.  
  
## <a name="on-error-goto--1"></a>On Error GoTo -1  
 `On Error GoTo -1` Disabilita l'eccezione nella procedura corrente. Non specifica riga -1 come punto di partenza del codice di gestione degli errori, anche se la routine contiene una riga numerata -1. Senza un `On Error GoTo -1` istruzione, un'eccezione viene disabilitata automaticamente quando si esce da una routine.  
  
 Per impedire che il codice di gestione degli errori in esecuzione quando non si è verificato alcun errore, inserire un `Exit Sub`, `Exit Function`, o `Exit Property` istruzione immediatamente prima della routine di gestione degli errori, come illustrato nel frammento seguente:  
  
 [!code-vb[VbVbalrErrorHandling#18](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/on-error-statement_2.vb)]  
  
 In questo caso, il codice di gestione degli errori segue il `Exit Sub` istruzione e precede il `End Sub` che lo separano dal flusso della routine. È possibile inserire il codice di gestione degli errori in un punto qualsiasi in una stored procedure.  
  
## <a name="untrapped-errors"></a>Errori non intercettati  
 Errori non intercettati negli oggetti vengono restituiti all'applicazione di controllo quando l'oggetto è in esecuzione come file eseguibile. All'interno dell'ambiente di sviluppo, non intercettati gli errori vengono restituiti all'applicazione di controllo solo se sono impostate le opzioni appropriate. Vedere la documentazione dell'applicazione host per una descrizione dei quali opzioni da impostare durante il debug, come impostarle e indica se l'host può creare classi.  
  
 Se si crea un oggetto che accede a altri oggetti, è consigliabile gestire errori non gestiti vengono passati. Se non è possibile, mappare i codici di errore `Err.Number` per uno degli errori, quindi passare nuovamente al chiamante dell'oggetto. È necessario specificare l'errore aggiungendo il codice di errore per il `VbObjectError` costante. Ad esempio, se il codice di errore è 1052, assegnarlo come indicato di seguito:  
  
 [!code-vb[VbVbalrErrorHandling#19](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/on-error-statement_3.vb)]  
  
> [!CAUTION]
>  Gli errori di sistema durante le chiamate alle librerie a collegamento dinamico (DLL) Windows non generano eccezioni e non possono essere intercettati con intercettazione degli errori di Visual Basic. Quando la chiamata di funzioni DLL, è necessario controllare ogni valore restituito per l'esito positivo o negativo (in base alle specifiche API) e in caso di errore, controllare il valore di `Err` dell'oggetto `LastDLLError` proprietà.  
  
## <a name="example"></a>Esempio  
 In questo esempio utilizza in primo luogo il `On Error GoTo` istruzione per specificare il percorso di una routine di gestione degli errori all'interno di una stored procedure. Nell'esempio, un tentativo di dividere per zero genera il numero di errore 6. Nella routine di gestione degli errori viene gestito l'errore e il controllo viene quindi restituito all'istruzione che ha causato l'errore. Il `On Error GoTo 0` istruzione consente di disattivare la registrazione degli errori. Il `On Error Resume Next` istruzione utilizzata per rinviare la registrazione degli errori in modo che il contesto per l'errore generato dall'istruzione successiva può essere riconosciuto per determinati. Si noti che `Err.Clear` viene utilizzato per cancellare il `Err` proprietà dell'oggetto dopo l'errore viene gestito.  
  
 [!code-vb[VbVbalrErrorHandling#20](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/on-error-statement_4.vb)]  
  
## <a name="requirements"></a>Requisiti  
 **Namespace:** [VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)  
  
 **Assembly:** libreria di Runtime di Visual Basic (in VisualBasic)  
  
## <a name="see-also"></a>Vedere anche  
 <xref:Microsoft.VisualBasic.Information.Err%2A>  
 <xref:Microsoft.VisualBasic.ErrObject.Number%2A>  
 <xref:Microsoft.VisualBasic.ErrObject.Description%2A>  
 <xref:Microsoft.VisualBasic.ErrObject.LastDllError%2A>  
 [Istruzione End](../../../visual-basic/language-reference/statements/end-statement.md)  
 [Istruzione Exit](../../../visual-basic/language-reference/statements/exit-statement.md)  
 [Istruzione Resume](../../../visual-basic/language-reference/statements/resume-statement.md)  
 [Messaggi di errore](../../../visual-basic/language-reference/error-messages/index.md)  
 [Istruzione Try...Catch...Finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
