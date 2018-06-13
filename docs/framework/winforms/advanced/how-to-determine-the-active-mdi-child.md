---
title: 'Procedura: determinare il figlio MDI attivo'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Clipboard [Windows Forms], copying data to
- MDI [Windows Forms], child windows
- child forms
- MDI [Windows Forms], activating forms
- MDI [Windows Forms], locating focus
ms.assetid: 33880ec3-0207-4c2b-a616-ff140443cc0f
ms.openlocfilehash: 0b084d204361764af1b36b154acfc5b360fc977e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33521718"
---
# <a name="how-to-determine-the-active-mdi-child"></a>Procedura: determinare il figlio MDI attivo
In alcuni casi, è necessario fornire un comando che viene eseguito sul controllo che ha lo stato attivo del form figlio attivo. Si supponga, ad esempio, che si desidera copiare negli Appunti il testo selezionato dalla casella di testo del form figlio. È necessario creare una routine che copia il testo selezionato negli Appunti mediante il <xref:System.Windows.Forms.Control.Click> evento della voce di menu copia dal menu di modifica standard.  
  
 Poiché un'applicazione MDI può avere molte istanze dello stesso form figlio, la procedura deve conoscere il modulo da utilizzare. Per specificare il formato corretto, utilizzare il <xref:System.Windows.Forms.Form.ActiveMdiChild%2A> proprietà, che restituisce il form figlio che ha lo stato attivo o che è stata attiva più di recente.  
  
 Quando si dispone di più controlli in un form, è inoltre necessario specificare quale controllo è attivo. Ad esempio il <xref:System.Windows.Forms.Form.ActiveMdiChild%2A> proprietà, il <xref:System.Windows.Forms.ContainerControl.ActiveControl%2A> proprietà restituisce il controllo con lo stato attivo sul form figlio attivo. La procedura seguente illustra una procedura di copia che può essere chiamata da un menu di form figlio, un menu del form MDI o un pulsante della barra degli strumenti.  
  
### <a name="to-determine-the-active-mdi-child-to-copy-its-text-to-the-clipboard"></a>Per determinare il figlio MDI attivo (per copiare il testo negli Appunti)  
  
1.  All'interno di un metodo, copiare il testo del controllo attivo del form figlio attivo negli Appunti.  
  
    > [!NOTE]
    >  Questo esempio si presuppone un form padre MDI è (`Form1`) che dispone di uno o più finestre figlio MDI contenente un <xref:System.Windows.Forms.RichTextBox> controllo. Per ulteriori informazioni, vedere [creazione di form padre MDI](../../../../docs/framework/winforms/advanced/how-to-create-mdi-parent-forms.md).  
  
    ```vb  
    Public Sub mniCopy_Click(ByVal sender As Object, _  
       ByVal e As System.EventArgs) Handles mniCopy.Click  
  
       ' Determine the active child form.  
       Dim activeChild As Form = Me.ActiveMDIChild  
  
       ' If there is an active child form, find the active control, which  
       ' in this example should be a RichTextBox.  
       If (Not activeChild Is Nothing) Then  
          Dim theBox As RichTextBox = _  
            TryCast(activeChild.ActiveControl, RichTextBox)  
  
          If (Not theBox Is Nothing) Then  
             'Put selected text on Clipboard.  
             Clipboard.SetDataObject(theBox.SelectedText)  
          Else  
             MessageBox.Show("You need to select a RichTextBox.")  
          End If  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    protected void mniCopy_Click (object sender, System.EventArgs e)  
    {  
       // Determine the active child form.  
       Form activeChild = this.ActiveMdiChild;  
  
       // If there is an active child form, find the active control, which  
       // in this example should be a RichTextBox.  
       if (activeChild != null)  
       {    
          try  
          {  
             RichTextBox theBox = (RichTextBox)activeChild.ActiveControl;  
             if (theBox != null)  
             {  
                // Put the selected text on the Clipboard.  
                Clipboard.SetDataObject(theBox.SelectedText);  
  
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
 [Applicazioni MDI (Interfaccia a documenti multipli, Multiple-Document Interface)](../../../../docs/framework/winforms/advanced/multiple-document-interface-mdi-applications.md)  
 [Procedura: Creare form padre MDI](../../../../docs/framework/winforms/advanced/how-to-create-mdi-parent-forms.md)  
 [Procedura: Creare form figlio MDI](../../../../docs/framework/winforms/advanced/how-to-create-mdi-child-forms.md)  
 [Procedura: Inviare dati al figlio MDI attivo](../../../../docs/framework/winforms/advanced/how-to-send-data-to-the-active-mdi-child.md)  
 [Procedura: Disporre i form figlio MDI](../../../../docs/framework/winforms/advanced/how-to-arrange-mdi-child-forms.md)
