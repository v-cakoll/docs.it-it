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
ms.openlocfilehash: 0a5a5261e6b71178adce02a5635c1f91a1469f3d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61784072"
---
# <a name="on-error-statement-visual-basic"></a>Istruzione On Error (Visual Basic)
Consente a una routine di gestione degli errori e specifica il percorso della routine all'interno di una routine. è anche utilizzabile per disabilitare una routine di gestione degli errori.  
  
 Senza la gestione degli errori è irreversibile qualsiasi errore di run-time che si verifica: viene visualizzato un messaggio di errore e l'esecuzione viene arrestata.  
  
 Quando possibile, si consiglia di usare la gestione del codice, anziché utilizzare la gestione delle eccezioni non strutturata delle eccezioni strutturata e `On Error` istruzione. Per altre informazioni, vedere [Istruzione Try...Catch...Finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).  
  
> [!NOTE]
>  Il `Error` parola chiave viene usata anche nel [Error (istruzione)](../../../visual-basic/language-reference/statements/error-statement.md), che è supportata per compatibilità con le versioni precedenti.  
  
## <a name="syntax"></a>Sintassi  
  
```  
On Error { GoTo [ line | 0 | -1 ] | Resume Next }  
```  
  
## <a name="parts"></a>Parti  
  
|Termine|Definizione|  
|---|---|  
|`GoTo` `line`|Abilita la routine di gestione degli errori che inizia alla riga specificata in richiesti `line` argomento. Il `line` argomento è un'etichetta di riga o un numero di riga. Se si verifica un errore di run-time, controllare la riga specificata, attivando il gestore di errori dei rami. La riga specificata deve trovarsi nella stessa routine come il `On Error` verrà eseguita l'istruzione o un errore in fase di compilazione.|  
|`GoTo` 0|Disabilita il gestore di errori abilitato nella procedura corrente e reimpostarlo su `Nothing`.|  
|`GoTo` -1|Disabilita eccezione abilitata nella procedura corrente e reimpostarlo su `Nothing`.|  
|`Resume Next`|Specifica che quando si verifica un errore di run-time, controllo passa all'istruzione immediatamente successiva all'istruzione in cui si è verificato l'errore e l'esecuzione continua da tale punto. Utilizzare questo modulo invece `On Error GoTo` l'accesso agli oggetti.|  
  
## <a name="remarks"></a>Note  
  
> [!NOTE]
>  È consigliabile usare Gestione strutturata delle eccezioni nel codice quando possibile, anziché utilizzare la gestione delle eccezioni non strutturati e `On Error` istruzione. Per altre informazioni, vedere [Istruzione Try...Catch...Finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).  
  
 Un gestore di errori "abilitato" è quello che è attivata per un `On Error` istruzione. Un gestore degli errori "active" è un gestore abilitato che sta per la gestione di un errore.  
  
 Se si verifica un errore mentre è attivo un gestore degli errori (tra l'occorrenza dell'errore e un `Resume`, `Exit Sub`, `Exit Function`, o `Exit Property` istruzione), il gestore di errori della stored procedure corrente non è possibile gestire l'errore. Controllo viene restituito alla routine chiamante.  
  
 Se la routine chiamante dispone di un gestore di errori abilitato, verrà attivato per gestire gli errori. Se il gestore di errori della stored procedure chiamante anche è attivo, il controllo passa attraverso procedure chiamante precedenti fino a quando non viene trovato un gestore di errori abilitato, ma inattiva. Se il gestore errori non viene trovato, l'errore è irreversibile nel punto in corrispondenza del quale si è effettivamente verificato.  
  
 Ogni volta che il gestore degli errori passa il controllo torna a una routine chiamante, questa diventerà la routine corrente. Dopo l'errore viene gestito da un gestore degli errori in tutte le procedure, l'esecuzione riprende nella procedura corrente in corrispondenza del punto designato dal `Resume` istruzione.  
  
