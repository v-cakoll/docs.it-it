---
title: Controllare il punto di inserimento nel controllo TextBox
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- TextBox control [Windows Forms], insertion point
- insertion points [Windows Forms], TextBox controls
- text boxes [Windows Forms], controlling insertion point
ms.assetid: 5bee7d34-5121-429e-ab1f-d8ff67bc74c1
ms.openlocfilehash: fd4803820921f0c922a4ce885f809abee8fd4c6c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742208"
---
# <a name="how-to-control-the-insertion-point-in-a-windows-forms-textbox-control"></a><span data-ttu-id="15f32-102">Procedura: controllare il punto di inserimento in un controllo TextBox Windows Form</span><span class="sxs-lookup"><span data-stu-id="15f32-102">How to: Control the Insertion Point in a Windows Forms TextBox Control</span></span>
<span data-ttu-id="15f32-103">Quando un Windows Forms controllo <xref:System.Windows.Forms.TextBox> prima riceve lo stato attivo, l'inserimento predefinito all'interno della casella di testo si trova a sinistra di qualsiasi testo esistente.</span><span class="sxs-lookup"><span data-stu-id="15f32-103">When a Windows Forms <xref:System.Windows.Forms.TextBox> control first receives the focus, the default insertion within the text box is to the left of any existing text.</span></span> <span data-ttu-id="15f32-104">L'utente può spostare il punto di inserimento con la tastiera o con il mouse.</span><span class="sxs-lookup"><span data-stu-id="15f32-104">The user can move the insertion point with the keyboard or the mouse.</span></span> <span data-ttu-id="15f32-105">Se la casella di testo perde e quindi riacquisisce lo stato attivo, il punto di inserimento sarà ogni volta che l'utente lo posiziona.</span><span class="sxs-lookup"><span data-stu-id="15f32-105">If the text box loses and then regains the focus, the insertion point will be wherever the user last placed it.</span></span>  
  
 <span data-ttu-id="15f32-106">In alcuni casi, questo comportamento può essere sconcertante per l'utente.</span><span class="sxs-lookup"><span data-stu-id="15f32-106">In some cases, this behavior can be disconcerting to the user.</span></span> <span data-ttu-id="15f32-107">In un'applicazione di elaborazione di testo, l'utente potrebbe aspettarsi che vengano visualizzati nuovi caratteri dopo un testo esistente.</span><span class="sxs-lookup"><span data-stu-id="15f32-107">In a word processing application, the user might expect new characters to appear after any existing text.</span></span> <span data-ttu-id="15f32-108">In un'applicazione di immissione dati, l'utente può prevedere che i nuovi caratteri sostituiscano qualsiasi voce esistente.</span><span class="sxs-lookup"><span data-stu-id="15f32-108">In a data entry application, the user might expect new characters to replace any existing entry.</span></span> <span data-ttu-id="15f32-109">Le proprietà <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> e <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> consentono di modificare il comportamento in base ai propri scopi.</span><span class="sxs-lookup"><span data-stu-id="15f32-109">The <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> and <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> properties enable you to modify the behavior to suit your purpose.</span></span>  
  
### <a name="to-control-the-insertion-point-in-a-textbox-control"></a><span data-ttu-id="15f32-110">Per controllare il punto di inserimento in un controllo TextBox</span><span class="sxs-lookup"><span data-stu-id="15f32-110">To control the insertion point in a TextBox control</span></span>  
  
1. <span data-ttu-id="15f32-111">Impostare la proprietà <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> su un valore appropriato.</span><span class="sxs-lookup"><span data-stu-id="15f32-111">Set the <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> property to an appropriate value.</span></span> <span data-ttu-id="15f32-112">Zero posiziona il punto di inserimento immediatamente a sinistra del primo carattere.</span><span class="sxs-lookup"><span data-stu-id="15f32-112">Zero places the insertion point immediately to the left of the first character.</span></span>  
  
