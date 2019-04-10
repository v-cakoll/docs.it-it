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
ms.openlocfilehash: f4399d8548eff76aaa4effae6da7239cd3b0284b
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59343714"
---
# <a name="how-to-send-data-to-the-active-mdi-child"></a><span data-ttu-id="9380a-102">Procedura: Inviare dati al figlio MDI attivo</span><span class="sxs-lookup"><span data-stu-id="9380a-102">How to: Send Data to the Active MDI Child</span></span>
<span data-ttu-id="9380a-103">Spesso, all'interno del contesto di [le applicazioni di interfaccia a documenti multipli (MDI)](multiple-document-interface-mdi-applications.md), si dovrà inviare dati alla finestra figlio attivi, ad esempio quando l'utente Incolla i dati dagli Appunti in un'applicazione MDI.</span><span class="sxs-lookup"><span data-stu-id="9380a-103">Often, within the context of [Multiple-Document Interface (MDI) Applications](multiple-document-interface-mdi-applications.md), you will need to send data to the active child window, such as when the user pastes data from the Clipboard into an MDI application.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9380a-104">Per informazioni sulla verifica della finestra figlio ha lo stato attivo e inviare il contenuto negli Appunti, vedere [determinare il figlio MDI attivo](how-to-determine-the-active-mdi-child.md).</span><span class="sxs-lookup"><span data-stu-id="9380a-104">For information about verifying which child window has focus and sending its contents to the Clipboard, see [Determining the Active MDI Child](how-to-determine-the-active-mdi-child.md).</span></span>  
  
### <a name="to-send-data-to-the-active-mdi-child-window-from-the-clipboard"></a><span data-ttu-id="9380a-105">Per inviare dati alla finestra figlio MDI attiva dagli Appunti</span><span class="sxs-lookup"><span data-stu-id="9380a-105">To send data to the active MDI child window from the Clipboard</span></span>  
  
1. <span data-ttu-id="9380a-106">All'interno di un metodo, copiare il testo negli Appunti per il controllo attivo del form figlio attivo.</span><span class="sxs-lookup"><span data-stu-id="9380a-106">Within a method, copy the text on the Clipboard to the active control of the active child form.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9380a-107">Questo esempio si presuppone esista un form padre MDI (`Form1`) che dispone di uno o più finestre figlio MDI che contiene un <xref:System.Windows.Forms.RichTextBox> controllo.</span><span class="sxs-lookup"><span data-stu-id="9380a-107">This example assumes there is an MDI parent form (`Form1`) that has one or more MDI child windows containing a <xref:System.Windows.Forms.RichTextBox> control.</span></span> <span data-ttu-id="9380a-108">Per altre informazioni, vedere [creazione di form padre MDI](how-to-create-mdi-parent-forms.md).</span><span class="sxs-lookup"><span data-stu-id="9380a-108">For more information, see [Creating MDI Parent Forms](how-to-create-mdi-parent-forms.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="9380a-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9380a-109">See also</span></span>

- [<span data-ttu-id="9380a-110">Applicazioni MDI (Interfaccia a documenti multipli, Multiple-Document Interface)</span><span class="sxs-lookup"><span data-stu-id="9380a-110">Multiple-Document Interface (MDI) Applications</span></span>](multiple-document-interface-mdi-applications.md)
- [<span data-ttu-id="9380a-111">Procedura: Creare form padre MDI</span><span class="sxs-lookup"><span data-stu-id="9380a-111">How to: Create MDI Parent Forms</span></span>](how-to-create-mdi-parent-forms.md)
- [<span data-ttu-id="9380a-112">Procedura: Creare form figlio MDI</span><span class="sxs-lookup"><span data-stu-id="9380a-112">How to: Create MDI Child Forms</span></span>](how-to-create-mdi-child-forms.md)
- [<span data-ttu-id="9380a-113">Procedura: Determinare il figlio MDI attivo</span><span class="sxs-lookup"><span data-stu-id="9380a-113">How to: Determine the Active MDI Child</span></span>](how-to-determine-the-active-mdi-child.md)
- [<span data-ttu-id="9380a-114">Procedura: Disporre form figlio MDI</span><span class="sxs-lookup"><span data-stu-id="9380a-114">How to: Arrange MDI Child Forms</span></span>](how-to-arrange-mdi-child-forms.md)
