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
# <a name="how-to-set-options-with-windows-forms-checkbox-controls"></a><span data-ttu-id="7ad84-102">Procedura: impostare opzioni con i controlli CheckBox di Windows Form</span><span class="sxs-lookup"><span data-stu-id="7ad84-102">How to: Set Options with Windows Forms CheckBox Controls</span></span>
<span data-ttu-id="7ad84-103">Un controllo Windows Forms <xref:System.Windows.Forms.CheckBox> viene usato per fornire agli utenti le opzioni true/false o Yes/No.</span><span class="sxs-lookup"><span data-stu-id="7ad84-103">A Windows Forms <xref:System.Windows.Forms.CheckBox> control is used to give users True/False or Yes/No options.</span></span> <span data-ttu-id="7ad84-104">Il controllo Visualizza un segno di spunta quando viene selezionato.</span><span class="sxs-lookup"><span data-stu-id="7ad84-104">The control displays a check mark when it is selected.</span></span>  
  
### <a name="to-set-options-with-checkbox-controls"></a><span data-ttu-id="7ad84-105">Per impostare le opzioni con i controlli CheckBox</span><span class="sxs-lookup"><span data-stu-id="7ad84-105">To set options with CheckBox controls</span></span>  
  
1. <span data-ttu-id="7ad84-106">Esaminare il valore della proprietà <xref:System.Windows.Forms.CheckBox.Checked%2A> per determinarne lo stato e utilizzare tale valore per impostare un'opzione.</span><span class="sxs-lookup"><span data-stu-id="7ad84-106">Examine the value of the <xref:System.Windows.Forms.CheckBox.Checked%2A> property to determine its state, and use that value to set an option.</span></span>  
  
     <span data-ttu-id="7ad84-107">Nell'esempio di codice riportato di seguito, quando viene generato l'evento <xref:System.Windows.Forms.CheckBox.CheckedChanged> del controllo <xref:System.Windows.Forms.CheckBox>, la proprietà <xref:System.Windows.Forms.Control.AllowDrop%2A> del form è impostata su `false` se la casella di controllo è selezionata.</span><span class="sxs-lookup"><span data-stu-id="7ad84-107">In the code sample below, when the <xref:System.Windows.Forms.CheckBox> control's <xref:System.Windows.Forms.CheckBox.CheckedChanged> event is raised, the form's <xref:System.Windows.Forms.Control.AllowDrop%2A> property is set to `false` if the check box is checked.</span></span> <span data-ttu-id="7ad84-108">Questa operazione è utile per le situazioni in cui si desidera limitare l'interazione dell'utente.</span><span class="sxs-lookup"><span data-stu-id="7ad84-108">This is useful for situations where you want to restrict user interaction.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="7ad84-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7ad84-109">See also</span></span>

- <xref:System.Windows.Forms.CheckBox>
- [<span data-ttu-id="7ad84-110">Panoramica sul controllo CheckBox</span><span class="sxs-lookup"><span data-stu-id="7ad84-110">CheckBox Control Overview</span></span>](checkbox-control-overview-windows-forms.md)
- [<span data-ttu-id="7ad84-111">Procedura: Rispondere alla selezione di controlli CheckBox di Windows Form</span><span class="sxs-lookup"><span data-stu-id="7ad84-111">How to: Respond to Windows Forms CheckBox Clicks</span></span>](how-to-respond-to-windows-forms-checkbox-clicks.md)
- [<span data-ttu-id="7ad84-112">Controllo CheckBox</span><span class="sxs-lookup"><span data-stu-id="7ad84-112">CheckBox Control</span></span>](checkbox-control-windows-forms.md)
