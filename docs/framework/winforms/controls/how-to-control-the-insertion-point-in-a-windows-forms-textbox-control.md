---
title: Controllare il punto di inserimento nel controllo TextBox
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
ms.openlocfilehash: fd4803820921f0c922a4ce885f809abee8fd4c6c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742208"
---
# <a name="how-to-control-the-insertion-point-in-a-windows-forms-textbox-control"></a>Procedura: controllare il punto di inserimento in un controllo TextBox Windows Form
Quando un Windows Forms controllo <xref:System.Windows.Forms.TextBox> prima riceve lo stato attivo, l'inserimento predefinito all'interno della casella di testo si trova a sinistra di qualsiasi testo esistente. L'utente può spostare il punto di inserimento con la tastiera o con il mouse. Se la casella di testo perde e quindi riacquisisce lo stato attivo, il punto di inserimento sarà ogni volta che l'utente lo posiziona.  
  
 In alcuni casi, questo comportamento può essere sconcertante per l'utente. In un'applicazione di elaborazione di testo, l'utente potrebbe aspettarsi che vengano visualizzati nuovi caratteri dopo un testo esistente. In un'applicazione di immissione dati, l'utente può prevedere che i nuovi caratteri sostituiscano qualsiasi voce esistente. Le proprietà <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> e <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> consentono di modificare il comportamento in base ai propri scopi.  
  
### <a name="to-control-the-insertion-point-in-a-textbox-control"></a>Per controllare il punto di inserimento in un controllo TextBox  
  
1. Impostare la proprietà <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> su un valore appropriato. Zero posiziona il punto di inserimento immediatamente a sinistra del primo carattere.  
  
2. Opzionale Impostare la proprietà <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> sulla lunghezza del testo che si desidera selezionare.  
  
     Il codice seguente restituisce sempre il punto di inserimento a 0. Il gestore dell'evento `TextBox1_Enter` deve essere associato al controllo; Per ulteriori informazioni, vedere [creazione di gestori eventi in Windows Forms](../creating-event-handlers-in-windows-forms.md).  
  
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
  
## <a name="making-the-insertion-point-visible-by-default"></a>Rendere visibile il punto di inserimento per impostazione predefinita  
 Il punto di inserimento <xref:System.Windows.Forms.TextBox> è visibile per impostazione predefinita in un nuovo form solo se il controllo <xref:System.Windows.Forms.TextBox> è primo nell'ordine di tabulazione. In caso contrario, il punto di inserimento viene visualizzato solo se si assegna al <xref:System.Windows.Forms.TextBox> lo stato attivo con la tastiera o con il mouse.  
  
#### <a name="to-make-the-text-box-insertion-point-visible-by-default-on-a-new-form"></a>Per rendere visibile il punto di inserimento della casella di testo per impostazione predefinita in un nuovo form  
  
- Impostare la proprietà <xref:System.Windows.Forms.Control.TabIndex%2A> del controllo <xref:System.Windows.Forms.TextBox> su `0`.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.TextBox>
- [Cenni preliminari sul controllo TextBox](textbox-control-overview-windows-forms.md)
- [Procedura: Creare una casella di testo Password con il controllo TextBox di Windows Form](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [Procedura: Creare una casella di testo in sola lettura](how-to-create-a-read-only-text-box-windows-forms.md)
- [Procedura: Inserire virgolette in una stringa](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [Procedura: Selezionare testo nel controllo TextBox di Windows Form](how-to-select-text-in-the-windows-forms-textbox-control.md)
- [Procedura: Visualizzare più righe nel controllo TextBox di Windows Form](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [Controllo TextBox](textbox-control-windows-forms.md)
