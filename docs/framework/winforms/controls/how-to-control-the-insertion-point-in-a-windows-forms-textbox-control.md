---
title: 'Procedura: controllare il punto di inserimento in un controllo TextBox Windows Form'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- TextBox control [Windows Forms], insertion point
- insertion points [Windows Forms], TextBox controls
- text boxes [Windows Forms], controlling insertion point
ms.assetid: 5bee7d34-5121-429e-ab1f-d8ff67bc74c1
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5cc3dab3acafdb151cf14f81145ef47e5a6ff689
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-control-the-insertion-point-in-a-windows-forms-textbox-control"></a><span data-ttu-id="a3a6a-102">Procedura: controllare il punto di inserimento in un controllo TextBox Windows Form</span><span class="sxs-lookup"><span data-stu-id="a3a6a-102">How to: Control the Insertion Point in a Windows Forms TextBox Control</span></span>
<span data-ttu-id="a3a6a-103">Quando un Windows Form <xref:System.Windows.Forms.TextBox> controllo riceve lo stato attivo, l'inserimento del valore predefinito all'interno della casella di testo a sinistra del testo esistente.</span><span class="sxs-lookup"><span data-stu-id="a3a6a-103">When a Windows Forms <xref:System.Windows.Forms.TextBox> control first receives the focus, the default insertion within the text box is to the left of any existing text.</span></span> <span data-ttu-id="a3a6a-104">L'utente può spostare il punto di inserimento con il mouse o tastiera.</span><span class="sxs-lookup"><span data-stu-id="a3a6a-104">The user can move the insertion point with the keyboard or the mouse.</span></span> <span data-ttu-id="a3a6a-105">Se la casella di testo perde e riassume quindi lo stato attivo, il punto di inserimento sarà ovunque l'utente ultimo inserito.</span><span class="sxs-lookup"><span data-stu-id="a3a6a-105">If the text box loses and then regains the focus, the insertion point will be wherever the user last placed it.</span></span>  
  
 <span data-ttu-id="a3a6a-106">In alcuni casi, questo comportamento può essere aggiunto all'utente.</span><span class="sxs-lookup"><span data-stu-id="a3a6a-106">In some cases, this behavior can be disconcerting to the user.</span></span> <span data-ttu-id="a3a6a-107">Applicazione di elaborazione di una parola, l'utente potrebbe prevedere nuovi caratteri dopo il testo esistente.</span><span class="sxs-lookup"><span data-stu-id="a3a6a-107">In a word processing application, the user might expect new characters to appear after any existing text.</span></span> <span data-ttu-id="a3a6a-108">In un'applicazione di immissione dati, l'utente potrebbe prevedere nuovi caratteri da sostituire qualsiasi voce esistente.</span><span class="sxs-lookup"><span data-stu-id="a3a6a-108">In a data entry application, the user might expect new characters to replace any existing entry.</span></span> <span data-ttu-id="a3a6a-109">Il <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> e <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> proprietà consentono di modificare il comportamento in base alle necessità.</span><span class="sxs-lookup"><span data-stu-id="a3a6a-109">The <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> and <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> properties enable you to modify the behavior to suit your purpose.</span></span>  
  
### <a name="to-control-the-insertion-point-in-a-textbox-control"></a><span data-ttu-id="a3a6a-110">Per controllare il punto di inserimento in un controllo casella di testo</span><span class="sxs-lookup"><span data-stu-id="a3a6a-110">To control the insertion point in a TextBox control</span></span>  
  
1.  <span data-ttu-id="a3a6a-111">Impostare la proprietà <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> su un valore appropriato.</span><span class="sxs-lookup"><span data-stu-id="a3a6a-111">Set the <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> property to an appropriate value.</span></span> <span data-ttu-id="a3a6a-112">Zero posiziona il punto di inserimento immediatamente a sinistra del primo carattere.</span><span class="sxs-lookup"><span data-stu-id="a3a6a-112">Zero places the insertion point immediately to the left of the first character.</span></span>  
  
2.  <span data-ttu-id="a3a6a-113">(Facoltativo) Impostare il <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> proprietà per la lunghezza del testo che si desidera selezionare.</span><span class="sxs-lookup"><span data-stu-id="a3a6a-113">(Optional) Set the <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> property to the length of the text you want to select.</span></span>  
  
     <span data-ttu-id="a3a6a-114">Il codice seguente restituisce sempre il punto di inserimento su 0.</span><span class="sxs-lookup"><span data-stu-id="a3a6a-114">The code below always returns the insertion point to 0.</span></span> <span data-ttu-id="a3a6a-115">Il `TextBox1_Enter` gestore dell'evento deve essere associato al controllo; per ulteriori informazioni, vedere [creazione di gestori eventi in Windows Form](../../../../docs/framework/winforms/creating-event-handlers-in-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="a3a6a-115">The `TextBox1_Enter` event handler must be bound to the control; for more information, see [Creating Event Handlers in Windows Forms](../../../../docs/framework/winforms/creating-event-handlers-in-windows-forms.md).</span></span>  
  
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
  
