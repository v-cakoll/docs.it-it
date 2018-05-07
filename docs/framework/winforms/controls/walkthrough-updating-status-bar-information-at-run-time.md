---
title: 'Procedura dettagliata: aggiornamento delle informazioni sulla barra di stato in fase di esecuzione'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- status bars [Windows Forms], updating at run time
- status bars [Windows Forms], refreshing panels
- StatusBar control [Windows Forms], refreshing panels
- panels [Windows Forms], refreshing status bar
ms.assetid: cc2abb06-c082-49f7-a5a3-2fd1bbcb58d1
ms.openlocfilehash: 4b2d968aff157ac83b21823d546c052e140607a2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="walkthrough-updating-status-bar-information-at-run-time"></a>Procedura dettagliata: aggiornamento delle informazioni sulla barra di stato in fase di esecuzione
> [!IMPORTANT]
>  Il <xref:System.Windows.Forms.StatusStrip> e <xref:System.Windows.Forms.ToolStripStatusLabel> controlli sostituire e aggiungere funzionalità a di <xref:System.Windows.Forms.StatusBar> e <xref:System.Windows.Forms.StatusBarPanel> controlli; tuttavia, il <xref:System.Windows.Forms.StatusBar> e <xref:System.Windows.Forms.StatusBarPanel> vengono mantenuti per compatibilità con le versioni precedenti e per utilizzo futuro, se si Scegliere.  
  
 Spesso, in fase di esecuzione, un programma richiede di aggiornare in modo dinamico il contenuto dei pannelli della barra di stato in base alle modifiche dello stato dell'applicazione o all'interazione dell'utente. Si tratta di un metodo comune utilizzato per segnalare agli utenti che sono attivati tasti quali BLOC MAIUSC, BLOC NUM o BLOC SCORR oppure per fornire la data o un orologio come riferimento.  
  
 Nell'esempio seguente, si utilizzerà un'istanza di <xref:System.Windows.Forms.StatusBarPanel> classe per ospitare un orologio.  
  
### <a name="to-get-the-status-bar-ready-for-updating"></a>Per preparare la barra di stato per l'aggiornamento  
  
1.  Creare un nuovo Windows Form.  
  
2.  Aggiungere un oggetto <xref:System.Windows.Forms.StatusBar> al form. Per informazioni dettagliate, vedere [Procedura: aggiungere controlli a Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  
  
3.  Aggiungere un pannello della barra di stato per il <xref:System.Windows.Forms.StatusBar> controllo. Per informazioni dettagliate, vedere [Procedura: aggiungere pannelli a un controllo StatusBar](../../../../docs/framework/winforms/controls/how-to-add-panels-to-a-statusbar-control.md).  
  
4.  Per il <xref:System.Windows.Forms.StatusBar> controllo è stato aggiunto al form, impostare il <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> proprietà `true`.  
  
5.  Aggiungere un Windows Form <xref:System.Windows.Forms.Timer> componente al form.  
  
    > [!NOTE]
    >  Windows Form <xref:System.Windows.Forms.Timer?displayProperty=nameWithType> componente è progettato per un ambiente Windows Form. Per informazioni su un timer adatto a un ambiente server, vedere [Introduzione ai timer basati su server](http://msdn.microsoft.com/library/adc0bc0a-a519-4812-bafc-fb9d1a5801fc).  
  
6.  Impostare la proprietà <xref:System.Windows.Forms.Timer.Enabled%2A> su `true`.  
  
7.  Impostare il <xref:System.Windows.Forms.Timer.Interval%2A> proprietà del <xref:System.Windows.Forms.Timer> su 30000.  
  
    > [!NOTE]
    >  Il <xref:System.Windows.Forms.Timer.Interval%2A> proprietà del <xref:System.Windows.Forms.Timer> componente è impostato su 30 secondi (30.000 millisecondi) per garantire che l'ora esatta nel periodo di tempo visualizzato.  
  
### <a name="to-implement-the-timer-to-update-the-status-bar"></a>Per implementare il timer per l'aggiornamento della barra di stato  
  
1.  Inserire il codice seguente nel gestore eventi del <xref:System.Windows.Forms.Timer> componente da aggiornare il pannello del <xref:System.Windows.Forms.StatusBar> controllo.  
  
    ```vb  
    Private Sub Timer1_Tick(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Timer1.Tick  
       StatusBar1.Panels(0).Text = Now.ToShortTimeString  
    End Sub  
    ```  
  
    ```csharp  
    private void timer1_Tick(object sender, System.EventArgs e)  
    {  
       statusBar1.Panels[0].Text = DateTime.Now.ToShortTimeString();  
    }  
    ```  
  
    ```cpp  
    private:  
      System::Void timer1_Tick(System::Object ^ sender,  
        System::EventArgs ^ e)  
      {  
        statusBar1->Panels[0]->Text =  
          DateTime::Now.ToShortTimeString();  
      }  
    ```  
  
     Ora è possibile eseguire l'applicazione per osservare l'orologio in funzione nel pannello della barra di stato.  
  
### <a name="to-test-the-application"></a>Per eseguire il test dell'applicazione  
  
1.  Effettuare il debug dell'applicazione, quindi premere F5 per eseguirla. Per informazioni dettagliate sul debug, vedere [Debug in Visual Studio](/visualstudio/debugger/debugging-in-visual-studio).  
  
    > [!NOTE]
    >  Sono richiesti circa 30 secondi per visualizzare l'orologio sulla barra di stato. per ottenere l'ora più accurata possibile. Per visualizzare più rapidamente l'orologio, al contrario, è possibile ridurre il valore di <xref:System.Windows.Forms.Timer.Interval%2A> impostata nel passaggio 7 nella procedura precedente.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.StatusBar>  
 <xref:System.Windows.Forms.ToolStripStatusLabel>  
 [Procedura: Aggiungere pannelli a un controllo StatusBar](../../../../docs/framework/winforms/controls/how-to-add-panels-to-a-statusbar-control.md)  
 [Procedura: Individuare il pannello selezionato nel controllo StatusBar di Windows Form](../../../../docs/framework/winforms/controls/determine-which-panel-wf-statusbar-control-was-clicked.md)  
 [Cenni preliminari sul controllo StatusBar](../../../../docs/framework/winforms/controls/statusbar-control-overview-windows-forms.md)
