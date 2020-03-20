---
title: 'Procedura: inviare dati al figlio MDI attivo'
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
ms.openlocfilehash: 563be8494cb84dc74b45985d3ba74e4b6a07eb8a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182487"
---
# <a name="how-to-send-data-to-the-active-mdi-child"></a><span data-ttu-id="867fc-102">Procedura: inviare dati al figlio MDI attivo</span><span class="sxs-lookup"><span data-stu-id="867fc-102">How to: Send Data to the Active MDI Child</span></span>
<span data-ttu-id="867fc-103">Spesso, nel contesto delle applicazioni [MDI (Multiple-Document Interface),](multiple-document-interface-mdi-applications.md)sarà necessario inviare dati alla finestra figlio attiva, ad esempio quando l'utente incolla i dati dagli Appunti in un'applicazione MDI.</span><span class="sxs-lookup"><span data-stu-id="867fc-103">Often, within the context of [Multiple-Document Interface (MDI) Applications](multiple-document-interface-mdi-applications.md), you will need to send data to the active child window, such as when the user pastes data from the Clipboard into an MDI application.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="867fc-104">Per informazioni sulla verifica della finestra figlio con lo stato attivo e sull'invio del relativo contenuto agli Appunti, vedere [Determinazione del figlio MDI attivo.](how-to-determine-the-active-mdi-child.md)</span><span class="sxs-lookup"><span data-stu-id="867fc-104">For information about verifying which child window has focus and sending its contents to the Clipboard, see [Determining the Active MDI Child](how-to-determine-the-active-mdi-child.md).</span></span>  
  
### <a name="to-send-data-to-the-active-mdi-child-window-from-the-clipboard"></a><span data-ttu-id="867fc-105">Per inviare dati alla finestra figlio MDI attiva dagli Appunti</span><span class="sxs-lookup"><span data-stu-id="867fc-105">To send data to the active MDI child window from the Clipboard</span></span>  
  
1. <span data-ttu-id="867fc-106">All'interno di un metodo, copiare il testo negli Appunti nel controllo attivo del form figlio attivo.</span><span class="sxs-lookup"><span data-stu-id="867fc-106">Within a method, copy the text on the Clipboard to the active control of the active child form.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="867fc-107">In questo esempio si presuppone che`Form1`sia presente un form padre MDI <xref:System.Windows.Forms.RichTextBox> ( ) con una o più finestre figlio MDI contenenti un controllo .</span><span class="sxs-lookup"><span data-stu-id="867fc-107">This example assumes there is an MDI parent form (`Form1`) that has one or more MDI child windows containing a <xref:System.Windows.Forms.RichTextBox> control.</span></span> <span data-ttu-id="867fc-108">Per ulteriori informazioni, vedere [Creazione di form padre MDI](how-to-create-mdi-parent-forms.md).</span><span class="sxs-lookup"><span data-stu-id="867fc-108">For more information, see [Creating MDI Parent Forms](how-to-create-mdi-parent-forms.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="867fc-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="867fc-109">See also</span></span>

- [<span data-ttu-id="867fc-110">Applicazioni MDI (Interfaccia a documenti multipli, Multiple-Document Interface)</span><span class="sxs-lookup"><span data-stu-id="867fc-110">Multiple-Document Interface (MDI) Applications</span></span>](multiple-document-interface-mdi-applications.md)
- [<span data-ttu-id="867fc-111">Procedura: Creare form padre MDI</span><span class="sxs-lookup"><span data-stu-id="867fc-111">How to: Create MDI Parent Forms</span></span>](how-to-create-mdi-parent-forms.md)
- [<span data-ttu-id="867fc-112">Procedura: creare form figlio MDI</span><span class="sxs-lookup"><span data-stu-id="867fc-112">How to: Create MDI Child Forms</span></span>](how-to-create-mdi-child-forms.md)
- [<span data-ttu-id="867fc-113">Procedura: determinare il figlio MDI attivo</span><span class="sxs-lookup"><span data-stu-id="867fc-113">How to: Determine the Active MDI Child</span></span>](how-to-determine-the-active-mdi-child.md)
- [<span data-ttu-id="867fc-114">Procedura: Disporre i form figlio MDI</span><span class="sxs-lookup"><span data-stu-id="867fc-114">How to: Arrange MDI Child Forms</span></span>](how-to-arrange-mdi-child-forms.md)
