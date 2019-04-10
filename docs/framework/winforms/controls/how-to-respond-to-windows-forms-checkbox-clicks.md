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
ms.openlocfilehash: ce616f45ceaa3db117c6981d2987ac09bba7b3fb
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59319898"
---
# <a name="how-to-respond-to-windows-forms-checkbox-clicks"></a>Procedura: Rispondere alla selezione dei controlli CheckBox di Windows Forms
Ogni volta che un utente fa clic su un controllo Windows Form <xref:System.Windows.Forms.CheckBox> (controllo), il <xref:System.Windows.Forms.Control.Click> evento si verifica. È possibile programmare l'applicazione per eseguire un'azione a seconda dello stato della casella di controllo.  
  
### <a name="to-respond-to-checkbox-clicks"></a>Per rispondere alle selezioni la casella di controllo  
  
1. Nel <xref:System.Windows.Forms.Control.Click> gestore eventi, usare il <xref:System.Windows.Forms.CheckBox.Checked%2A> proprietà per determinare lo stato del controllo ed eseguire tutte le azioni necessarie.  
  
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
    >  Se l'utente tenta di fare doppio clic il <xref:System.Windows.Forms.CheckBox> (controllo), a ogni clic verranno elaborate separatamente, vale a dire, il <xref:System.Windows.Forms.CheckBox> controllo non supporta l'evento doppio clic.  
  
    > [!NOTE]
    >  Quando la <xref:System.Windows.Forms.CheckBox.AutoCheck%2A> proprietà è `true` (impostazione predefinita), il <xref:System.Windows.Forms.CheckBox> selezionata o deselezionata quando viene selezionato automaticamente. In caso contrario, è necessario impostare manualmente le <xref:System.Windows.Forms.CheckBox.Checked%2A> proprietà quando il <xref:System.Windows.Forms.Control.Click> evento si verifica.  
  
     È anche possibile usare il <xref:System.Windows.Forms.CheckBox> controllo per determinare le azioni da intraprendere.  
  
### <a name="to-determine-a-course-of-action-when-a-check-box-is-clicked"></a>Per stabilire una linea di condotta quando una casella di controllo si fa clic su  
  
1. Usare un'istruzione case per il valore di query di <xref:System.Windows.Forms.CheckBox.CheckState%2A> proprietà per determinare le azioni da intraprendere. Quando la <xref:System.Windows.Forms.CheckBox.ThreeState%2A> è impostata su `true`, il <xref:System.Windows.Forms.CheckBox.CheckState%2A> proprietà può restituire tre possibili valori, che rappresentano la casella selezionata, la casella è deselezionata, o un terzo stato indeterminato in cui viene visualizzata la finestra con un grigio aspetto per indicare che l'opzione non è disponibile.  
  
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
    >  Quando la <xref:System.Windows.Forms.CheckBox.ThreeState%2A> è impostata su `true`, il <xref:System.Windows.Forms.CheckBox.Checked%2A> restituisce proprietà `true` per entrambi <xref:System.Windows.Forms.CheckState.Checked> e <xref:System.Windows.Forms.CheckState.Indeterminate>.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.CheckBox>
- [Panoramica del controllo CheckBox](checkbox-control-overview-windows-forms.md)
- [Procedura: Impostare opzioni con i controlli CheckBox di Windows Forms](how-to-set-options-with-windows-forms-checkbox-controls.md)
- [Controllo CheckBox](checkbox-control-windows-forms.md)
