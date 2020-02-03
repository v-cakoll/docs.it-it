---
title: Modificare l'aspetto del controllo LinkLabel
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- LinkLabel properties
- LinkLabel control [Windows Forms], changing appearance of links
- links [Windows Forms], changing appearance
- examples [Windows Forms], LinkLabel control
- LinkLabel control [Windows Forms], examples
ms.assetid: fdc5854f-5162-4457-8cbe-1042feb2d132
ms.openlocfilehash: 0b38722fb1647ea215c3bb8978dd3f54b300a0e0
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746625"
---
# <a name="how-to-change-the-appearance-of-the-windows-forms-linklabel-control"></a><span data-ttu-id="cef74-102">Procedura: modificare l'aspetto del controllo LinkLabel di Windows Form</span><span class="sxs-lookup"><span data-stu-id="cef74-102">How to: Change the Appearance of the Windows Forms LinkLabel Control</span></span>
<span data-ttu-id="cef74-103">È possibile modificare il testo visualizzato dal controllo <xref:System.Windows.Forms.LinkLabel> per adattarlo a diversi scopi.</span><span class="sxs-lookup"><span data-stu-id="cef74-103">You can change the text displayed by the <xref:System.Windows.Forms.LinkLabel> control to suit a variety of purposes.</span></span> <span data-ttu-id="cef74-104">Ad esempio, è pratica comune indicare all'utente che è possibile fare clic su testo impostando il testo in modo che venga visualizzato in un colore specifico con una sottolineatura.</span><span class="sxs-lookup"><span data-stu-id="cef74-104">For example, it is common practice to indicate to the user that text can be clicked by setting the text to appear in a specific color with an underline.</span></span> <span data-ttu-id="cef74-105">Dopo che l'utente fa clic sul testo, il colore diventa un colore diverso.</span><span class="sxs-lookup"><span data-stu-id="cef74-105">After the user clicks the text, the color changes to a different color.</span></span> <span data-ttu-id="cef74-106">Per controllare questo comportamento, è possibile impostare cinque proprietà diverse, ovvero le proprietà <xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A>, <xref:System.Windows.Forms.LinkLabel.LinkArea%2A>, <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>, <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>e <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A>.</span><span class="sxs-lookup"><span data-stu-id="cef74-106">To control this behavior, you can set five different properties: the <xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A>, <xref:System.Windows.Forms.LinkLabel.LinkArea%2A>, <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>, <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>, and <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> properties.</span></span>  
  
### <a name="to-change-the-appearance-of-a-linklabel-control"></a><span data-ttu-id="cef74-107">Per modificare l'aspetto di un controllo LinkLabel</span><span class="sxs-lookup"><span data-stu-id="cef74-107">To change the appearance of a LinkLabel control</span></span>  
  
1. <span data-ttu-id="cef74-108">Impostare le proprietà <xref:System.Windows.Forms.LinkLabel.LinkColor%2A> e <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A> sui colori desiderati.</span><span class="sxs-lookup"><span data-stu-id="cef74-108">Set the <xref:System.Windows.Forms.LinkLabel.LinkColor%2A> and <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A> properties to the colors you want.</span></span>  
  
     <span data-ttu-id="cef74-109">Questa operazione può essere eseguita a livello di programmazione o in fase di progettazione nella finestra **Proprietà** .</span><span class="sxs-lookup"><span data-stu-id="cef74-109">This can be done either programmatically or at design time in the **Properties** window.</span></span>  
  
    ```vb  
    ' You can set the color using decimal values for red, green, and blue  
    LinkLabel1.LinkColor = Color.FromArgb(0, 0, 255)  
    ' Or you can set the color using defined constants  
    LinkLabel1.VisitedLinkColor = Color.Purple  
    ```  
  
    ```csharp  
    // You can set the color using decimal values for red, green, and blue  
    linkLabel1.LinkColor = Color.FromArgb(0, 0, 255);  
    // Or you can set the color using defined constants  
    linkLabel1.VisitedLinkColor = Color.Purple;  
    ```  
  
    ```cpp  
    // You can set the color using decimal values for red, green, and blue  
    linkLabel1->LinkColor = Color::FromArgb(0, 0, 255);  
    // Or you can set the color using defined constants  
    linkLabel1->VisitedLinkColor = Color::Purple;  
    ```  
  
2. <span data-ttu-id="cef74-110">Impostare la proprietà <xref:System.Windows.Forms.LinkLabel.Text%2A> su una didascalia appropriata.</span><span class="sxs-lookup"><span data-stu-id="cef74-110">Set the <xref:System.Windows.Forms.LinkLabel.Text%2A> property to an appropriate caption.</span></span>  
  
     <span data-ttu-id="cef74-111">Questa operazione può essere eseguita a livello di programmazione o in fase di progettazione nella finestra **Proprietà** .</span><span class="sxs-lookup"><span data-stu-id="cef74-111">This can be done either programmatically or at design time in the **Properties** window.</span></span>  
  
    ```vb  
    LinkLabel1.Text = "Click here to see more."  
    ```  
  
    ```csharp  
    linkLabel1.Text = "Click here to see more.";  
    ```  
  
    ```cpp  
    linkLabel1->Text = "Click here to see more.";  
    ```  
  
