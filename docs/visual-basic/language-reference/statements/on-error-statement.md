---
title: Istruzione On Error
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
ms.openlocfilehash: 0297f7af29faf5a08472fd1d18ca52e9b2fda1af
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404408"
---
# <a name="on-error-statement-visual-basic"></a>Istruzione On Error (Visual Basic)
Abilita una routine di gestione degli errori e specifica il percorso della routine all'interno di una routine. può essere usato anche per disabilitare una routine di gestione degli errori. L' `On Error` istruzione viene utilizzata nella gestione degli errori non strutturata e può essere utilizzata al posto della gestione strutturata delle eccezioni. La [gestione strutturata delle eccezioni](../../../standard/exceptions/index.md) è incorporata in .NET, è in genere più efficiente ed è quindi consigliabile quando si gestiscono errori di runtime nell'applicazione.

 Senza la gestione degli errori o la gestione delle eccezioni, eventuali errori di run-time che si verificano sono irreversibili: viene visualizzato un messaggio di errore e l'esecuzione viene arrestata.

> [!NOTE]
> La `Error` parola chiave viene inoltre utilizzata nell' [istruzione Error](error-statement.md), supportata per la compatibilità con le versioni precedenti.

## <a name="syntax"></a>Sintassi

```vb
On Error { GoTo [ line | 0 | -1 ] | Resume Next }
```

## <a name="parts"></a>Parti

|Termine|Definizione|
|---|---|
|`GoTo` *line*|Abilita la routine di gestione degli errori che inizia in corrispondenza della riga specificata nell'argomento della *riga* obbligatorio. L'argomento della *riga* è qualsiasi etichetta di riga o numero di riga. Se si verifica un errore in fase di esecuzione, controllare i rami alla riga specificata, rendendo attivo il gestore degli errori. La riga specificata deve essere nella stessa procedura dell' `On Error` istruzione oppure si verificherà un errore in fase di compilazione.|
|`GoTo 0`|Disabilita il gestore degli errori abilitato nella procedura corrente e lo reimposta su `Nothing` .|
|`GoTo -1`|Consente di disabilitare l'eccezione abilitata nella procedura corrente e di reimpostarla su `Nothing` .|
|`Resume Next`|Specifica che quando si verifica un errore in fase di esecuzione, il controllo passa all'istruzione immediatamente successiva all'istruzione in cui si è verificato l'errore e l'esecuzione continua da quel punto. Utilizzare questo form anziché `On Error GoTo` quando si accede a oggetti.|

## <a name="remarks"></a>Commenti

> [!NOTE]
> Si consiglia di utilizzare la gestione delle eccezioni strutturata nel codice, quando possibile, anziché utilizzare la gestione delle eccezioni non strutturata e l' `On Error` istruzione. Per altre informazioni, vedere [Istruzione Try...Catch...Finally](try-catch-finally-statement.md).

 Un gestore degli errori "Enabled" è uno attivato da un' `On Error` istruzione. Un gestore degli errori "attivo" è un gestore abilitato che sta gestendo un errore.

 Se si verifica un errore durante l'attivazione di un gestore errori (tra l'occorrenza dell'errore e un' `Resume` `Exit Sub` istruzione,, `Exit Function` o `Exit Property` ), il gestore degli errori della procedura corrente non è in grado di gestire l'errore. Il controllo torna alla procedura chiamante.
  
 Se la procedura chiamante dispone di un gestore degli errori abilitato, viene attivata per gestire l'errore. Se anche il gestore errori della procedura chiamante è attivo, il controllo passa di nuovo attraverso le routine di chiamata precedenti fino a quando non viene trovato un gestore degli errori abilitato, ma inattivo. Se non viene trovato alcun gestore di errori di questo tipo, l'errore è irreversibile nel punto in cui si è effettivamente verificato.
  
 Ogni volta che il gestore degli errori passa di nuovo il controllo a una routine chiamante, tale procedura diventa la routine corrente. Quando un errore viene gestito da un gestore degli errori in qualsiasi routine, l'esecuzione riprende nella procedura corrente nel punto indicato dall' `Resume` istruzione.
  