2. <span data-ttu-id="15f32-113">Opzionale Impostare la proprietà <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> sulla lunghezza del testo che si desidera selezionare.</span><span class="sxs-lookup"><span data-stu-id="15f32-113">(Optional) Set the <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> property to the length of the text you want to select.</span></span>  
  
     <span data-ttu-id="15f32-114">Il codice seguente restituisce sempre il punto di inserimento a 0.</span><span class="sxs-lookup"><span data-stu-id="15f32-114">The code below always returns the insertion point to 0.</span></span> <span data-ttu-id="15f32-115">Il gestore dell'evento `TextBox1_Enter` deve essere associato al controllo; Per ulteriori informazioni, vedere [creazione di gestori eventi in Windows Forms](../creating-event-handlers-in-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="15f32-115">The `TextBox1_Enter` event handler must be bound to the control; for more information, see [Creating Event Handlers in Windows Forms](../creating-event-handlers-in-windows-forms.md).</span></span>  
  
    ```vb  
    Private Sub TextBox1_Enter(ByVal sender As Object, ByVal e As System.EventArgs) Handles TextBox1.Enter  
       TextBox1.SelectionStart = 0  
       TextBox1.SelectionLength = 0  
    End Sub  
    ```  
  
    ```csharp  
    private void textBox1_Enter(Object sender, System.EventArgs e) {  
       textBox1.SelectionStart = 0;  
       textBox1.SelectionLength = 0;  
    }  
    ```  
  
    ```cpp  
    private:  
       void textBox1_Enter(System::Object ^  sender,  
          System::EventArgs ^  e)  
       {  
          textBox1->SelectionStart = 0;  
          textBox1->SelectionLength = 0;  
       }  
    ```  
  
## <a name="making-the-insertion-point-visible-by-default"></a><span data-ttu-id="15f32-116">Rendere visibile il punto di inserimento per impostazione predefinita</span><span class="sxs-lookup"><span data-stu-id="15f32-116">Making the Insertion Point Visible by Default</span></span>  
 <span data-ttu-id="15f32-117">Il punto di inserimento <xref:System.Windows.Forms.TextBox> è visibile per impostazione predefinita in un nuovo form solo se il controllo <xref:System.Windows.Forms.TextBox> è primo nell'ordine di tabulazione.</span><span class="sxs-lookup"><span data-stu-id="15f32-117">The <xref:System.Windows.Forms.TextBox> insertion point is visible by default in a new form only if the <xref:System.Windows.Forms.TextBox> control is first in the tab order.</span></span> <span data-ttu-id="15f32-118">In caso contrario, il punto di inserimento viene visualizzato solo se si assegna al <xref:System.Windows.Forms.TextBox> lo stato attivo con la tastiera o con il mouse.</span><span class="sxs-lookup"><span data-stu-id="15f32-118">Otherwise, the insertion point appears only if you give the <xref:System.Windows.Forms.TextBox> the focus with either the keyboard or the mouse.</span></span>  
  
#### <a name="to-make-the-text-box-insertion-point-visible-by-default-on-a-new-form"></a><span data-ttu-id="15f32-119">Per rendere visibile il punto di inserimento della casella di testo per impostazione predefinita in un nuovo form</span><span class="sxs-lookup"><span data-stu-id="15f32-119">To make the text box insertion point visible by default on a new form</span></span>  
  
- <span data-ttu-id="15f32-120">Impostare la proprietà <xref:System.Windows.Forms.Control.TabIndex%2A> del controllo <xref:System.Windows.Forms.TextBox> su `0`.</span><span class="sxs-lookup"><span data-stu-id="15f32-120">Set the <xref:System.Windows.Forms.TextBox> control's <xref:System.Windows.Forms.Control.TabIndex%2A> property to `0`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15f32-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="15f32-121">See also</span></span>

- <xref:System.Windows.Forms.TextBox>
- [<span data-ttu-id="15f32-122">Cenni preliminari sul controllo TextBox</span><span class="sxs-lookup"><span data-stu-id="15f32-122">TextBox Control Overview</span></span>](textbox-control-overview-windows-forms.md)
- [<span data-ttu-id="15f32-123">Procedura: Creare una casella di testo Password con il controllo TextBox di Windows Form</span><span class="sxs-lookup"><span data-stu-id="15f32-123">How to: Create a Password Text Box with the Windows Forms TextBox Control</span></span>](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="15f32-124">Procedura: Creare una casella di testo in sola lettura</span><span class="sxs-lookup"><span data-stu-id="15f32-124">How to: Create a Read-Only Text Box</span></span>](how-to-create-a-read-only-text-box-windows-forms.md)
- [<span data-ttu-id="15f32-125">Procedura: Inserire virgolette in una stringa</span><span class="sxs-lookup"><span data-stu-id="15f32-125">How to: Put Quotation Marks in a String</span></span>](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [<span data-ttu-id="15f32-126">Procedura: Selezionare testo nel controllo TextBox di Windows Form</span><span class="sxs-lookup"><span data-stu-id="15f32-126">How to: Select Text in the Windows Forms TextBox Control</span></span>](how-to-select-text-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="15f32-127">Procedura: Visualizzare più righe nel controllo TextBox di Windows Form</span><span class="sxs-lookup"><span data-stu-id="15f32-127">How to: View Multiple Lines in the Windows Forms TextBox Control</span></span>](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="15f32-128">Controllo TextBox</span><span class="sxs-lookup"><span data-stu-id="15f32-128">TextBox Control</span></span>](textbox-control-windows-forms.md)
