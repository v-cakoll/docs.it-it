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
ms.openlocfilehash: f1d22079dfa3a6452efb74ef57530bb43e059a4a
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/31/2019
ms.locfileid: "73197097"
---
# <a name="walkthrough-updating-status-bar-information-at-run-time"></a>Procedura dettagliata: aggiornamento delle informazioni sulla barra di stato in fase di esecuzione
> [!IMPORTANT]
> I controlli <xref:System.Windows.Forms.StatusStrip> e <xref:System.Windows.Forms.ToolStripStatusLabel> sostituiscono e aggiungono funzionalità ai controlli <xref:System.Windows.Forms.StatusBar> e <xref:System.Windows.Forms.StatusBarPanel>; Tuttavia, se si sceglie, i controlli <xref:System.Windows.Forms.StatusBar> e <xref:System.Windows.Forms.StatusBarPanel> vengono conservati sia per la compatibilità con le versioni precedenti che per un uso futuro.  
  
 Spesso, in fase di esecuzione, un programma richiede di aggiornare in modo dinamico il contenuto dei pannelli della barra di stato in base alle modifiche dello stato dell'applicazione o all'interazione dell'utente. Si tratta di un metodo comune utilizzato per segnalare agli utenti che sono attivati tasti quali BLOC MAIUSC, BLOC NUM o BLOC SCORR oppure per fornire la data o un orologio come riferimento.  
  
 Nell'esempio seguente si userà un'istanza della classe <xref:System.Windows.Forms.StatusBarPanel> per ospitare un clock.  
  
### <a name="to-get-the-status-bar-ready-for-updating"></a>Per preparare la barra di stato per l'aggiornamento  
  
1. Creare un nuovo Windows Form.  
  
2. Aggiungere un oggetto <xref:System.Windows.Forms.StatusBar> al form. Per informazioni dettagliate, vedere [Procedura: aggiungere controlli a Windows Forms](how-to-add-controls-to-windows-forms.md).  
  
3. Aggiungere un pannello della barra di stato al controllo <xref:System.Windows.Forms.StatusBar>. Per informazioni dettagliate, vedere [Procedura: aggiungere pannelli a un controllo StatusBar](how-to-add-panels-to-a-statusbar-control.md).  
  
4. Per il controllo <xref:System.Windows.Forms.StatusBar> aggiunto al form, impostare la proprietà <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> su `true`.  
  
5. Aggiungere un Windows Forms <xref:System.Windows.Forms.Timer> componente al modulo.  
  
    > [!NOTE]
    > Il componente Windows Forms <xref:System.Windows.Forms.Timer?displayProperty=nameWithType> è progettato per un ambiente Windows Forms. Per informazioni su un timer adatto a un ambiente server, vedere [Introduzione ai timer basati su server](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90)).  
  
6. Impostare la proprietà <xref:System.Windows.Forms.Timer.Enabled%2A> su `true`.  
  
7. Impostare la proprietà <xref:System.Windows.Forms.Timer.Interval%2A> della <xref:System.Windows.Forms.Timer> su 30000.  
  
    > [!NOTE]
    > La proprietà <xref:System.Windows.Forms.Timer.Interval%2A> del componente <xref:System.Windows.Forms.Timer> è impostata su 30 secondi (30.000 millisecondi) per garantire che venga riflessa un'ora esatta nel tempo visualizzato.  
  
### <a name="to-implement-the-timer-to-update-the-status-bar"></a>Per implementare il timer per l'aggiornamento della barra di stato  
  
1. Inserire il codice seguente nel gestore eventi del componente <xref:System.Windows.Forms.Timer> per aggiornare il pannello del controllo <xref:System.Windows.Forms.StatusBar>.  
  
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
  
1. Effettuare il debug dell'applicazione, quindi premere F5 per eseguirla. Per informazioni dettagliate sul debug, vedere [Debug in Visual Studio](/visualstudio/debugger/debugger-feature-tour).  
  
    > [!NOTE]
    > Sono richiesti circa 30 secondi per visualizzare l'orologio sulla barra di stato. per ottenere l'ora più accurata possibile. Viceversa, per far apparire il clock prima, è possibile ridurre il valore della proprietà <xref:System.Windows.Forms.Timer.Interval%2A> impostata nel passaggio 7 della procedura precedente.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.StatusBar>
- <xref:System.Windows.Forms.ToolStripStatusLabel>
- [Procedura: Aggiungere pannelli a un controllo StatusBar](how-to-add-panels-to-a-statusbar-control.md)
- [Procedura: Individuare il pannello selezionato nel controllo StatusBar di Windows Form](determine-which-panel-wf-statusbar-control-was-clicked.md)
- [Cenni preliminari sul controllo StatusBar](statusbar-control-overview-windows-forms.md)