## <a name="making-the-insertion-point-visible-by-default"></a><span data-ttu-id="a3a6a-116">Rendere visibile per impostazione predefinita il punto di inserimento</span><span class="sxs-lookup"><span data-stu-id="a3a6a-116">Making the Insertion Point Visible by Default</span></span>  
 <span data-ttu-id="a3a6a-117">Il <xref:System.Windows.Forms.TextBox> punto di inserimento è visibile per impostazione predefinita in un nuovo form solo nel <xref:System.Windows.Forms.TextBox> controllo è il primo nell'ordine di tabulazione.</span><span class="sxs-lookup"><span data-stu-id="a3a6a-117">The <xref:System.Windows.Forms.TextBox> insertion point is visible by default in a new form only if the <xref:System.Windows.Forms.TextBox> control is first in the tab order.</span></span> <span data-ttu-id="a3a6a-118">In caso contrario, il punto di inserimento viene visualizzata solo se si imposta la <xref:System.Windows.Forms.TextBox> lo stato attivo con la tastiera o il mouse.</span><span class="sxs-lookup"><span data-stu-id="a3a6a-118">Otherwise, the insertion point appears only if you give the <xref:System.Windows.Forms.TextBox> the focus with either the keyboard or the mouse.</span></span>  
  
#### <a name="to-make-the-text-box-insertion-point-visible-by-default-on-a-new-form"></a><span data-ttu-id="a3a6a-119">Per rendere visibile punto di inserimento della casella di testo per impostazione predefinita in un nuovo form</span><span class="sxs-lookup"><span data-stu-id="a3a6a-119">To make the text box insertion point visible by default on a new form</span></span>  
  
-   <span data-ttu-id="a3a6a-120">Impostare il <xref:System.Windows.Forms.TextBox> del controllo <xref:System.Windows.Forms.Control.TabIndex%2A> proprietà `0`.</span><span class="sxs-lookup"><span data-stu-id="a3a6a-120">Set the <xref:System.Windows.Forms.TextBox> control's <xref:System.Windows.Forms.Control.TabIndex%2A> property to `0`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3a6a-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a3a6a-121">See Also</span></span>  
 <xref:System.Windows.Forms.TextBox>  
 [<span data-ttu-id="a3a6a-122">Cenni preliminari sul controllo TextBox</span><span class="sxs-lookup"><span data-stu-id="a3a6a-122">TextBox Control Overview</span></span>](../../../../docs/framework/winforms/controls/textbox-control-overview-windows-forms.md)  
 [<span data-ttu-id="a3a6a-123">Procedura: Creare una casella di testo Password con il controllo TextBox di Windows Form</span><span class="sxs-lookup"><span data-stu-id="a3a6a-123">How to: Create a Password Text Box with the Windows Forms TextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)  
 [<span data-ttu-id="a3a6a-124">Procedura: Creare una casella di testo in sola lettura</span><span class="sxs-lookup"><span data-stu-id="a3a6a-124">How to: Create a Read-Only Text Box</span></span>](../../../../docs/framework/winforms/controls/how-to-create-a-read-only-text-box-windows-forms.md)  
 [<span data-ttu-id="a3a6a-125">Procedura: Inserire virgolette in una stringa</span><span class="sxs-lookup"><span data-stu-id="a3a6a-125">How to: Put Quotation Marks in a String</span></span>](../../../../docs/framework/winforms/controls/how-to-put-quotation-marks-in-a-string-windows-forms.md)  
 [<span data-ttu-id="a3a6a-126">Procedura: Selezionare testo nel controllo TextBox di Windows Form</span><span class="sxs-lookup"><span data-stu-id="a3a6a-126">How to: Select Text in the Windows Forms TextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-select-text-in-the-windows-forms-textbox-control.md)  
 [<span data-ttu-id="a3a6a-127">Procedura: Visualizzare più righe nel controllo TextBox di Windows Form</span><span class="sxs-lookup"><span data-stu-id="a3a6a-127">How to: View Multiple Lines in the Windows Forms TextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)  
 [<span data-ttu-id="a3a6a-128">Controllo TextBox</span><span class="sxs-lookup"><span data-stu-id="a3a6a-128">TextBox Control</span></span>](../../../../docs/framework/winforms/controls/textbox-control-windows-forms.md)
