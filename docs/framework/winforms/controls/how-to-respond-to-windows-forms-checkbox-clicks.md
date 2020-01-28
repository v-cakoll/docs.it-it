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
ms.openlocfilehash: ba2afb52939a6274978ce725dac19b5622419b99
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76735672"
---
# <a name="how-to-respond-to-windows-forms-checkbox-clicks"></a><span data-ttu-id="b6ba7-102">Procedura: Rispondere alla selezione di controlli CheckBox di Windows Form</span><span class="sxs-lookup"><span data-stu-id="b6ba7-102">How to: Respond to Windows Forms CheckBox Clicks</span></span>
<span data-ttu-id="b6ba7-103">Ogni volta che un utente fa clic su un Windows Forms <xref:System.Windows.Forms.CheckBox> controllo, si verifica l'evento <xref:System.Windows.Forms.Control.Click>.</span><span class="sxs-lookup"><span data-stu-id="b6ba7-103">Whenever a user clicks a Windows Forms <xref:System.Windows.Forms.CheckBox> control, the <xref:System.Windows.Forms.Control.Click> event occurs.</span></span> <span data-ttu-id="b6ba7-104">È possibile programmare l'applicazione in modo che esegua un'azione a seconda dello stato della casella di controllo.</span><span class="sxs-lookup"><span data-stu-id="b6ba7-104">You can program your application to perform some action depending upon the state of the check box.</span></span>  
  
### <a name="to-respond-to-checkbox-clicks"></a><span data-ttu-id="b6ba7-105">Per rispondere ai clic della casella di controllo</span><span class="sxs-lookup"><span data-stu-id="b6ba7-105">To respond to CheckBox clicks</span></span>  
  
1. <span data-ttu-id="b6ba7-106">Nel gestore dell'evento <xref:System.Windows.Forms.Control.Click> usare la proprietà <xref:System.Windows.Forms.CheckBox.Checked%2A> per determinare lo stato del controllo ed eseguire le azioni necessarie.</span><span class="sxs-lookup"><span data-stu-id="b6ba7-106">In the <xref:System.Windows.Forms.Control.Click> event handler, use the <xref:System.Windows.Forms.CheckBox.Checked%2A> property to determine the control's state, and perform any necessary action.</span></span>  
  
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
    > <span data-ttu-id="b6ba7-107">Se l'utente tenta di fare doppio clic sul controllo <xref:System.Windows.Forms.CheckBox>, ogni clic verrà elaborato separatamente. Ciò significa che il controllo <xref:System.Windows.Forms.CheckBox> non supporta l'evento di doppio clic.</span><span class="sxs-lookup"><span data-stu-id="b6ba7-107">If the user attempts to double-click the <xref:System.Windows.Forms.CheckBox> control, each click will be processed separately; that is, the <xref:System.Windows.Forms.CheckBox> control does not support the double-click event.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="b6ba7-108">Quando la proprietà <xref:System.Windows.Forms.CheckBox.AutoCheck%2A> è `true` (impostazione predefinita), la <xref:System.Windows.Forms.CheckBox> viene selezionata o cancellata automaticamente quando si fa clic su di essa.</span><span class="sxs-lookup"><span data-stu-id="b6ba7-108">When the <xref:System.Windows.Forms.CheckBox.AutoCheck%2A> property is `true` (the default), the <xref:System.Windows.Forms.CheckBox> is automatically selected or cleared when it is clicked.</span></span> <span data-ttu-id="b6ba7-109">In caso contrario, è necessario impostare manualmente la proprietà <xref:System.Windows.Forms.CheckBox.Checked%2A> quando si verifica l'evento <xref:System.Windows.Forms.Control.Click>.</span><span class="sxs-lookup"><span data-stu-id="b6ba7-109">Otherwise, you must manually set the <xref:System.Windows.Forms.CheckBox.Checked%2A> property when the <xref:System.Windows.Forms.Control.Click> event occurs.</span></span>  
  
     <span data-ttu-id="b6ba7-110">È anche possibile usare il controllo <xref:System.Windows.Forms.CheckBox> per determinare una linea di azione.</span><span class="sxs-lookup"><span data-stu-id="b6ba7-110">You can also use the <xref:System.Windows.Forms.CheckBox> control to determine a course of action.</span></span>  
  
### <a name="to-determine-a-course-of-action-when-a-check-box-is-clicked"></a><span data-ttu-id="b6ba7-111">Per determinare una linea di azione quando si fa clic su una casella di controllo</span><span class="sxs-lookup"><span data-stu-id="b6ba7-111">To determine a course of action when a check box is clicked</span></span>  
  
1. <span data-ttu-id="b6ba7-112">Utilizzare un'istruzione case per eseguire una query sul valore della proprietà <xref:System.Windows.Forms.CheckBox.CheckState%2A> per determinare una linea di azione.</span><span class="sxs-lookup"><span data-stu-id="b6ba7-112">Use a case statement to query the value of the <xref:System.Windows.Forms.CheckBox.CheckState%2A> property to determine a course of action.</span></span> <span data-ttu-id="b6ba7-113">Quando la proprietà <xref:System.Windows.Forms.CheckBox.ThreeState%2A> è impostata su `true`, la proprietà <xref:System.Windows.Forms.CheckBox.CheckState%2A> può restituire tre valori possibili, che rappresentano la casella selezionata, la casella deselezionata o un terzo stato indeterminato in cui la casella viene visualizzata con un aspetto attenuato per indicare che l'opzione non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="b6ba7-113">When the <xref:System.Windows.Forms.CheckBox.ThreeState%2A> property is set to `true`, the <xref:System.Windows.Forms.CheckBox.CheckState%2A> property may return three possible values, which represent the box being checked, the box being unchecked, or a third indeterminate state in which the box is displayed with a dimmed appearance to indicate the option is unavailable.</span></span>  
  
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
    > <span data-ttu-id="b6ba7-114">Quando la proprietà <xref:System.Windows.Forms.CheckBox.ThreeState%2A> è impostata su `true`, la proprietà <xref:System.Windows.Forms.CheckBox.Checked%2A> restituisce `true` sia per <xref:System.Windows.Forms.CheckState.Checked> che per <xref:System.Windows.Forms.CheckState.Indeterminate>.</span><span class="sxs-lookup"><span data-stu-id="b6ba7-114">When the <xref:System.Windows.Forms.CheckBox.ThreeState%2A> property is set to `true`, the <xref:System.Windows.Forms.CheckBox.Checked%2A> property returns `true` for both <xref:System.Windows.Forms.CheckState.Checked> and <xref:System.Windows.Forms.CheckState.Indeterminate>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6ba7-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b6ba7-115">See also</span></span>

- <xref:System.Windows.Forms.CheckBox>
- [<span data-ttu-id="b6ba7-116">Panoramica sul controllo CheckBox</span><span class="sxs-lookup"><span data-stu-id="b6ba7-116">CheckBox Control Overview</span></span>](checkbox-control-overview-windows-forms.md)
- [<span data-ttu-id="b6ba7-117">Procedura: Impostare opzioni con i controlli CheckBox di Windows Form</span><span class="sxs-lookup"><span data-stu-id="b6ba7-117">How to: Set Options with Windows Forms CheckBox Controls</span></span>](how-to-set-options-with-windows-forms-checkbox-controls.md)
- [<span data-ttu-id="b6ba7-118">Controllo CheckBox</span><span class="sxs-lookup"><span data-stu-id="b6ba7-118">CheckBox Control</span></span>](checkbox-control-windows-forms.md)
