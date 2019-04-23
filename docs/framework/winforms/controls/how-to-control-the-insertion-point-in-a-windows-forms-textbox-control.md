---
title: 'Procedura: Controllare il punto di inserimento in un controllo TextBox di Windows Forms'
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
ms.openlocfilehash: 43fdb023f19aa988dfef3dcd68443d6f59808472
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59341322"
---
# <a name="how-to-control-the-insertion-point-in-a-windows-forms-textbox-control"></a><span data-ttu-id="f27f9-102">Procedura: Controllare il punto di inserimento in un controllo TextBox di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f27f9-102">How to: Control the Insertion Point in a Windows Forms TextBox Control</span></span>
<span data-ttu-id="f27f9-103">Quando un controllo Windows Form <xref:System.Windows.Forms.TextBox> controllo riceve lo stato attivo, l'inserimento dell'impostazione predefinita all'interno della casella di testo è a sinistra del testo esistente.</span><span class="sxs-lookup"><span data-stu-id="f27f9-103">When a Windows Forms <xref:System.Windows.Forms.TextBox> control first receives the focus, the default insertion within the text box is to the left of any existing text.</span></span> <span data-ttu-id="f27f9-104">L'utente può spostare il punto di inserimento con il mouse o tastiera.</span><span class="sxs-lookup"><span data-stu-id="f27f9-104">The user can move the insertion point with the keyboard or the mouse.</span></span> <span data-ttu-id="f27f9-105">Se la casella di testo perde e riacquisisce quindi lo stato attivo, il punto di inserimento sarà ovunque l'utente ultima posizione assegnata.</span><span class="sxs-lookup"><span data-stu-id="f27f9-105">If the text box loses and then regains the focus, the insertion point will be wherever the user last placed it.</span></span>  
  
 <span data-ttu-id="f27f9-106">In alcuni casi, questo comportamento può essere aggiunto all'utente.</span><span class="sxs-lookup"><span data-stu-id="f27f9-106">In some cases, this behavior can be disconcerting to the user.</span></span> <span data-ttu-id="f27f9-107">Applicazione di elaborazione di una parola, l'utente potrebbe prevedere caratteri di nuova visualizzazione dopo il testo esistente.</span><span class="sxs-lookup"><span data-stu-id="f27f9-107">In a word processing application, the user might expect new characters to appear after any existing text.</span></span> <span data-ttu-id="f27f9-108">In un'applicazione di immissione dati, l'utente potrebbe prevedere nuovi caratteri da sostituire qualsiasi voce esistente.</span><span class="sxs-lookup"><span data-stu-id="f27f9-108">In a data entry application, the user might expect new characters to replace any existing entry.</span></span> <span data-ttu-id="f27f9-109">Il <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> e <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> proprietà consentono di modificare il comportamento di un determinato scopo.</span><span class="sxs-lookup"><span data-stu-id="f27f9-109">The <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> and <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> properties enable you to modify the behavior to suit your purpose.</span></span>  
  
### <a name="to-control-the-insertion-point-in-a-textbox-control"></a><span data-ttu-id="f27f9-110">Per controllare il punto di inserimento in un controllo TextBox</span><span class="sxs-lookup"><span data-stu-id="f27f9-110">To control the insertion point in a TextBox control</span></span>  
  
1. <span data-ttu-id="f27f9-111">Impostare la proprietà <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> su un valore appropriato.</span><span class="sxs-lookup"><span data-stu-id="f27f9-111">Set the <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> property to an appropriate value.</span></span> <span data-ttu-id="f27f9-112">Zero inserisce il punto di inserimento immediatamente a sinistra del primo carattere.</span><span class="sxs-lookup"><span data-stu-id="f27f9-112">Zero places the insertion point immediately to the left of the first character.</span></span>  
  
2. <span data-ttu-id="f27f9-113">(Facoltativo) Impostare il <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> proprietà per la lunghezza del testo che si desidera selezionare.</span><span class="sxs-lookup"><span data-stu-id="f27f9-113">(Optional) Set the <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> property to the length of the text you want to select.</span></span>  
  
     <span data-ttu-id="f27f9-114">Il codice seguente restituisce sempre il punto di inserimento su 0.</span><span class="sxs-lookup"><span data-stu-id="f27f9-114">The code below always returns the insertion point to 0.</span></span> <span data-ttu-id="f27f9-115">Il `TextBox1_Enter` gestore dell'evento deve essere associato al controllo; per altre informazioni, vedere [creazione di gestori di eventi in Windows Form](../creating-event-handlers-in-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="f27f9-115">The `TextBox1_Enter` event handler must be bound to the control; for more information, see [Creating Event Handlers in Windows Forms](../creating-event-handlers-in-windows-forms.md).</span></span>  
  
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
  
