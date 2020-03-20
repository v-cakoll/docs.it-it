---
title: Rispondere ai clic sui controlli CheckBox
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Click event [Windows Forms], CheckBox control
- CheckBox control [Windows Forms], Click events
- events [Windows Forms], Click events
- double-clicks
- check boxes [Windows Forms], responding to events
ms.assetid: c39f901e-8899-43b6-aa31-939cbf7089fb
ms.openlocfilehash: 6ff20c443519446d3804b325924cb3c5cbedea97
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141926"
---
# <a name="how-to-respond-to-windows-forms-checkbox-clicks"></a><span data-ttu-id="72eba-102">Procedura: rispondere alla selezione di controlli CheckBox Windows Form</span><span class="sxs-lookup"><span data-stu-id="72eba-102">How to: Respond to Windows Forms CheckBox Clicks</span></span>
<span data-ttu-id="72eba-103">Ogni volta che un <xref:System.Windows.Forms.CheckBox> utente fa <xref:System.Windows.Forms.Control.Click> clic su un controllo Windows Form, si verifica l'evento.</span><span class="sxs-lookup"><span data-stu-id="72eba-103">Whenever a user clicks a Windows Forms <xref:System.Windows.Forms.CheckBox> control, the <xref:System.Windows.Forms.Control.Click> event occurs.</span></span> <span data-ttu-id="72eba-104">È possibile programmare l'applicazione per eseguire un'azione a seconda dello stato della casella di controllo.</span><span class="sxs-lookup"><span data-stu-id="72eba-104">You can program your application to perform some action depending upon the state of the check box.</span></span>  
  
### <a name="to-respond-to-checkbox-clicks"></a><span data-ttu-id="72eba-105">Per rispondere ai clic della casella di controllo</span><span class="sxs-lookup"><span data-stu-id="72eba-105">To respond to CheckBox clicks</span></span>  
  
1. <span data-ttu-id="72eba-106"><xref:System.Windows.Forms.Control.Click> Nel gestore eventi <xref:System.Windows.Forms.CheckBox.Checked%2A> utilizzare la proprietà per determinare lo stato del controllo ed eseguire le azioni necessarie.</span><span class="sxs-lookup"><span data-stu-id="72eba-106">In the <xref:System.Windows.Forms.Control.Click> event handler, use the <xref:System.Windows.Forms.CheckBox.Checked%2A> property to determine the control's state, and perform any necessary action.</span></span>  
  
    ```vb  
    Private Sub CheckBox1_Click(ByVal sender As Object, ByVal e As System.EventArgs) Handles CheckBox1.Click  
       ' The CheckBox control's Text property is changed each time the
       ' control is clicked, indicating a checked or unchecked state.  
       If CheckBox1.Checked = True Then  
          CheckBox1.Text = "Checked"  
       Else  
          CheckBox1.Text = "Unchecked"  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void checkBox1_Click(object sender, System.EventArgs e)  
    {  
       // The CheckBox control's Text property is changed each time the
       // control is clicked, indicating a checked or unchecked state.  
       if (checkBox1.Checked)  
       {  
          checkBox1.Text = "Checked";  
       }  
       else  
       {  
          checkBox1.Text = "Unchecked";  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void checkBox1_CheckedChanged(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          if (checkBox1->Checked)  
          {  
             checkBox1->Text = "Checked";  
          }  
          else  
          {  
             checkBox1->Text = "Unchecked";  
          }  
       }  
    ```  
  
    > [!NOTE]
    > <span data-ttu-id="72eba-107">Se l'utente tenta di <xref:System.Windows.Forms.CheckBox> fare doppio clic sul controllo, ogni clic verrà elaborato separatamente; ovvero, il <xref:System.Windows.Forms.CheckBox> controllo non supporta l'evento double-click.</span><span class="sxs-lookup"><span data-stu-id="72eba-107">If the user attempts to double-click the <xref:System.Windows.Forms.CheckBox> control, each click will be processed separately; that is, the <xref:System.Windows.Forms.CheckBox> control does not support the double-click event.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="72eba-108">Quando <xref:System.Windows.Forms.CheckBox.AutoCheck%2A> la `true` proprietà è (impostazione predefinita), <xref:System.Windows.Forms.CheckBox> viene selezionata o deselezionata automaticamente quando si fa clic su di essa.</span><span class="sxs-lookup"><span data-stu-id="72eba-108">When the <xref:System.Windows.Forms.CheckBox.AutoCheck%2A> property is `true` (the default), the <xref:System.Windows.Forms.CheckBox> is automatically selected or cleared when it is clicked.</span></span> <span data-ttu-id="72eba-109">In caso contrario, <xref:System.Windows.Forms.CheckBox.Checked%2A> è <xref:System.Windows.Forms.Control.Click> necessario impostare manualmente la proprietà quando si verifica l'evento.</span><span class="sxs-lookup"><span data-stu-id="72eba-109">Otherwise, you must manually set the <xref:System.Windows.Forms.CheckBox.Checked%2A> property when the <xref:System.Windows.Forms.Control.Click> event occurs.</span></span>  
  
     <span data-ttu-id="72eba-110">È inoltre possibile <xref:System.Windows.Forms.CheckBox> utilizzare il controllo per determinare un corso dell'azione.</span><span class="sxs-lookup"><span data-stu-id="72eba-110">You can also use the <xref:System.Windows.Forms.CheckBox> control to determine a course of action.</span></span>  
  
