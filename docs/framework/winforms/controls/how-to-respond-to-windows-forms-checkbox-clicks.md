---
title: 'Procedura: Rispondere alla selezione dei controlli CheckBox di Windows Forms'
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
ms.openlocfilehash: 7ff6b2aad9ef0775547af57f11af28839e69637c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69914976"
---
# <a name="how-to-respond-to-windows-forms-checkbox-clicks"></a><span data-ttu-id="85df1-102">Procedura: Rispondere alla selezione dei controlli CheckBox di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="85df1-102">How to: Respond to Windows Forms CheckBox Clicks</span></span>
<span data-ttu-id="85df1-103">Ogni volta che un utente fa <xref:System.Windows.Forms.CheckBox> clic su un <xref:System.Windows.Forms.Control.Click> controllo Windows Forms, si verifica l'evento.</span><span class="sxs-lookup"><span data-stu-id="85df1-103">Whenever a user clicks a Windows Forms <xref:System.Windows.Forms.CheckBox> control, the <xref:System.Windows.Forms.Control.Click> event occurs.</span></span> <span data-ttu-id="85df1-104">È possibile programmare l'applicazione in modo che esegua un'azione a seconda dello stato della casella di controllo.</span><span class="sxs-lookup"><span data-stu-id="85df1-104">You can program your application to perform some action depending upon the state of the check box.</span></span>  
  
### <a name="to-respond-to-checkbox-clicks"></a><span data-ttu-id="85df1-105">Per rispondere ai clic della casella di controllo</span><span class="sxs-lookup"><span data-stu-id="85df1-105">To respond to CheckBox clicks</span></span>  
  
1. <span data-ttu-id="85df1-106"><xref:System.Windows.Forms.CheckBox.Checked%2A> Nel gestore <xref:System.Windows.Forms.Control.Click> eventi usare la proprietà per determinare lo stato del controllo ed eseguire le azioni necessarie.</span><span class="sxs-lookup"><span data-stu-id="85df1-106">In the <xref:System.Windows.Forms.Control.Click> event handler, use the <xref:System.Windows.Forms.CheckBox.Checked%2A> property to determine the control's state, and perform any necessary action.</span></span>  
  
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
    > <span data-ttu-id="85df1-107">Se l'utente tenta di fare doppio clic sul <xref:System.Windows.Forms.CheckBox> controllo, ogni clic viene elaborato separatamente, ovvero il <xref:System.Windows.Forms.CheckBox> controllo non supporta l'evento di doppio clic.</span><span class="sxs-lookup"><span data-stu-id="85df1-107">If the user attempts to double-click the <xref:System.Windows.Forms.CheckBox> control, each click will be processed separately; that is, the <xref:System.Windows.Forms.CheckBox> control does not support the double-click event.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="85df1-108">Quando la <xref:System.Windows.Forms.CheckBox.AutoCheck%2A> proprietà è `true` (impostazione predefinita), <xref:System.Windows.Forms.CheckBox> viene selezionata o deselezionata automaticamente quando si fa clic su di essa.</span><span class="sxs-lookup"><span data-stu-id="85df1-108">When the <xref:System.Windows.Forms.CheckBox.AutoCheck%2A> property is `true` (the default), the <xref:System.Windows.Forms.CheckBox> is automatically selected or cleared when it is clicked.</span></span> <span data-ttu-id="85df1-109">In caso contrario, è necessario impostare <xref:System.Windows.Forms.CheckBox.Checked%2A> manualmente la proprietà <xref:System.Windows.Forms.Control.Click> quando si verifica l'evento.</span><span class="sxs-lookup"><span data-stu-id="85df1-109">Otherwise, you must manually set the <xref:System.Windows.Forms.CheckBox.Checked%2A> property when the <xref:System.Windows.Forms.Control.Click> event occurs.</span></span>  
  
     <span data-ttu-id="85df1-110">È anche possibile usare il <xref:System.Windows.Forms.CheckBox> controllo per determinare una linea di azione.</span><span class="sxs-lookup"><span data-stu-id="85df1-110">You can also use the <xref:System.Windows.Forms.CheckBox> control to determine a course of action.</span></span>  
  
### <a name="to-determine-a-course-of-action-when-a-check-box-is-clicked"></a><span data-ttu-id="85df1-111">Per determinare una linea di azione quando si fa clic su una casella di controllo</span><span class="sxs-lookup"><span data-stu-id="85df1-111">To determine a course of action when a check box is clicked</span></span>  
  
1. <span data-ttu-id="85df1-112">Utilizzare un'istruzione case per eseguire una query sul valore <xref:System.Windows.Forms.CheckBox.CheckState%2A> della proprietà per determinare una linea di azione.</span><span class="sxs-lookup"><span data-stu-id="85df1-112">Use a case statement to query the value of the <xref:System.Windows.Forms.CheckBox.CheckState%2A> property to determine a course of action.</span></span> <span data-ttu-id="85df1-113">Quando la <xref:System.Windows.Forms.CheckBox.ThreeState%2A> proprietà è impostata su `true`, la <xref:System.Windows.Forms.CheckBox.CheckState%2A> proprietà può restituire tre valori possibili, che rappresentano la casella selezionata, la casella deselezionata o un terzo stato indeterminato in cui la casella viene visualizzata con un oggetto grigio aspetto per indicare che l'opzione non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="85df1-113">When the <xref:System.Windows.Forms.CheckBox.ThreeState%2A> property is set to `true`, the <xref:System.Windows.Forms.CheckBox.CheckState%2A> property may return three possible values, which represent the box being checked, the box being unchecked, or a third indeterminate state in which the box is displayed with a dimmed appearance to indicate the option is unavailable.</span></span>  
  
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
    > <span data-ttu-id="85df1-114">Quando la <xref:System.Windows.Forms.CheckBox.ThreeState%2A> proprietà è impostata su `true`, la <xref:System.Windows.Forms.CheckBox.Checked%2A> proprietà restituisce `true` sia <xref:System.Windows.Forms.CheckState.Checked> per che <xref:System.Windows.Forms.CheckState.Indeterminate>per.</span><span class="sxs-lookup"><span data-stu-id="85df1-114">When the <xref:System.Windows.Forms.CheckBox.ThreeState%2A> property is set to `true`, the <xref:System.Windows.Forms.CheckBox.Checked%2A> property returns `true` for both <xref:System.Windows.Forms.CheckState.Checked> and <xref:System.Windows.Forms.CheckState.Indeterminate>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85df1-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="85df1-115">See also</span></span>

- <xref:System.Windows.Forms.CheckBox>
- [<span data-ttu-id="85df1-116">Panoramica sul controllo CheckBox</span><span class="sxs-lookup"><span data-stu-id="85df1-116">CheckBox Control Overview</span></span>](checkbox-control-overview-windows-forms.md)
- [<span data-ttu-id="85df1-117">Procedura: Impostare le opzioni con Windows Forms controlli CheckBox</span><span class="sxs-lookup"><span data-stu-id="85df1-117">How to: Set Options with Windows Forms CheckBox Controls</span></span>](how-to-set-options-with-windows-forms-checkbox-controls.md)
- [<span data-ttu-id="85df1-118">Controllo CheckBox</span><span class="sxs-lookup"><span data-stu-id="85df1-118">CheckBox Control</span></span>](checkbox-control-windows-forms.md)
