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
# <a name="how-to-respond-to-windows-forms-checkbox-clicks"></a>Procedura: rispondere alla selezione di controlli CheckBox Windows Form
Ogni volta che un <xref:System.Windows.Forms.CheckBox> utente fa <xref:System.Windows.Forms.Control.Click> clic su un controllo Windows Form, si verifica l'evento. È possibile programmare l'applicazione per eseguire un'azione a seconda dello stato della casella di controllo.  
  
### <a name="to-respond-to-checkbox-clicks"></a>Per rispondere ai clic della casella di controllo  
  
1. <xref:System.Windows.Forms.Control.Click> Nel gestore eventi <xref:System.Windows.Forms.CheckBox.Checked%2A> utilizzare la proprietà per determinare lo stato del controllo ed eseguire le azioni necessarie.  
  
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
    > Se l'utente tenta di <xref:System.Windows.Forms.CheckBox> fare doppio clic sul controllo, ogni clic verrà elaborato separatamente; ovvero, il <xref:System.Windows.Forms.CheckBox> controllo non supporta l'evento double-click.  
  
    > [!NOTE]
    > Quando <xref:System.Windows.Forms.CheckBox.AutoCheck%2A> la `true` proprietà è (impostazione predefinita), <xref:System.Windows.Forms.CheckBox> viene selezionata o deselezionata automaticamente quando si fa clic su di essa. In caso contrario, <xref:System.Windows.Forms.CheckBox.Checked%2A> è <xref:System.Windows.Forms.Control.Click> necessario impostare manualmente la proprietà quando si verifica l'evento.  
  
     È inoltre possibile <xref:System.Windows.Forms.CheckBox> utilizzare il controllo per determinare un corso dell'azione.  
  
### <a name="to-determine-a-course-of-action-when-a-check-box-is-clicked"></a>Per determinare un corso d'azione quando si fa clic su una casella di controllo  
  
1. Utilizzare un'istruzione case per <xref:System.Windows.Forms.CheckBox.CheckState%2A> eseguire una query sul valore della proprietà per determinare un corso dell'azione. Quando <xref:System.Windows.Forms.CheckBox.ThreeState%2A> la proprietà `true`è <xref:System.Windows.Forms.CheckBox.CheckState%2A> impostata su , la proprietà può restituire tre valori possibili, che rappresentano la casella selezionata, la casella deselezionata o un terzo stato indeterminato in cui la casella viene visualizzata con un aspetto in grigio per indicare che l'opzione non è disponibile.  
  
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
    > Quando <xref:System.Windows.Forms.CheckBox.ThreeState%2A> la proprietà `true`è <xref:System.Windows.Forms.CheckBox.Checked%2A> impostata `true` su <xref:System.Windows.Forms.CheckState.Checked> <xref:System.Windows.Forms.CheckState.Indeterminate>, la proprietà restituisce entrambi e .  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.CheckBox>
- [Panoramica del controllo CheckBox](checkbox-control-overview-windows-forms.md)
- [Procedura: impostare opzioni con i controlli CheckBox di Windows Form](how-to-set-options-with-windows-forms-checkbox-controls.md)
- [Controllo CheckBox](checkbox-control-windows-forms.md)
