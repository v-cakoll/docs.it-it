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
ms.openlocfilehash: 00b467836d8e60aeee51a010a6384abf7dd73c56
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141848"
---
# <a name="how-to-set-options-with-windows-forms-checkbox-controls"></a><span data-ttu-id="b2a00-102">Procedura: impostare opzioni con i controlli CheckBox di Windows Form</span><span class="sxs-lookup"><span data-stu-id="b2a00-102">How to: Set Options with Windows Forms CheckBox Controls</span></span>
<span data-ttu-id="b2a00-103">Un controllo <xref:System.Windows.Forms.CheckBox> Windows Form viene utilizzato per fornire agli utenti opzioni True/False o Sì/No.</span><span class="sxs-lookup"><span data-stu-id="b2a00-103">A Windows Forms <xref:System.Windows.Forms.CheckBox> control is used to give users True/False or Yes/No options.</span></span> <span data-ttu-id="b2a00-104">Il controllo visualizza un segno di spunta quando viene selezionato.</span><span class="sxs-lookup"><span data-stu-id="b2a00-104">The control displays a check mark when it is selected.</span></span>  
  
### <a name="to-set-options-with-checkbox-controls"></a><span data-ttu-id="b2a00-105">Per impostare le opzioni con i controlli CheckBox</span><span class="sxs-lookup"><span data-stu-id="b2a00-105">To set options with CheckBox controls</span></span>  
  
1. <span data-ttu-id="b2a00-106">Esaminare il <xref:System.Windows.Forms.CheckBox.Checked%2A> valore della proprietà per determinarne lo stato e utilizzare tale valore per impostare un'opzione.</span><span class="sxs-lookup"><span data-stu-id="b2a00-106">Examine the value of the <xref:System.Windows.Forms.CheckBox.Checked%2A> property to determine its state, and use that value to set an option.</span></span>  
  
     <span data-ttu-id="b2a00-107">Nell'esempio di codice <xref:System.Windows.Forms.CheckBox> riportato <xref:System.Windows.Forms.CheckBox.CheckedChanged> di seguito, quando viene <xref:System.Windows.Forms.Control.AllowDrop%2A> generato l'evento del controllo, la proprietà del form viene impostata su `false` se la casella di controllo è selezionata.</span><span class="sxs-lookup"><span data-stu-id="b2a00-107">In the code sample below, when the <xref:System.Windows.Forms.CheckBox> control's <xref:System.Windows.Forms.CheckBox.CheckedChanged> event is raised, the form's <xref:System.Windows.Forms.Control.AllowDrop%2A> property is set to `false` if the check box is checked.</span></span> <span data-ttu-id="b2a00-108">Ciò è utile per le situazioni in cui si desidera limitare l'interazione dell'utente.</span><span class="sxs-lookup"><span data-stu-id="b2a00-108">This is useful for situations where you want to restrict user interaction.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b2a00-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b2a00-109">See also</span></span>

- <xref:System.Windows.Forms.CheckBox>
- [<span data-ttu-id="b2a00-110">Panoramica del controllo CheckBox</span><span class="sxs-lookup"><span data-stu-id="b2a00-110">CheckBox Control Overview</span></span>](checkbox-control-overview-windows-forms.md)
- [<span data-ttu-id="b2a00-111">Procedura: rispondere alla selezione di controlli CheckBox Windows Form</span><span class="sxs-lookup"><span data-stu-id="b2a00-111">How to: Respond to Windows Forms CheckBox Clicks</span></span>](how-to-respond-to-windows-forms-checkbox-clicks.md)
- [<span data-ttu-id="b2a00-112">Controllo CheckBox</span><span class="sxs-lookup"><span data-stu-id="b2a00-112">CheckBox Control</span></span>](checkbox-control-windows-forms.md)
