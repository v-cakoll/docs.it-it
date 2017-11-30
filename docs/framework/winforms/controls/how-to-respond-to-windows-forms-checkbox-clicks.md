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
# <a name="how-to-respond-to-windows-forms-checkbox-clicks"></a>Procedura: rispondere alla selezione di controlli CheckBox Windows Form
Ogni volta che un utente fa clic su un Windows Form <xref:System.Windows.Forms.CheckBox> (controllo), il <xref:System.Windows.Forms.Control.Click> si verifica l'evento. È possibile programmare l'applicazione esegua un'azione a seconda dello stato della casella di controllo.  
  
### <a name="to-respond-to-checkbox-clicks"></a>Per rispondere alle selezioni la casella di controllo  
  
1.  Nel <xref:System.Windows.Forms.Control.Click> gestore dell'evento, utilizzare il <xref:System.Windows.Forms.CheckBox.Checked%2A> proprietà per determinare lo stato del controllo e di eseguire qualsiasi azione necessaria.  
  
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
    >  Se l'utente tenta di fare doppio clic su di <xref:System.Windows.Forms.CheckBox> (controllo), verranno elaborati separatamente ogni clic, vale a dire, il <xref:System.Windows.Forms.CheckBox> controllo non supporta l'evento di doppio clic.  
  
    > [!NOTE]
    >  Quando il <xref:System.Windows.Forms.CheckBox.AutoCheck%2A> proprietà `true` (impostazione predefinita), il <xref:System.Windows.Forms.CheckBox> viene selezionato o deselezionato quando viene selezionato automaticamente. In caso contrario, è necessario impostare manualmente il <xref:System.Windows.Forms.CheckBox.Checked%2A> proprietà quando il <xref:System.Windows.Forms.Control.Click> si verifica l'evento.  
  
     È inoltre possibile utilizzare il <xref:System.Windows.Forms.CheckBox> controllo per determinare le azioni da intraprendere.  
  
### <a name="to-determine-a-course-of-action-when-a-check-box-is-clicked"></a>Per stabilire una linea di condotta quando una casella di controllo si fa clic su  
  
1.  Utilizzare un'istruzione case per il valore di query di <xref:System.Windows.Forms.CheckBox.CheckState%2A> proprietà per determinare le azioni da intraprendere. Quando il <xref:System.Windows.Forms.CheckBox.ThreeState%2A> è impostata su `true`, la <xref:System.Windows.Forms.CheckBox.CheckState%2A> proprietà può restituire tre possibili valori, che rappresentano la casella selezionata, la casella deselezionata o un terzo stato indeterminato in cui viene visualizzata con un in grigio aspetto per indicare che l'opzione è disponibile.  
  
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
    >  Quando il <xref:System.Windows.Forms.CheckBox.ThreeState%2A> è impostata su `true`, <xref:System.Windows.Forms.CheckBox.Checked%2A> restituisce proprietà `true` per entrambi <xref:System.Windows.Forms.CheckState.Checked> e <xref:System.Windows.Forms.CheckState.Indeterminate>.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.CheckBox>  
 [Panoramica sul controllo CheckBox](../../../../docs/framework/winforms/controls/checkbox-control-overview-windows-forms.md)  
 [Procedura: Impostare opzioni con i controlli CheckBox di Windows Form](../../../../docs/framework/winforms/controls/how-to-set-options-with-windows-forms-checkbox-controls.md)  
 [Controllo CheckBox](../../../../docs/framework/winforms/controls/checkbox-control-windows-forms.md)