### <a name="to-determine-a-course-of-action-when-a-check-box-is-clicked"></a><span data-ttu-id="72eba-111">Per determinare un corso d'azione quando si fa clic su una casella di controllo</span><span class="sxs-lookup"><span data-stu-id="72eba-111">To determine a course of action when a check box is clicked</span></span>  
  
1. <span data-ttu-id="72eba-112">Utilizzare un'istruzione case per <xref:System.Windows.Forms.CheckBox.CheckState%2A> eseguire una query sul valore della proprietà per determinare un corso dell'azione.</span><span class="sxs-lookup"><span data-stu-id="72eba-112">Use a case statement to query the value of the <xref:System.Windows.Forms.CheckBox.CheckState%2A> property to determine a course of action.</span></span> <span data-ttu-id="72eba-113">Quando <xref:System.Windows.Forms.CheckBox.ThreeState%2A> la proprietà `true`è <xref:System.Windows.Forms.CheckBox.CheckState%2A> impostata su , la proprietà può restituire tre valori possibili, che rappresentano la casella selezionata, la casella deselezionata o un terzo stato indeterminato in cui la casella viene visualizzata con un aspetto in grigio per indicare che l'opzione non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="72eba-113">When the <xref:System.Windows.Forms.CheckBox.ThreeState%2A> property is set to `true`, the <xref:System.Windows.Forms.CheckBox.CheckState%2A> property may return three possible values, which represent the box being checked, the box being unchecked, or a third indeterminate state in which the box is displayed with a dimmed appearance to indicate the option is unavailable.</span></span>  
  
    ```vb  
    Private Sub CheckBox1_Click(ByVal sender As Object, ByVal e As System.EventArgs) Handles CheckBox1.Click  
       Select Case CheckBox1.CheckState  
          Case CheckState.Checked  
             ' Code for checked state.  
          Case CheckState.Unchecked  
             ' Code for unchecked state.  
          Case CheckState.Indeterminate  
             ' Code for indeterminate state.  
       End Select
    End Sub  
    ```  
  
    ```csharp  
    private void checkBox1_Click(object sender, System.EventArgs e)  
    {  
       switch(checkBox1.CheckState)  
       {  
          case CheckState.Checked:  
             // Code for checked state.  
             break;  
          case CheckState.Unchecked:  
             // Code for unchecked state.  
             break;  
          case CheckState.Indeterminate:  
             // Code for indeterminate state.  
             break;  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void checkBox1_CheckedChanged(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          switch(checkBox1->CheckState) {  
             case CheckState::Checked:  
                // Code for checked state.  
                break;  
             case CheckState::Unchecked:  
                // Code for unchecked state.  
                break;  
             case CheckState::Indeterminate:  
                // Code for indeterminate state.  
                break;  
          }  
       }  
    ```  
  
    > [!NOTE]
    > <span data-ttu-id="72eba-114">Quando <xref:System.Windows.Forms.CheckBox.ThreeState%2A> la proprietà `true`è <xref:System.Windows.Forms.CheckBox.Checked%2A> impostata `true` su <xref:System.Windows.Forms.CheckState.Checked> <xref:System.Windows.Forms.CheckState.Indeterminate>, la proprietà restituisce entrambi e .</span><span class="sxs-lookup"><span data-stu-id="72eba-114">When the <xref:System.Windows.Forms.CheckBox.ThreeState%2A> property is set to `true`, the <xref:System.Windows.Forms.CheckBox.Checked%2A> property returns `true` for both <xref:System.Windows.Forms.CheckState.Checked> and <xref:System.Windows.Forms.CheckState.Indeterminate>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72eba-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="72eba-115">See also</span></span>

- <xref:System.Windows.Forms.CheckBox>
- [<span data-ttu-id="72eba-116">Panoramica del controllo CheckBox</span><span class="sxs-lookup"><span data-stu-id="72eba-116">CheckBox Control Overview</span></span>](checkbox-control-overview-windows-forms.md)
- [<span data-ttu-id="72eba-117">Procedura: impostare opzioni con i controlli CheckBox di Windows Form</span><span class="sxs-lookup"><span data-stu-id="72eba-117">How to: Set Options with Windows Forms CheckBox Controls</span></span>](how-to-set-options-with-windows-forms-checkbox-controls.md)
- [<span data-ttu-id="72eba-118">Controllo CheckBox</span><span class="sxs-lookup"><span data-stu-id="72eba-118">CheckBox Control</span></span>](checkbox-control-windows-forms.md)
