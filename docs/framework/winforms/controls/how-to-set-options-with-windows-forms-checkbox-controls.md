---
title: 'Procedura: Impostare opzioni con i controlli CheckBox di Windows Forms'
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
ms.openlocfilehash: 926e89272e9ebedb0668b26b96b1614e85e637ea
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59095919"
---
# <a name="how-to-set-options-with-windows-forms-checkbox-controls"></a>Procedura: Impostare opzioni con i controlli CheckBox di Windows Forms
Un controllo Windows Form <xref:System.Windows.Forms.CheckBox> controllo tra le opzioni Sì/No o viene usato per assegnare gli utenti True/False. Quando viene selezionata, il controllo Visualizza un segno di spunta.  
  
### <a name="to-set-options-with-checkbox-controls"></a>Per impostare le opzioni con i controlli CheckBox  
  
1.  Esaminare il valore della <xref:System.Windows.Forms.CheckBox.Checked%2A> proprietà per determinare lo stato e utilizzare tale valore per impostare un'opzione.  
  
     Nell'esempio di codice seguente, quando la <xref:System.Windows.Forms.CheckBox> del controllo <xref:System.Windows.Forms.CheckBox.CheckedChanged> evento viene generato, del form <xref:System.Windows.Forms.Control.AllowDrop%2A> è impostata su `false` se è selezionata la casella di controllo. Ciò è utile nelle situazioni in cui si vuole limitare l'interazione dell'utente.  
  
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
- [Panoramica del controllo CheckBox](checkbox-control-overview-windows-forms.md)
- [Procedura: Rispondere alla selezione dei controlli CheckBox di Windows Forms](how-to-respond-to-windows-forms-checkbox-clicks.md)
- [Controllo CheckBox](checkbox-control-windows-forms.md)
