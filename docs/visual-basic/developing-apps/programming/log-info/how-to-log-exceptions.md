---
title: 'Procedura: registrare eccezioni in Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- exceptions, logging
- exceptions, tracking
ms.assetid: a26c60e2-ae39-444a-aebb-33eccadc0eeb
ms.openlocfilehash: b8ec45f43438f8181d9e045cdf43c81db34e4242
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33588526"
---
# <a name="how-to-log-exceptions-in-visual-basic"></a>Procedura: registrare eccezioni in Visual Basic
È possibile usare gli oggetti `My.Application.Log` e `My.Log` per registrare informazioni sulle eccezioni generate nell'applicazione. Questi esempi illustrano come usare il metodo `My.Application.Log.WriteException` per registrare le eccezioni rilevate in modo esplicito e quelle non gestite.  
  
 Per registrare le informazioni di traccia, usare il metodo `My.Application.Log.WriteEntry`. Per altre informazioni, vedere <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A>.  
  
### <a name="to-log-a-handled-exception"></a>Per registrare un'eccezione gestita  
  
1.  Creare il metodo che genererà le informazioni sull'eccezione.  
  
     [!code-vb[VbVbalrMyApplicationLog#9](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-exceptions_1.vb)]  
  
2.  Usare un blocco `Try...Catch` per rilevare l'eccezione.  
  
     [!code-vb[VbVbalrMyApplicationLog#6](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-exceptions_2.vb)]  
  
3.  Inserire il codice che potrebbe generare un'eccezione nel blocco `Try`.  
  
     Rimuovere il commento dalle righe `Dim` e `MsgBox` per causare un'eccezione <xref:System.NullReferenceException>.  
  
     [!code-vb[VbVbalrMyApplicationLog#7](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-exceptions_3.vb)]  
  
4.  Nel blocco `Catch` usare il metodo `My.Application.Log.WriteException` per scrivere le informazioni sull'eccezione.  
  
     [!code-vb[VbVbalrMyApplicationLog#8](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-exceptions_4.vb)]  
  
     L'esempio seguente illustra il codice completo per registrare un'eccezione gestita.  
  
     [!code-vb[VbVbalrMyApplicationLog#10](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-exceptions_5.vb)]  
  
### <a name="to-log-an-unhandled-exception"></a>Per registrare un'eccezione non gestita  
  
1.  Selezionare un progetto in **Esplora soluzioni**. Scegliere **Proprietà** dal menu **Progetto**.  
  
2.  Fare clic sulla scheda **Applicazione** .  
  
3.  Fare clic sul pulsante **Visualizza eventi applicazione** per aprire l'editor di codice.  
  
     Verrà aperto il file ApplicationEvents.vb.  
  
4.  Aprire il file ApplicationEvents.vb nell'editor di codice. Scegliere **Eventi MyApplication** dal menu **Generale**.  
  
5.  Scegliere **UnhandledException** dal menu **Dichiarazioni**.  
  
     L'applicazione genera l'evento <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException> prima dell'esecuzione dell'applicazione principale.  
  
6.  Aggiungere il metodo `My.Application.Log.WriteException` al gestore eventi `UnhandledException` .  
  
     [!code-vb[VbVbalrMyApplicationLog#4](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-exceptions_6.vb)]  
  
     L'esempio seguente illustra il codice completo per registrare un'eccezione non gestita.  
  
     [!code-vb[VbVbalrMyApplicationLog#5](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-exceptions_7.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=nameWithType>  
 <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A>  
 <xref:Microsoft.VisualBasic.Logging.Log.WriteException%2A>  
 [Utilizzo dei log applicazione](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md)  
 [Procedura: Scrivere messaggi di log](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-log-messages.md)  
 [Procedura dettagliata: Individuazione della posizione di inserimento delle informazioni con My.Application.Log](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md)  
 [Procedura dettagliata: Modifica della posizione di inserimento delle informazioni con My.Application.Log](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-changing-where-my-application-log-writes-information.md)
