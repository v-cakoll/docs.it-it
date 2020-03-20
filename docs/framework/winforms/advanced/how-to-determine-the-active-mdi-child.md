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
ms.openlocfilehash: 57491faa10c182630d41565ba236d65e393929b3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182540"
---
# <a name="how-to-determine-the-active-mdi-child"></a><span data-ttu-id="14ba8-102">Procedura: determinare il figlio MDI attivo</span><span class="sxs-lookup"><span data-stu-id="14ba8-102">How to: Determine the Active MDI Child</span></span>
<span data-ttu-id="14ba8-103">In alcuni casi, è necessario fornire un comando che opera sul controllo che ha lo stato attivo sul form figlio attualmente attivo.</span><span class="sxs-lookup"><span data-stu-id="14ba8-103">On occasion, you will want to provide a command that operates on the control that has focus on the currently active child form.</span></span> <span data-ttu-id="14ba8-104">Si supponga, ad esempio, di voler copiare negli Appunti il testo selezionato dalla casella di testo del form figlio.</span><span class="sxs-lookup"><span data-stu-id="14ba8-104">For example, suppose you want to copy selected text from the child form's text box to the Clipboard.</span></span> <span data-ttu-id="14ba8-105">È possibile creare una routine che copia il <xref:System.Windows.Forms.Control.Click> testo selezionato negli Appunti utilizzando l'evento della voce di menu Copia del menu Modifica standard.</span><span class="sxs-lookup"><span data-stu-id="14ba8-105">You would create a procedure that copies selected text to the Clipboard using the <xref:System.Windows.Forms.Control.Click> event of the Copy menu item on the standard Edit menu.</span></span>  
  
 <span data-ttu-id="14ba8-106">Poiché un'applicazione MDI può avere molte istanze dello stesso form figlio, la procedura deve sapere quale form utilizzare.</span><span class="sxs-lookup"><span data-stu-id="14ba8-106">Because an MDI application can have many instances of the same child form, the procedure needs to know which form to use.</span></span> <span data-ttu-id="14ba8-107">Per specificare il form <xref:System.Windows.Forms.Form.ActiveMdiChild%2A> corretto, utilizzare la proprietà , che restituisce il form figlio con lo stato attivo o attivo più di recente.</span><span class="sxs-lookup"><span data-stu-id="14ba8-107">To specify the correct form, use the <xref:System.Windows.Forms.Form.ActiveMdiChild%2A> property, which returns the child form that has the focus or that was most recently active.</span></span>  
  
 <span data-ttu-id="14ba8-108">Quando in un form sono presenti più controlli, è necessario specificare anche quale controllo è attivo.</span><span class="sxs-lookup"><span data-stu-id="14ba8-108">When you have several controls on a form, you also need to specify which control is active.</span></span> <span data-ttu-id="14ba8-109">Come <xref:System.Windows.Forms.Form.ActiveMdiChild%2A> la proprietà, la <xref:System.Windows.Forms.ContainerControl.ActiveControl%2A> proprietà restituisce il controllo con lo stato attivo sul form figlio attivo.</span><span class="sxs-lookup"><span data-stu-id="14ba8-109">Like the <xref:System.Windows.Forms.Form.ActiveMdiChild%2A> property, the <xref:System.Windows.Forms.ContainerControl.ActiveControl%2A> property returns the control with the focus on the active child form.</span></span> <span data-ttu-id="14ba8-110">Nella procedura riportata di seguito viene illustrata una procedura di copia che può essere chiamata da un menu del form figlio, da un menu del form MDI o da un pulsante della barra degli strumenti.</span><span class="sxs-lookup"><span data-stu-id="14ba8-110">The procedure below illustrates a copy procedure that can be called from a child form menu, a menu on the MDI form, or a toolbar button.</span></span>  
  
### <a name="to-determine-the-active-mdi-child-to-copy-its-text-to-the-clipboard"></a><span data-ttu-id="14ba8-111">Per determinare l'elemento figlio MDI attivo (per copiarne il testo negli Appunti)</span><span class="sxs-lookup"><span data-stu-id="14ba8-111">To determine the active MDI child (to copy its text to the Clipboard)</span></span>  
  
1. <span data-ttu-id="14ba8-112">All'interno di un metodo, copiare il testo del controllo attivo del form figlio attivo negli Appunti.</span><span class="sxs-lookup"><span data-stu-id="14ba8-112">Within a method, copy the text of the active control of the active child form to the Clipboard.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="14ba8-113">In questo esempio si presuppone che`Form1`sia presente un form padre MDI <xref:System.Windows.Forms.RichTextBox> ( ) con una o più finestre figlio MDI contenenti un controllo .</span><span class="sxs-lookup"><span data-stu-id="14ba8-113">This example assumes there is an MDI parent form (`Form1`) that has one or more MDI child windows containing a <xref:System.Windows.Forms.RichTextBox> control.</span></span> <span data-ttu-id="14ba8-114">Per ulteriori informazioni, vedere [Creazione di form padre MDI](how-to-create-mdi-parent-forms.md).</span><span class="sxs-lookup"><span data-stu-id="14ba8-114">For more information, see [Creating MDI Parent Forms](how-to-create-mdi-parent-forms.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="14ba8-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="14ba8-115">See also</span></span>

- [<span data-ttu-id="14ba8-116">Applicazioni MDI (Interfaccia a documenti multipli, Multiple-Document Interface)</span><span class="sxs-lookup"><span data-stu-id="14ba8-116">Multiple-Document Interface (MDI) Applications</span></span>](multiple-document-interface-mdi-applications.md)
- [<span data-ttu-id="14ba8-117">Procedura: Creare form padre MDI</span><span class="sxs-lookup"><span data-stu-id="14ba8-117">How to: Create MDI Parent Forms</span></span>](how-to-create-mdi-parent-forms.md)
- [<span data-ttu-id="14ba8-118">Procedura: creare form figlio MDI</span><span class="sxs-lookup"><span data-stu-id="14ba8-118">How to: Create MDI Child Forms</span></span>](how-to-create-mdi-child-forms.md)
- [<span data-ttu-id="14ba8-119">Procedura: inviare dati al figlio MDI attivo</span><span class="sxs-lookup"><span data-stu-id="14ba8-119">How to: Send Data to the Active MDI Child</span></span>](how-to-send-data-to-the-active-mdi-child.md)
- [<span data-ttu-id="14ba8-120">Procedura: Disporre i form figlio MDI</span><span class="sxs-lookup"><span data-stu-id="14ba8-120">How to: Arrange MDI Child Forms</span></span>](how-to-arrange-mdi-child-forms.md)
