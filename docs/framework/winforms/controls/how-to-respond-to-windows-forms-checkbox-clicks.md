---
title: 'Procedura: rispondere alla selezione di controlli CheckBox Windows Form'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8f15adb84f92c9434d6835e80f08bf1d9bd500ad
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-respond-to-windows-forms-checkbox-clicks"></a><span data-ttu-id="18506-102">Procedura: rispondere alla selezione di controlli CheckBox Windows Form</span><span class="sxs-lookup"><span data-stu-id="18506-102">How to: Respond to Windows Forms CheckBox Clicks</span></span>
<span data-ttu-id="18506-103">Ogni volta che un utente fa clic su un Windows Form <xref:System.Windows.Forms.CheckBox> (controllo), il <xref:System.Windows.Forms.Control.Click> si verifica l'evento.</span><span class="sxs-lookup"><span data-stu-id="18506-103">Whenever a user clicks a Windows Forms <xref:System.Windows.Forms.CheckBox> control, the <xref:System.Windows.Forms.Control.Click> event occurs.</span></span> <span data-ttu-id="18506-104">È possibile programmare l'applicazione esegua un'azione a seconda dello stato della casella di controllo.</span><span class="sxs-lookup"><span data-stu-id="18506-104">You can program your application to perform some action depending upon the state of the check box.</span></span>  
  
### <a name="to-respond-to-checkbox-clicks"></a><span data-ttu-id="18506-105">Per rispondere alle selezioni la casella di controllo</span><span class="sxs-lookup"><span data-stu-id="18506-105">To respond to CheckBox clicks</span></span>  
  
1.  <span data-ttu-id="18506-106">Nel <xref:System.Windows.Forms.Control.Click> gestore dell'evento, utilizzare il <xref:System.Windows.Forms.CheckBox.Checked%2A> proprietà per determinare lo stato del controllo e di eseguire qualsiasi azione necessaria.</span><span class="sxs-lookup"><span data-stu-id="18506-106">In the <xref:System.Windows.Forms.Control.Click> event handler, use the <xref:System.Windows.Forms.CheckBox.Checked%2A> property to determine the control's state, and perform any necessary action.</span></span>  
  
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
    >  <span data-ttu-id="18506-107">Se l'utente tenta di fare doppio clic su di <xref:System.Windows.Forms.CheckBox> (controllo), verranno elaborati separatamente ogni clic, vale a dire, il <xref:System.Windows.Forms.CheckBox> controllo non supporta l'evento di doppio clic.</span><span class="sxs-lookup"><span data-stu-id="18506-107">If the user attempts to double-click the <xref:System.Windows.Forms.CheckBox> control, each click will be processed separately; that is, the <xref:System.Windows.Forms.CheckBox> control does not support the double-click event.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="18506-108">Quando il <xref:System.Windows.Forms.CheckBox.AutoCheck%2A> proprietà `true` (impostazione predefinita), il <xref:System.Windows.Forms.CheckBox> viene selezionato o deselezionato quando viene selezionato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="18506-108">When the <xref:System.Windows.Forms.CheckBox.AutoCheck%2A> property is `true` (the default), the <xref:System.Windows.Forms.CheckBox> is automatically selected or cleared when it is clicked.</span></span> <span data-ttu-id="18506-109">In caso contrario, è necessario impostare manualmente il <xref:System.Windows.Forms.CheckBox.Checked%2A> proprietà quando il <xref:System.Windows.Forms.Control.Click> si verifica l'evento.</span><span class="sxs-lookup"><span data-stu-id="18506-109">Otherwise, you must manually set the <xref:System.Windows.Forms.CheckBox.Checked%2A> property when the <xref:System.Windows.Forms.Control.Click> event occurs.</span></span>  
  
     <span data-ttu-id="18506-110">È inoltre possibile utilizzare il <xref:System.Windows.Forms.CheckBox> controllo per determinare le azioni da intraprendere.</span><span class="sxs-lookup"><span data-stu-id="18506-110">You can also use the <xref:System.Windows.Forms.CheckBox> control to determine a course of action.</span></span>  
  
### <a name="to-determine-a-course-of-action-when-a-check-box-is-clicked"></a><span data-ttu-id="18506-111">Per stabilire una linea di condotta quando una casella di controllo si fa clic su</span><span class="sxs-lookup"><span data-stu-id="18506-111">To determine a course of action when a check box is clicked</span></span>  
  
1.  <span data-ttu-id="18506-112">Utilizzare un'istruzione case per il valore di query di <xref:System.Windows.Forms.CheckBox.CheckState%2A> proprietà per determinare le azioni da intraprendere.</span><span class="sxs-lookup"><span data-stu-id="18506-112">Use a case statement to query the value of the <xref:System.Windows.Forms.CheckBox.CheckState%2A> property to determine a course of action.</span></span> <span data-ttu-id="18506-113">Quando il <xref:System.Windows.Forms.CheckBox.ThreeState%2A> è impostata su `true`, la <xref:System.Windows.Forms.CheckBox.CheckState%2A> proprietà può restituire tre possibili valori, che rappresentano la casella selezionata, la casella deselezionata o un terzo stato indeterminato in cui viene visualizzata con un in grigio aspetto per indicare che l'opzione è disponibile.</span><span class="sxs-lookup"><span data-stu-id="18506-113">When the <xref:System.Windows.Forms.CheckBox.ThreeState%2A> property is set to `true`, the <xref:System.Windows.Forms.CheckBox.CheckState%2A> property may return three possible values, which represent the box being checked, the box being unchecked, or a third indeterminate state in which the box is displayed with a dimmed appearance to indicate the option is unavailable.</span></span>  
  
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
    >  <span data-ttu-id="18506-114">Quando il <xref:System.Windows.Forms.CheckBox.ThreeState%2A> è impostata su `true`, <xref:System.Windows.Forms.CheckBox.Checked%2A> restituisce proprietà `true` per entrambi <xref:System.Windows.Forms.CheckState.Checked> e <xref:System.Windows.Forms.CheckState.Indeterminate>.</span><span class="sxs-lookup"><span data-stu-id="18506-114">When the <xref:System.Windows.Forms.CheckBox.ThreeState%2A> property is set to `true`, the <xref:System.Windows.Forms.CheckBox.Checked%2A> property returns `true` for both <xref:System.Windows.Forms.CheckState.Checked> and <xref:System.Windows.Forms.CheckState.Indeterminate>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18506-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="18506-115">See Also</span></span>  
 <xref:System.Windows.Forms.CheckBox>  
 [<span data-ttu-id="18506-116">Panoramica sul controllo CheckBox</span><span class="sxs-lookup"><span data-stu-id="18506-116">CheckBox Control Overview</span></span>](../../../../docs/framework/winforms/controls/checkbox-control-overview-windows-forms.md)  
 [<span data-ttu-id="18506-117">Procedura: Impostare opzioni con i controlli CheckBox di Windows Form</span><span class="sxs-lookup"><span data-stu-id="18506-117">How to: Set Options with Windows Forms CheckBox Controls</span></span>](../../../../docs/framework/winforms/controls/how-to-set-options-with-windows-forms-checkbox-controls.md)  
 [<span data-ttu-id="18506-118">Controllo CheckBox</span><span class="sxs-lookup"><span data-stu-id="18506-118">CheckBox Control</span></span>](../../../../docs/framework/winforms/controls/checkbox-control-windows-forms.md)
