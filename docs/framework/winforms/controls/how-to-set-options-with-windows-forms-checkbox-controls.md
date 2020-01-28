---
title: Impostare le opzioni con i controlli CheckBox
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- checked
helpviewer_keywords:
- CheckBox control [Windows Forms], checked state
- check boxes [Windows Forms], using to set options
- CheckBox control [Windows Forms], using to set options
ms.assetid: 2ac70498-7e3e-4e07-8901-ccabaeb5fd3e
ms.openlocfilehash: 84198eab42aa02b1bb37fa16a3c4247a37f58a10
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746774"
---
# <a name="how-to-set-options-with-windows-forms-checkbox-controls"></a>Procedura: Impostare opzioni con i controlli CheckBox di Windows Form
Un controllo Windows Forms <xref:System.Windows.Forms.CheckBox> viene usato per fornire agli utenti le opzioni true/false o Yes/No. Il controllo Visualizza un segno di spunta quando viene selezionato.  
  
### <a name="to-set-options-with-checkbox-controls"></a>Per impostare le opzioni con i controlli CheckBox  
  
1. Esaminare il valore della proprietà <xref:System.Windows.Forms.CheckBox.Checked%2A> per determinarne lo stato e utilizzare tale valore per impostare un'opzione.  
  
     Nell'esempio di codice riportato di seguito, quando viene generato l'evento <xref:System.Windows.Forms.CheckBox.CheckedChanged> del controllo <xref:System.Windows.Forms.CheckBox>, la proprietà <xref:System.Windows.Forms.Control.AllowDrop%2A> del form è impostata su `false` se la casella di controllo è selezionata. Questa operazione è utile per le situazioni in cui si desidera limitare l'interazione dell'utente.  
  
    ```vb  
    Private Sub CheckBox1_CheckedChanged(ByVal sender As System.Object, _  
       ByVal e As System.EventArgs) Handles CheckBox1.CheckedChanged  
       ' Determine the CheckState of the check box.  
       If CheckBox1.CheckState = CheckState.Checked Then  
          ' If checked, do not allow items to be dragged onto the form.  
          Me.AllowDrop = False  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void checkBox1_CheckedChanged(object sender, System.EventArgs e)  
    {  
       // Determine the CheckState of the check box.  
       if (checkBox1.CheckState == CheckState.Checked)   
       {  
          // If checked, do not allow items to be dragged onto the form.  
          this.AllowDrop = false;  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void checkBox1_CheckedChanged(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          // Determine the CheckState of the check box.  
          if (checkBox1->CheckState == CheckState::Checked)   
          {  
             // If checked, do not allow items to be dragged onto the form.  
             this->AllowDrop = false;  
          }  
       }  
    ```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.CheckBox>
- [Panoramica sul controllo CheckBox](checkbox-control-overview-windows-forms.md)
- [Procedura: Rispondere alla selezione di controlli CheckBox di Windows Form](how-to-respond-to-windows-forms-checkbox-clicks.md)
- [Controllo CheckBox](checkbox-control-windows-forms.md)