## <a name="making-the-insertion-point-visible-by-default"></a><span data-ttu-id="f27f9-116">Rendere visibile per impostazione predefinita il punto di inserimento</span><span class="sxs-lookup"><span data-stu-id="f27f9-116">Making the Insertion Point Visible by Default</span></span>  
 <span data-ttu-id="f27f9-117">Il <xref:System.Windows.Forms.TextBox> punto di inserimento è visibile per impostazione predefinita in un nuovo form solo nel <xref:System.Windows.Forms.TextBox> controllo è il primo nell'ordine di tabulazione.</span><span class="sxs-lookup"><span data-stu-id="f27f9-117">The <xref:System.Windows.Forms.TextBox> insertion point is visible by default in a new form only if the <xref:System.Windows.Forms.TextBox> control is first in the tab order.</span></span> <span data-ttu-id="f27f9-118">In caso contrario, il punto di inserimento viene visualizzata solo se si assegna il <xref:System.Windows.Forms.TextBox> lo stato attivo con la tastiera o con il mouse.</span><span class="sxs-lookup"><span data-stu-id="f27f9-118">Otherwise, the insertion point appears only if you give the <xref:System.Windows.Forms.TextBox> the focus with either the keyboard or the mouse.</span></span>  
  
#### <a name="to-make-the-text-box-insertion-point-visible-by-default-on-a-new-form"></a><span data-ttu-id="f27f9-119">Per rendere visibile punto di inserimento della casella di testo per impostazione predefinita in un nuovo modulo</span><span class="sxs-lookup"><span data-stu-id="f27f9-119">To make the text box insertion point visible by default on a new form</span></span>  
  
-   <span data-ttu-id="f27f9-120">Impostare il <xref:System.Windows.Forms.TextBox> del controllo <xref:System.Windows.Forms.Control.TabIndex%2A> proprietà `0`.</span><span class="sxs-lookup"><span data-stu-id="f27f9-120">Set the <xref:System.Windows.Forms.TextBox> control's <xref:System.Windows.Forms.Control.TabIndex%2A> property to `0`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f27f9-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f27f9-121">See also</span></span>

- <xref:System.Windows.Forms.TextBox>
- [<span data-ttu-id="f27f9-122">Cenni preliminari sul controllo TextBox</span><span class="sxs-lookup"><span data-stu-id="f27f9-122">TextBox Control Overview</span></span>](textbox-control-overview-windows-forms.md)
- [<span data-ttu-id="f27f9-123">Procedura: Creare una casella di testo Password con il controllo TextBox di Windows Form</span><span class="sxs-lookup"><span data-stu-id="f27f9-123">How to: Create a Password Text Box with the Windows Forms TextBox Control</span></span>](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="f27f9-124">Procedura: Creare una casella di testo di sola lettura</span><span class="sxs-lookup"><span data-stu-id="f27f9-124">How to: Create a Read-Only Text Box</span></span>](how-to-create-a-read-only-text-box-windows-forms.md)
- [<span data-ttu-id="f27f9-125">Procedura: Inserire virgolette in una stringa</span><span class="sxs-lookup"><span data-stu-id="f27f9-125">How to: Put Quotation Marks in a String</span></span>](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [<span data-ttu-id="f27f9-126">Procedura: Selezionare il testo nel controllo TextBox Windows Form</span><span class="sxs-lookup"><span data-stu-id="f27f9-126">How to: Select Text in the Windows Forms TextBox Control</span></span>](how-to-select-text-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="f27f9-127">Procedura: Visualizzare più righe nel controllo TextBox Windows Form</span><span class="sxs-lookup"><span data-stu-id="f27f9-127">How to: View Multiple Lines in the Windows Forms TextBox Control</span></span>](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="f27f9-128">Controllo TextBox</span><span class="sxs-lookup"><span data-stu-id="f27f9-128">TextBox Control</span></span>](textbox-control-windows-forms.md)
