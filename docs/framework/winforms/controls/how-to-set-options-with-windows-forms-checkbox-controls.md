---
title: 'Procedura: Impostare le opzioni con i controlli CheckBox di Windows Form'
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
ms.openlocfilehash: 3eb68d76d936f13e78d13629455c6ac7fb537b40
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57714788"
---
# <a name="how-to-set-options-with-windows-forms-checkbox-controls"></a><span data-ttu-id="52205-102">Procedura: Impostare le opzioni con i controlli CheckBox di Windows Form</span><span class="sxs-lookup"><span data-stu-id="52205-102">How to: Set Options with Windows Forms CheckBox Controls</span></span>
<span data-ttu-id="52205-103">Un controllo Windows Form <xref:System.Windows.Forms.CheckBox> controllo tra le opzioni Sì/No o viene usato per assegnare gli utenti True/False.</span><span class="sxs-lookup"><span data-stu-id="52205-103">A Windows Forms <xref:System.Windows.Forms.CheckBox> control is used to give users True/False or Yes/No options.</span></span> <span data-ttu-id="52205-104">Quando viene selezionata, il controllo Visualizza un segno di spunta.</span><span class="sxs-lookup"><span data-stu-id="52205-104">The control displays a check mark when it is selected.</span></span>  
  
### <a name="to-set-options-with-checkbox-controls"></a><span data-ttu-id="52205-105">Per impostare le opzioni con i controlli CheckBox</span><span class="sxs-lookup"><span data-stu-id="52205-105">To set options with CheckBox controls</span></span>  
  
1.  <span data-ttu-id="52205-106">Esaminare il valore della <xref:System.Windows.Forms.CheckBox.Checked%2A> proprietà per determinare lo stato e utilizzare tale valore per impostare un'opzione.</span><span class="sxs-lookup"><span data-stu-id="52205-106">Examine the value of the <xref:System.Windows.Forms.CheckBox.Checked%2A> property to determine its state, and use that value to set an option.</span></span>  
  
     <span data-ttu-id="52205-107">Nell'esempio di codice seguente, quando la <xref:System.Windows.Forms.CheckBox> del controllo <xref:System.Windows.Forms.CheckBox.CheckedChanged> evento viene generato, del form <xref:System.Windows.Forms.Control.AllowDrop%2A> è impostata su `false` se è selezionata la casella di controllo.</span><span class="sxs-lookup"><span data-stu-id="52205-107">In the code sample below, when the <xref:System.Windows.Forms.CheckBox> control's <xref:System.Windows.Forms.CheckBox.CheckedChanged> event is raised, the form's <xref:System.Windows.Forms.Control.AllowDrop%2A> property is set to `false` if the check box is checked.</span></span> <span data-ttu-id="52205-108">Ciò è utile nelle situazioni in cui si vuole limitare l'interazione dell'utente.</span><span class="sxs-lookup"><span data-stu-id="52205-108">This is useful for situations where you want to restrict user interaction.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="52205-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="52205-109">See also</span></span>
- <xref:System.Windows.Forms.CheckBox>
- [<span data-ttu-id="52205-110">Panoramica sul controllo CheckBox</span><span class="sxs-lookup"><span data-stu-id="52205-110">CheckBox Control Overview</span></span>](checkbox-control-overview-windows-forms.md)
- [<span data-ttu-id="52205-111">Procedura: Rispondere a un Windows Form controlli CheckBox</span><span class="sxs-lookup"><span data-stu-id="52205-111">How to: Respond to Windows Forms CheckBox Clicks</span></span>](how-to-respond-to-windows-forms-checkbox-clicks.md)
- [<span data-ttu-id="52205-112">Controllo CheckBox</span><span class="sxs-lookup"><span data-stu-id="52205-112">CheckBox Control</span></span>](checkbox-control-windows-forms.md)
