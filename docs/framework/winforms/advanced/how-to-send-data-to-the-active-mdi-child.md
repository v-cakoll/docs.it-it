---
title: 'Procedura: Inviare dati al figlio MDI attivo'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- child forms
- MDI [Windows Forms], sending data to forms
- Clipboard [Windows Forms], pasting
- Clipboard [Windows Forms], getting data from
ms.assetid: 1047d2fe-1235-46db-aad9-563aea1d743b
ms.openlocfilehash: dab72d64cdd013125ae7c302ccf297ecdc0c98b3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54589934"
---
# <a name="how-to-send-data-to-the-active-mdi-child"></a>Procedura: Inviare dati al figlio MDI attivo
Spesso, all'interno del contesto di [le applicazioni di interfaccia a documenti multipli (MDI)](../../../../docs/framework/winforms/advanced/multiple-document-interface-mdi-applications.md), si dovrà inviare dati alla finestra figlio attivi, ad esempio quando l'utente Incolla i dati dagli Appunti in un'applicazione MDI.  
  
> [!NOTE]
>  Per informazioni sulla verifica della finestra figlio ha lo stato attivo e inviare il contenuto negli Appunti, vedere [determinare il figlio MDI attivo](../../../../docs/framework/winforms/advanced/how-to-determine-the-active-mdi-child.md).  
  
### <a name="to-send-data-to-the-active-mdi-child-window-from-the-clipboard"></a>Per inviare dati alla finestra figlio MDI attiva dagli Appunti  
  
1.  All'interno di un metodo, copiare il testo negli Appunti per il controllo attivo del form figlio attivo.  
  
    > [!NOTE]
    >  Questo esempio si presuppone esista un form padre MDI (`Form1`) che dispone di uno o più finestre figlio MDI che contiene un <xref:System.Windows.Forms.RichTextBox> controllo. Per altre informazioni, vedere [creazione di form padre MDI](../../../../docs/framework/winforms/advanced/how-to-create-mdi-parent-forms.md).  
  
    ```vb  
    Public Sub mniPaste_Click(ByVal sender As Object, _  
       ByVal e As System.EventArgs) Handles mniPaste.Click  
  
       ' Determine the active child form.  
       Dim activeChild As Form = Me.ParentForm.ActiveMDIChild  
  
       ' If there is an active child form, find the active control, which  
       ' in this example should be a RichTextBox.  
       If (Not activeChild Is Nothing) Then  
          Try  
             Dim theBox As RichTextBox = Ctype(activeChild.ActiveControl, RichTextBox)  
             If (Not theBox Is Nothing) Then  
                ' Create a new instance of the DataObject interface.  
                Dim data As IDataObject = Clipboard.GetDataObject()  
                ' If the data is text, then set the text of the   
                ' RichTextBox to the text in the clipboard.  
                If (data.GetDataPresent(DataFormats.Text)) Then  
                   theBox.SelectedText = data.GetData(DataFormats.Text).ToString()  
                End If  
             End If  
          Catch  
             MessageBox.Show("You need to select a RichTextBox.")  
          End Try  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    protected void mniPaste_Click (object sender, System.EventArgs e)  
    {  
      // Determine the active child form.  
       Form activeChild = this.ParentForm.ActiveMdiChild;  
  
       // If there is an active child form, find the active control, which  
       // in this example should be a RichTextBox.  
       if (activeChild != null)  
       {  
          try   
          {  
             RichTextBox theBox = (RichTextBox)activeChild.ActiveControl;  
             if (theBox != null)  
             {  
                // Create a new instance of the DataObject interface.  
                IDataObject data = Clipboard.GetDataObject();  
                // If the data is text, then set the text of the   
                // RichTextBox to the text in the clipboard.  
                if (data.GetDataPresent(DataFormats.Text))  
                {  
                   theBox.SelectedText = data.GetData(DataFormats.Text).ToString();                 
                }  
             }  
          }  
          catch   
          {  
             MessageBox.Show("You need to select a RichTextBox.");  
          }  
       }  
    }  
    ```  
  
## <a name="see-also"></a>Vedere anche
- [Applicazioni MDI (Interfaccia a documenti multipli, Multiple-Document Interface)](../../../../docs/framework/winforms/advanced/multiple-document-interface-mdi-applications.md)
- [Procedura: Creare form padre MDI](../../../../docs/framework/winforms/advanced/how-to-create-mdi-parent-forms.md)
- [Procedura: Creare form figlio MDI](../../../../docs/framework/winforms/advanced/how-to-create-mdi-child-forms.md)
- [Procedura: Determinare il figlio MDI attivo](../../../../docs/framework/winforms/advanced/how-to-determine-the-active-mdi-child.md)
- [Procedura: Disporre i form figlio MDI](../../../../docs/framework/winforms/advanced/how-to-arrange-mdi-child-forms.md)