> [!NOTE]
>  Una routine di gestione degli errori non è un `Sub` routine o un `Function` procedure. È una sezione di codice contrassegnato da un'etichetta di riga o un numero di riga.  
  
## <a name="number-property"></a>Proprietà Number  
 Routine di gestione degli errori si basano sul valore di `Number` proprietà del `Err` oggetto per determinare la causa dell'errore. La routine deve testare o salvare i valori delle proprietà pertinenti nel `Err` prima di qualsiasi altro errore può verificarsi o prima di una routine che potrebbe causare un errore è denominato dell'oggetto. I valori delle proprietà di `Err` oggetto riflettono solo l'errore più recente. Il messaggio di errore associato `Err.Number` contenuto in `Err.Description`.  
  
## <a name="throw-statement"></a>Istruzione Throw  
 Un errore che viene generato con il `Err.Raise` metodo imposta la `Exception` proprietà a un'istanza appena creata del <xref:System.Exception> classe. Per supportare la generazione di eccezioni derivate dei tipi di eccezione, un `Throw` istruzione è supportata nel linguaggio. Ciò richiede un solo parametro che rappresenta l'istanza di eccezione viene generata. Nell'esempio seguente viene illustrato come queste funzionalità possono essere utilizzate con supporto di gestione delle eccezioni esistenti:  
  
 [!code-vb[VbVbalrErrorHandling#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrErrorHandling/VB/Class1.vb#17)]  
  
 Si noti che il `On Error GoTo` istruzione intercetta tutti gli errori, indipendentemente dalla classe di eccezione.  
  
## <a name="on-error-resume-next"></a>On Error Resume Next  
 `On Error Resume Next` fa sì che l'esecuzione di continuare con l'istruzione immediatamente successiva all'istruzione che ha causato l'errore di run-time, oppure con l'istruzione immediatamente successiva all'ultima chiamata all'esterno di procedure che contiene il `On Error Resume Next` istruzione. Questa istruzione consente l'esecuzione di continuare nonostante sia un errore di run-time. È possibile inserire la routine di gestione degli errori in cui si verificherà l'errore anziché il trasferimento del controllo in un'altra posizione all'interno della routine. Un' `On Error Resume Next` istruzione diventa inattiva quando viene chiamata un'altra routine, pertanto è consigliabile eseguire un `On Error Resume Next` istruzione in ogni chiamata di routine se si desidera che all'interno di tale routine di gestione degli errori di linea.  
  
> [!NOTE]
>  Il `On Error Resume Next` costrutto può essere preferibile `On Error GoTo` durante la gestione degli errori generati durante l'accesso ad altri oggetti. Controllo `Err` dopo ogni interazione con un oggetto rimuove ambiguità intorno al quale oggetto ha effettuato l'accesso dal codice. È possibile che l'oggetto inserito il codice di errore in `Err.Number`, nonché l'oggetto che ha originariamente generato l'errore (l'oggetto specificato nel `Err.Source`).  
  
## <a name="on-error-goto-0"></a>On Error GoTo 0  
 `On Error GoTo 0` Disabilita la gestione degli errori nelle routine corrente. La riga 0 non viene specificata come l'inizio del codice di gestione degli errori, anche se la routine contiene una riga numerata da 0. Senza un `On Error GoTo 0` istruzione, un gestore degli errori viene automaticamente disabilitata quando si esce da una routine.  
  
## <a name="on-error-goto--1"></a>On Error GoTo -1  
 `On Error GoTo -1` Disabilita l'eccezione nella procedura corrente. Non specifica riga -1 come punto di partenza del codice di gestione degli errori, anche se la routine contiene una riga con il numero di -1. Senza un `On Error GoTo -1` istruzione, un'eccezione viene automaticamente disabilitata quando si esce da una routine.  
  
 Per evitare che il codice di gestione degli errori in esecuzione quando si è verificato alcun errore, inserire un `Exit Sub`, `Exit Function`, o `Exit Property` istruzione immediatamente prima della routine di gestione degli errori, come illustrato nel frammento seguente:  
  
 [!code-vb[VbVbalrErrorHandling#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrErrorHandling/VB/Class1.vb#18)]  
  
 In questo caso, il codice di gestione degli errori segue il `Exit Sub` istruzione e precede la `End Sub` che lo separano dal flusso della routine. È possibile inserire codice di gestione degli errori in un punto qualsiasi in una procedura.  
  
## <a name="untrapped-errors"></a>Errori non intercettati  
 Non intercettati errori negli oggetti vengono restituiti all'applicazione di controllo quando l'oggetto è in esecuzione come un file eseguibile. All'interno dell'ambiente di sviluppo, non intercettati gli errori vengono restituiti all'applicazione di controllo solo se sono impostate le opzioni appropriate. Vedere la documentazione dell'applicazione host per una descrizione dei quali opzioni devono essere impostato durante il debug, come impostarli e indica se l'host può creare classi.  
  
 Se si crea un oggetto che accede a altri oggetti, è consigliabile gestire errori non gestiti che passare di nuovo. Se non è possibile, il mapping di codici di errore `Err.Number` a uno dei propri errori e quindi passare nuovamente al chiamante dell'oggetto. È necessario specificare l'errore aggiungendo il codice di errore per il `VbObjectError` costante. Ad esempio, se il codice di errore è 1052, assegnarla come indicato di seguito:  
  
 [!code-vb[VbVbalrErrorHandling#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrErrorHandling/VB/Class1.vb#19)]  
  
> [!CAUTION]
>  Non generano eccezioni ed errori di sistema durante le chiamate alle librerie Windows a collegamento dinamico (DLL) non possono essere intercettati con intercettazione degli errori di Visual Basic. Quando si chiamano le funzioni di DLL, è necessario controllare ogni valore restituito per esito positivo o negativo (in base alle specifiche di API) e si verifica un errore, controllare il valore di `Err` dell'oggetto `LastDLLError` proprietà.  
  
## <a name="example"></a>Esempio  
 In questo esempio utilizza in primo luogo il `On Error GoTo` istruzione per specificare il percorso di una routine di gestione degli errori all'interno di una routine. Nell'esempio, un tentativo di dividere per zero genera il numero di errore 6. L'errore viene gestito nella routine di gestione degli errori e il controllo viene quindi restituito all'istruzione che ha causato l'errore. Il `On Error GoTo 0` istruzione consente di disattivare la registrazione degli errori. Il `On Error Resume Next` istruzione viene utilizzata per rinviare la registrazione degli errori in modo che il contesto dell'errore generato dall'istruzione successiva può essere riconosciuto per alcuni. Si noti che `Err.Clear` viene usato per cancellare il `Err` proprietà dell'oggetto dopo l'errore viene gestito.  
  
 [!code-vb[VbVbalrErrorHandling#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrErrorHandling/VB/Class1.vb#20)]  
  
## <a name="requirements"></a>Requisiti  
 **Spazio dei nomi:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)  
  
 **Assembly:** Visual Basic Runtime Library (in Microsoft.VisualBasic.dll)  
  
## <a name="see-also"></a>Vedere anche

- <xref:Microsoft.VisualBasic.Information.Err%2A>
- <xref:Microsoft.VisualBasic.ErrObject.Number%2A>
- <xref:Microsoft.VisualBasic.ErrObject.Description%2A>
- <xref:Microsoft.VisualBasic.ErrObject.LastDllError%2A>
- [Istruzione End](../../../visual-basic/language-reference/statements/end-statement.md)
- [Istruzione Exit](../../../visual-basic/language-reference/statements/exit-statement.md)
- [Istruzione Resume](../../../visual-basic/language-reference/statements/resume-statement.md)
- [Messaggi di errore](../../../visual-basic/language-reference/error-messages/index.md)
- [Istruzione Try...Catch...Finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
