---
title: 'Procedura: Controllare il punto di inserimento in un controllo TextBox di Windows Form'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- TextBox control [Windows Forms], insertion point
- insertion points [Windows Forms], TextBox controls
- text boxes [Windows Forms], controlling insertion point
ms.assetid: 5bee7d34-5121-429e-ab1f-d8ff67bc74c1
ms.openlocfilehash: 6ed49cac8341551dd0900a8468990e314a16e7b6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54660190"
---
# <a name="how-to-control-the-insertion-point-in-a-windows-forms-textbox-control"></a>Procedura: Controllare il punto di inserimento in un controllo TextBox di Windows Form
Quando un controllo Windows Form <xref:System.Windows.Forms.TextBox> controllo riceve lo stato attivo, l'inserimento dell'impostazione predefinita all'interno della casella di testo è a sinistra del testo esistente. L'utente può spostare il punto di inserimento con il mouse o tastiera. Se la casella di testo perde e riacquisisce quindi lo stato attivo, il punto di inserimento sarà ovunque l'utente ultima posizione assegnata.  
  
 In alcuni casi, questo comportamento può essere aggiunto all'utente. Applicazione di elaborazione di una parola, l'utente potrebbe prevedere caratteri di nuova visualizzazione dopo il testo esistente. In un'applicazione di immissione dati, l'utente potrebbe prevedere nuovi caratteri da sostituire qualsiasi voce esistente. Il <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> e <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> proprietà consentono di modificare il comportamento di un determinato scopo.  
  
### <a name="to-control-the-insertion-point-in-a-textbox-control"></a>Per controllare il punto di inserimento in un controllo TextBox  
  
1.  Impostare la proprietà <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> su un valore appropriato. Zero inserisce il punto di inserimento immediatamente a sinistra del primo carattere.  
  
2.  (Facoltativo) Impostare il <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> proprietà per la lunghezza del testo che si desidera selezionare.  
  
     Il codice seguente restituisce sempre il punto di inserimento su 0. Il `TextBox1_Enter` gestore dell'evento deve essere associato al controllo; per altre informazioni, vedere [creazione di gestori di eventi in Windows Form](../../../../docs/framework/winforms/creating-event-handlers-in-windows-forms.md).  
  
    ```vb  
    Private Sub TextBox1_Enter(ByVal sender As Object, ByVal e As System.EventArgs) Handles TextBox1.Enter  
       TextBox1.SelectionStart = 0  
       TextBox1.SelectionLength = 0  
    End Sub  
    ```  
  
    ```csharp  
    private void textBox1_Enter(Object sender, System.EventArgs e) {  
       textBox1.SelectionStart = 0;  
       textBox1.SelectionLength = 0;  
    }  
    ```  
  
    ```cpp  
    private:  
       void textBox1_Enter(System::Object ^  sender,  
          System::EventArgs ^  e)  
       {  
          textBox1->SelectionStart = 0;  
          textBox1->SelectionLength = 0;  
       }  
    ```  
  
## <a name="making-the-insertion-point-visible-by-default"></a>Rendere visibile per impostazione predefinita il punto di inserimento  
 Il <xref:System.Windows.Forms.TextBox> punto di inserimento è visibile per impostazione predefinita in un nuovo form solo nel <xref:System.Windows.Forms.TextBox> controllo è il primo nell'ordine di tabulazione. In caso contrario, il punto di inserimento viene visualizzata solo se si assegna il <xref:System.Windows.Forms.TextBox> lo stato attivo con la tastiera o con il mouse.  
  
#### <a name="to-make-the-text-box-insertion-point-visible-by-default-on-a-new-form"></a>Per rendere visibile punto di inserimento della casella di testo per impostazione predefinita in un nuovo modulo  
  
-   Impostare il <xref:System.Windows.Forms.TextBox> del controllo <xref:System.Windows.Forms.Control.TabIndex%2A> proprietà `0`.  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.Forms.TextBox>
- [Cenni preliminari sul controllo TextBox](../../../../docs/framework/winforms/controls/textbox-control-overview-windows-forms.md)
- [Procedura: Creare una casella di testo Password con il controllo TextBox di Windows Form](../../../../docs/framework/winforms/controls/how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [Procedura: Creare una casella di testo di sola lettura](../../../../docs/framework/winforms/controls/how-to-create-a-read-only-text-box-windows-forms.md)
- [Procedura: Inserire virgolette in una stringa](../../../../docs/framework/winforms/controls/how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [Procedura: Selezionare il testo nel controllo TextBox Windows Form](../../../../docs/framework/winforms/controls/how-to-select-text-in-the-windows-forms-textbox-control.md)
- [Procedura: Visualizzare più righe nel controllo TextBox Windows Form](../../../../docs/framework/winforms/controls/how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [Controllo TextBox](../../../../docs/framework/winforms/controls/textbox-control-windows-forms.md)