3. <span data-ttu-id="cef74-112">Impostare la proprietà <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> per determinare quale parte della didascalia verrà indicata come collegamento.</span><span class="sxs-lookup"><span data-stu-id="cef74-112">Set the <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> property to determine which part of the caption will be indicated as a link.</span></span>  
  
     <span data-ttu-id="cef74-113">Il valore <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> è rappresentato da un <xref:System.Windows.Forms.LinkArea> contenente due numeri, la posizione iniziale del carattere e il numero di caratteri.</span><span class="sxs-lookup"><span data-stu-id="cef74-113">The <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> value is represented with a <xref:System.Windows.Forms.LinkArea> containing two numbers, the starting character position and the number of characters.</span></span> <span data-ttu-id="cef74-114">Questa operazione può essere eseguita a livello di programmazione o in fase di progettazione nella finestra **Proprietà** .</span><span class="sxs-lookup"><span data-stu-id="cef74-114">This can be done either programmatically or at design time in the **Properties** window.</span></span>  
  
    ```vb  
    LinkLabel1.LinkArea = new LinkArea(6,4)  
    ```  
  
    ```csharp  
    linkLabel1.LinkArea = new LinkArea(6,4);  
    ```  
  
    ```cpp  
    linkLabel1->LinkArea = LinkArea(6,4);  
    ```  
  
4. <span data-ttu-id="cef74-115">Impostare la proprietà <xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A> su <xref:System.Windows.Forms.LinkBehavior.AlwaysUnderline>, <xref:System.Windows.Forms.LinkBehavior.HoverUnderline>o <xref:System.Windows.Forms.LinkBehavior.NeverUnderline>.</span><span class="sxs-lookup"><span data-stu-id="cef74-115">Set the <xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A> property to <xref:System.Windows.Forms.LinkBehavior.AlwaysUnderline>, <xref:System.Windows.Forms.LinkBehavior.HoverUnderline>, or <xref:System.Windows.Forms.LinkBehavior.NeverUnderline>.</span></span>  
  
     <span data-ttu-id="cef74-116">Se è impostato su <xref:System.Windows.Forms.LinkBehavior.HoverUnderline>, la parte della didascalia determinata da <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> sarà sottolineata solo quando il puntatore viene posizionato su di esso.</span><span class="sxs-lookup"><span data-stu-id="cef74-116">If it is set to <xref:System.Windows.Forms.LinkBehavior.HoverUnderline>, the part of the caption determined by <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> will only be underlined when the pointer rests on it.</span></span>  
  
5. <span data-ttu-id="cef74-117">Nel gestore dell'evento <xref:System.Windows.Forms.LinkLabel.LinkClicked> impostare la proprietà <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> su `true`.</span><span class="sxs-lookup"><span data-stu-id="cef74-117">In the <xref:System.Windows.Forms.LinkLabel.LinkClicked> event handler, set the <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> property to `true`.</span></span>  
  
     <span data-ttu-id="cef74-118">Quando è stato visitato un collegamento, è pratica comune modificarne l'aspetto in qualche modo, in genere in base al colore.</span><span class="sxs-lookup"><span data-stu-id="cef74-118">When a link has been visited, it is common practice to change its appearance in some way, usually by color.</span></span> <span data-ttu-id="cef74-119">Il testo cambierà in base al colore specificato dalla proprietà <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>.</span><span class="sxs-lookup"><span data-stu-id="cef74-119">The text will change to the color specified by the <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A> property.</span></span>  
  
    ```vb  
    Protected Sub LinkLabel1_LinkClicked (ByVal sender As Object, _  
       ByVal e As EventArgs) Handles LinkLabel1.LinkClicked  
       ' Change the color of the link text  
       ' by setting LinkVisited to True.  
       LinkLabel1.LinkVisited = True  
       ' Then do whatever other action is appropriate  
    End Sub  
    ```  
  
    ```csharp  
    protected void LinkLabel1_LinkClicked(object sender, System.EventArgs e)  
    {  
       // Change the color of the link text by setting LinkVisited   
       // to True.  
       linkLabel1.LinkVisited = true;  
       // Then do whatever other action is appropriate  
    }  
    ```  
  
    ```cpp  
    private:  
       System::Void linkLabel1_LinkClicked(System::Object ^  sender,  
          System::Windows::Forms::LinkLabelLinkClickedEventArgs ^  e)  
       {  
          // Change the color of the link text by setting LinkVisited   
          // to True.  
          linkLabel1->LinkVisited = true;  
          // Then do whatever other action is appropriate  
       }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="cef74-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cef74-120">See also</span></span>

- <xref:System.Windows.Forms.LinkLabel.LinkArea%2A>
- <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>
- <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>
- <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A>
- [<span data-ttu-id="cef74-121">Panoramica sul controllo LinkLabel</span><span class="sxs-lookup"><span data-stu-id="cef74-121">LinkLabel Control Overview</span></span>](linklabel-control-overview-windows-forms.md)
- [<span data-ttu-id="cef74-122">Procedura: Eseguire il collegamento a un oggetto o a una pagina Web con il controllo LinkLabel di Windows Form</span><span class="sxs-lookup"><span data-stu-id="cef74-122">How to: Link to an Object or Web Page with the Windows Forms LinkLabel Control</span></span>](link-to-an-object-or-web-page-with-wf-linklabel-control.md)
- [<span data-ttu-id="cef74-123">Controllo LinkLabel</span><span class="sxs-lookup"><span data-stu-id="cef74-123">LinkLabel Control</span></span>](linklabel-control-windows-forms.md)