> [!NOTE]
> Una routine di gestione degli errori non è una `Sub` procedura o una `Function` procedura. Si tratta di una sezione di codice contrassegnata da un'etichetta di riga o un numero di riga.
  
## <a name="number-property"></a>Proprietà Number
 Le routine di gestione degli errori si basano sul valore della `Number` proprietà dell' `Err` oggetto per determinare la cause dell'errore. La routine deve verificare o salvare i valori delle proprietà rilevanti nell' `Err` oggetto prima che venga generato un altro errore o prima che venga chiamata una procedura che può causare un errore. I valori delle proprietà nell' `Err` oggetto riflettono solo l'errore più recente. Il messaggio di errore associato a `Err.Number` è contenuto in `Err.Description` .  
  
## <a name="throw-statement"></a>Istruzione Throw  
 Un errore generato con il `Err.Raise` metodo imposta la `Exception` proprietà su un'istanza appena creata della <xref:System.Exception> classe. Per supportare la generazione di eccezioni di tipi di eccezioni derivate, `Throw` nel linguaggio è supportata un'istruzione. Questo accetta un solo parametro che rappresenta l'istanza di eccezione da generare. Nell'esempio seguente viene illustrato il modo in cui queste funzionalità possono essere utilizzate con il supporto per la gestione delle eccezioni esistente:

 [!code-vb[VbVbalrErrorHandling#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrErrorHandling/VB/Class1.vb#17)]  
  
 Si noti che l' `On Error GoTo` istruzione intrappola tutti gli errori, indipendentemente dalla classe Exception.
  
## <a name="on-error-resume-next"></a>In seguito alla ripresa dell'errore
 `On Error Resume Next`fa in modo che l'esecuzione continui con l'istruzione che segue l'istruzione che ha causato l'errore di run-time o con l'istruzione immediatamente successiva alla chiamata più recente della routine che contiene l' `On Error Resume Next` istruzione. Questa istruzione consente di continuare l'esecuzione nonostante un errore di run-time. È possibile inserire la routine di gestione degli errori in cui si verifica l'errore anziché trasferire il controllo a un'altra posizione all'interno della procedura. Un' `On Error Resume Next` istruzione diventa inattiva quando viene chiamata un'altra procedura, quindi è consigliabile eseguire un' `On Error Resume Next` istruzione in ogni routine chiamata se si desidera la gestione degli errori inline all'interno di tale routine.
  
> [!NOTE]
> Il `On Error Resume Next` costrutto può essere preferibile a `On Error GoTo` quando si gestiscono gli errori generati durante l'accesso ad altri oggetti. `Err`Il controllo dopo ogni interazione con un oggetto comporta la rimozione dell'ambiguità sull'oggetto a cui il codice ha eseguito l'accesso. È possibile essere certi dell'oggetto in cui è stato inserito il codice di errore, nonché dell' `Err.Number` oggetto che ha generato in origine l'errore (l'oggetto specificato in `Err.Source` ).

## <a name="on-error-goto-0"></a>In errore GoTo 0
 `On Error GoTo 0`Disabilita la gestione degli errori nella procedura corrente. Non viene specificata la riga 0 come inizio del codice di gestione degli errori, anche se la procedura contiene una riga con numero 0. Senza un' `On Error GoTo 0` istruzione, un gestore degli errori viene disabilitato automaticamente quando si esce da una routine.

## <a name="on-error-goto--1"></a>In errore GoTo-1
 `On Error GoTo -1`Disabilita l'eccezione nella routine corrente. Non specifica la riga 1 come inizio del codice di gestione degli errori, anche se la procedura contiene una riga numerata-1. Senza un' `On Error GoTo -1` istruzione, un'eccezione viene disabilitata automaticamente quando si esce da una routine.

 Per impedire l'esecuzione di codice di gestione degli errori quando non si è verificato alcun errore, inserire un' `Exit Sub` `Exit Function` istruzione, o `Exit Property` immediatamente prima della routine di gestione degli errori, come nel frammento seguente:

 [!code-vb[VbVbalrErrorHandling#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrErrorHandling/VB/Class1.vb#18)]

 In questo caso, il codice di gestione degli errori segue l' `Exit Sub` istruzione e precede l' `End Sub` istruzione per separarla dal flusso di procedura. È possibile inserire il codice di gestione degli errori in qualsiasi punto di una procedura.

## <a name="untrapped-errors"></a>Errori non intercettati
 Gli errori non intercettati negli oggetti vengono restituiti all'applicazione di controllo quando l'oggetto è in esecuzione come file eseguibile. All'interno dell'ambiente di sviluppo, gli errori non intercettati vengono restituiti all'applicazione di controllo solo se sono impostate le opzioni corrette. Vedere la documentazione dell'applicazione host per una descrizione delle opzioni da impostare durante il debug, come impostarle e se l'host può creare classi.

 Se si crea un oggetto che accede ad altri oggetti, è consigliabile tentare di gestire gli eventuali errori non gestiti che passano di nuovo. Se non è possibile, eseguire il mapping dei codici di errore in `Err.Number` a uno dei propri errori, quindi passarli di nuovo al chiamante dell'oggetto. È necessario specificare l'errore aggiungendo il codice di errore alla `VbObjectError` costante. Se, ad esempio, il codice di errore è 1052, assegnarlo come segue:

 [!code-vb[VbVbalrErrorHandling#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrErrorHandling/VB/Class1.vb#19)]

> [!CAUTION]
> Gli errori di sistema durante le chiamate alle librerie di collegamento dinamico (dll) di Windows non generano eccezioni e non possono essere intercettati con Visual Basic l'intercettazione degli errori. Quando si chiamano le funzioni DLL, è necessario controllare ogni valore restituito per l'esito positivo o negativo (in base alle specifiche API) e, in caso di errore, controllare il valore nella `Err` proprietà dell'oggetto `LastDLLError` .

## <a name="example"></a>Esempio
 In questo esempio viene innanzitutto utilizzata l' `On Error GoTo` istruzione per specificare il percorso di una routine di gestione degli errori all'interno di una routine. Nell'esempio, un tentativo di dividere per zero genera il numero di errore 6. L'errore viene gestito nella routine di gestione degli errori e il controllo viene quindi restituito all'istruzione che ha causato l'errore. L' `On Error GoTo 0` istruzione disattiva l'intercettazione degli errori. Viene quindi `On Error Resume Next` utilizzata l'istruzione per rinviare l'intercettazione degli errori, in modo che il contesto per l'errore generato dall'istruzione successiva possa essere noto per alcuni. Si noti che `Err.Clear` viene usato per cancellare le `Err` proprietà dell'oggetto dopo che l'errore è stato gestito.

 [!code-vb[VbVbalrErrorHandling#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrErrorHandling/VB/Class1.vb#20)]

## <a name="requirements"></a>Requisiti
 **Spazio dei nomi:** [Microsoft. VisualBasic](../runtime-library-members.md)

 **Assembly:** Libreria di runtime Visual Basic (in Microsoft. VisualBasic. dll)

## <a name="see-also"></a>Vedere anche

- <xref:Microsoft.VisualBasic.Information.Err%2A>
- <xref:Microsoft.VisualBasic.ErrObject.Number%2A>
- <xref:Microsoft.VisualBasic.ErrObject.Description%2A>
- <xref:Microsoft.VisualBasic.ErrObject.LastDllError%2A>
- [Istruzione End](end-statement.md)
- [Istruzione Exit](exit-statement.md)
- [Istruzione Resume](resume-statement.md)
- [messaggi di errore](../error-messages/index.md)
- [Istruzione Try...Catch...Finally](try-catch-finally-statement.md)
