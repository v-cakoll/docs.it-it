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
# <a name="how-to-respond-to-windows-forms-checkbox-clicks"></a>Procedura: Rispondere alla selezione di controlli CheckBox di Windows Form
Ogni volta che un utente fa clic su un Windows Forms <xref:System.Windows.Forms.CheckBox> controllo, si verifica l'evento <xref:System.Windows.Forms.Control.Click>. È possibile programmare l'applicazione in modo che esegua un'azione a seconda dello stato della casella di controllo.  
  
### <a name="to-respond-to-checkbox-clicks"></a>Per rispondere ai clic della casella di controllo  
  
1. Nel gestore dell'evento <xref:System.Windows.Forms.Control.Click> usare la proprietà <xref:System.Windows.Forms.CheckBox.Checked%2A> per determinare lo stato del controllo ed eseguire le azioni necessarie.  
  
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
    > Se l'utente tenta di fare doppio clic sul controllo <xref:System.Windows.Forms.CheckBox>, ogni clic verrà elaborato separatamente. Ciò significa che il controllo <xref:System.Windows.Forms.CheckBox> non supporta l'evento di doppio clic.  
  
    > [!NOTE]
    > Quando la proprietà <xref:System.Windows.Forms.CheckBox.AutoCheck%2A> è `true` (impostazione predefinita), la <xref:System.Windows.Forms.CheckBox> viene selezionata o cancellata automaticamente quando si fa clic su di essa. In caso contrario, è necessario impostare manualmente la proprietà <xref:System.Windows.Forms.CheckBox.Checked%2A> quando si verifica l'evento <xref:System.Windows.Forms.Control.Click>.  
  
     È anche possibile usare il controllo <xref:System.Windows.Forms.CheckBox> per determinare una linea di azione.  
  
### <a name="to-determine-a-course-of-action-when-a-check-box-is-clicked"></a>Per determinare una linea di azione quando si fa clic su una casella di controllo  
  
1. Utilizzare un'istruzione case per eseguire una query sul valore della proprietà <xref:System.Windows.Forms.CheckBox.CheckState%2A> per determinare una linea di azione. Quando la proprietà <xref:System.Windows.Forms.CheckBox.ThreeState%2A> è impostata su `true`, la proprietà <xref:System.Windows.Forms.CheckBox.CheckState%2A> può restituire tre valori possibili, che rappresentano la casella selezionata, la casella deselezionata o un terzo stato indeterminato in cui la casella viene visualizzata con un aspetto attenuato per indicare che l'opzione non è disponibile.  
  
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
    > Quando la proprietà <xref:System.Windows.Forms.CheckBox.ThreeState%2A> è impostata su `true`, la proprietà <xref:System.Windows.Forms.CheckBox.Checked%2A> restituisce `true` sia per <xref:System.Windows.Forms.CheckState.Checked> che per <xref:System.Windows.Forms.CheckState.Indeterminate>.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.CheckBox>
- [Panoramica sul controllo CheckBox](checkbox-control-overview-windows-forms.md)
- [Procedura: Impostare opzioni con i controlli CheckBox di Windows Form](how-to-set-options-with-windows-forms-checkbox-controls.md)
- [Controllo CheckBox](checkbox-control-windows-forms.md)
