---
title: 'Procedura: Determinare il figlio MDI attivo'
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
ms.openlocfilehash: 91100b37e4cae9041479b209e40034efe376df5b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69946224"
---
# <a name="how-to-determine-the-active-mdi-child"></a><span data-ttu-id="f28c0-102">Procedura: Determinare il figlio MDI attivo</span><span class="sxs-lookup"><span data-stu-id="f28c0-102">How to: Determine the Active MDI Child</span></span>
<span data-ttu-id="f28c0-103">In alcuni casi, sarà necessario fornire un comando che opera sul controllo che ha lo stato attivo sul form figlio attualmente attivo.</span><span class="sxs-lookup"><span data-stu-id="f28c0-103">On occasion, you will want to provide a command that operates on the control that has focus on the currently active child form.</span></span> <span data-ttu-id="f28c0-104">Si supponga, ad esempio, di voler copiare negli Appunti il testo selezionato dalla casella di testo del form figlio.</span><span class="sxs-lookup"><span data-stu-id="f28c0-104">For example, suppose you want to copy selected text from the child form's text box to the Clipboard.</span></span> <span data-ttu-id="f28c0-105">Si creerebbe una procedura che consente di copiare il testo selezionato negli Appunti <xref:System.Windows.Forms.Control.Click> utilizzando l'evento della voce di menu copia nel menu modifica standard.</span><span class="sxs-lookup"><span data-stu-id="f28c0-105">You would create a procedure that copies selected text to the Clipboard using the <xref:System.Windows.Forms.Control.Click> event of the Copy menu item on the standard Edit menu.</span></span>  
  
 <span data-ttu-id="f28c0-106">Poiché un'applicazione MDI può avere più istanze dello stesso form figlio, è necessario che la procedura conosca il formato da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="f28c0-106">Because an MDI application can have many instances of the same child form, the procedure needs to know which form to use.</span></span> <span data-ttu-id="f28c0-107">Per specificare il formato corretto, utilizzare la <xref:System.Windows.Forms.Form.ActiveMdiChild%2A> proprietà, che restituisce il form figlio con lo stato attivo o che è stato attivato più di recente.</span><span class="sxs-lookup"><span data-stu-id="f28c0-107">To specify the correct form, use the <xref:System.Windows.Forms.Form.ActiveMdiChild%2A> property, which returns the child form that has the focus or that was most recently active.</span></span>  
  
 <span data-ttu-id="f28c0-108">Quando si dispone di più controlli in un form, è necessario specificare anche il controllo attivo.</span><span class="sxs-lookup"><span data-stu-id="f28c0-108">When you have several controls on a form, you also need to specify which control is active.</span></span> <span data-ttu-id="f28c0-109">Analogamente <xref:System.Windows.Forms.Form.ActiveMdiChild%2A> alla proprietà, <xref:System.Windows.Forms.ContainerControl.ActiveControl%2A> la proprietà restituisce il controllo con lo stato attivo sul form figlio attivo.</span><span class="sxs-lookup"><span data-stu-id="f28c0-109">Like the <xref:System.Windows.Forms.Form.ActiveMdiChild%2A> property, the <xref:System.Windows.Forms.ContainerControl.ActiveControl%2A> property returns the control with the focus on the active child form.</span></span> <span data-ttu-id="f28c0-110">Nella procedura riportata di seguito viene illustrata una procedura di copia che può essere chiamata da un menu form figlio, da un menu nel form MDI o da un pulsante della barra degli strumenti.</span><span class="sxs-lookup"><span data-stu-id="f28c0-110">The procedure below illustrates a copy procedure that can be called from a child form menu, a menu on the MDI form, or a toolbar button.</span></span>  
  
### <a name="to-determine-the-active-mdi-child-to-copy-its-text-to-the-clipboard"></a><span data-ttu-id="f28c0-111">Per determinare il figlio MDI attivo (per copiare il testo negli Appunti)</span><span class="sxs-lookup"><span data-stu-id="f28c0-111">To determine the active MDI child (to copy its text to the Clipboard)</span></span>  
  
1. <span data-ttu-id="f28c0-112">All'interno di un metodo, copiare il testo del controllo attivo del form figlio attivo negli Appunti.</span><span class="sxs-lookup"><span data-stu-id="f28c0-112">Within a method, copy the text of the active control of the active child form to the Clipboard.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="f28c0-113">In questo esempio si presuppone che esista un form padre`Form1`MDI () con una o più finestre figlio MDI contenenti <xref:System.Windows.Forms.RichTextBox> un controllo.</span><span class="sxs-lookup"><span data-stu-id="f28c0-113">This example assumes there is an MDI parent form (`Form1`) that has one or more MDI child windows containing a <xref:System.Windows.Forms.RichTextBox> control.</span></span> <span data-ttu-id="f28c0-114">Per ulteriori informazioni, vedere [creazione di form padre MDI](how-to-create-mdi-parent-forms.md).</span><span class="sxs-lookup"><span data-stu-id="f28c0-114">For more information, see [Creating MDI Parent Forms](how-to-create-mdi-parent-forms.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f28c0-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f28c0-115">See also</span></span>

- [<span data-ttu-id="f28c0-116">Applicazioni MDI (Interfaccia a documenti multipli, Multiple-Document Interface)</span><span class="sxs-lookup"><span data-stu-id="f28c0-116">Multiple-Document Interface (MDI) Applications</span></span>](multiple-document-interface-mdi-applications.md)
- [<span data-ttu-id="f28c0-117">Procedura: Creare form padre MDI</span><span class="sxs-lookup"><span data-stu-id="f28c0-117">How to: Create MDI Parent Forms</span></span>](how-to-create-mdi-parent-forms.md)
- [<span data-ttu-id="f28c0-118">Procedura: Creare form figlio MDI</span><span class="sxs-lookup"><span data-stu-id="f28c0-118">How to: Create MDI Child Forms</span></span>](how-to-create-mdi-child-forms.md)
- [<span data-ttu-id="f28c0-119">Procedura: Invia dati al figlio MDI attivo</span><span class="sxs-lookup"><span data-stu-id="f28c0-119">How to: Send Data to the Active MDI Child</span></span>](how-to-send-data-to-the-active-mdi-child.md)
- [<span data-ttu-id="f28c0-120">Procedura: Disponi form figlio MDI</span><span class="sxs-lookup"><span data-stu-id="f28c0-120">How to: Arrange MDI Child Forms</span></span>](how-to-arrange-mdi-child-forms.md)
