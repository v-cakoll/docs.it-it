---
title: Modifica dell'aspetto del controllo LinkLabel
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
ms.openlocfilehash: df66991289373a05fc7c27b7768a96643e3bbae0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79142130"
---
# <a name="how-to-change-the-appearance-of-the-windows-forms-linklabel-control"></a><span data-ttu-id="d2add-102">Procedura: modificare l'aspetto del controllo LinkLabel di Windows Form</span><span class="sxs-lookup"><span data-stu-id="d2add-102">How to: Change the Appearance of the Windows Forms LinkLabel Control</span></span>
<span data-ttu-id="d2add-103">È possibile modificare il testo <xref:System.Windows.Forms.LinkLabel> visualizzato dal controllo in base a diversi scopi.</span><span class="sxs-lookup"><span data-stu-id="d2add-103">You can change the text displayed by the <xref:System.Windows.Forms.LinkLabel> control to suit a variety of purposes.</span></span> <span data-ttu-id="d2add-104">Ad esempio, è pratica comune indicare all'utente che è possibile fare clic sul testo impostando il testo in modo che venga visualizzato in un colore specifico con una sottolineatura.</span><span class="sxs-lookup"><span data-stu-id="d2add-104">For example, it is common practice to indicate to the user that text can be clicked by setting the text to appear in a specific color with an underline.</span></span> <span data-ttu-id="d2add-105">Dopo che l'utente fa clic sul testo, il colore assume un colore diverso.</span><span class="sxs-lookup"><span data-stu-id="d2add-105">After the user clicks the text, the color changes to a different color.</span></span> <span data-ttu-id="d2add-106">Per controllare questo comportamento, è possibile <xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A>impostare cinque proprietà diverse: le proprietà , <xref:System.Windows.Forms.LinkLabel.LinkArea%2A>, <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>, <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>e <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> .</span><span class="sxs-lookup"><span data-stu-id="d2add-106">To control this behavior, you can set five different properties: the <xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A>, <xref:System.Windows.Forms.LinkLabel.LinkArea%2A>, <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>, <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>, and <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> properties.</span></span>  
  
### <a name="to-change-the-appearance-of-a-linklabel-control"></a><span data-ttu-id="d2add-107">Per modificare l'aspetto di un controllo LinkLabel</span><span class="sxs-lookup"><span data-stu-id="d2add-107">To change the appearance of a LinkLabel control</span></span>  
  
1. <span data-ttu-id="d2add-108">Impostare <xref:System.Windows.Forms.LinkLabel.LinkColor%2A> <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A> le proprietà e per i colori desiderati.</span><span class="sxs-lookup"><span data-stu-id="d2add-108">Set the <xref:System.Windows.Forms.LinkLabel.LinkColor%2A> and <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A> properties to the colors you want.</span></span>  
  
     <span data-ttu-id="d2add-109">Questa operazione può essere eseguita a livello di codice o in fase di progettazione nel **proprietà** finestra.</span><span class="sxs-lookup"><span data-stu-id="d2add-109">This can be done either programmatically or at design time in the **Properties** window.</span></span>  
  
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
  
2. <span data-ttu-id="d2add-110">Impostare <xref:System.Windows.Forms.LinkLabel.Text%2A> la proprietà su una didascalia appropriata.</span><span class="sxs-lookup"><span data-stu-id="d2add-110">Set the <xref:System.Windows.Forms.LinkLabel.Text%2A> property to an appropriate caption.</span></span>  
  
     <span data-ttu-id="d2add-111">Questa operazione può essere eseguita a livello di codice o in fase di progettazione nel **proprietà** finestra.</span><span class="sxs-lookup"><span data-stu-id="d2add-111">This can be done either programmatically or at design time in the **Properties** window.</span></span>  
  
    ```vb  
    LinkLabel1.Text = "Click here to see more."  
    ```  
  
    ```csharp  
    linkLabel1.Text = "Click here to see more.";  
    ```  
  
    ```cpp  
    linkLabel1->Text = "Click here to see more.";  
    ```  
  
3. <span data-ttu-id="d2add-112">Impostare <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> la proprietà per determinare quale parte della didascalia verrà indicata come collegamento.</span><span class="sxs-lookup"><span data-stu-id="d2add-112">Set the <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> property to determine which part of the caption will be indicated as a link.</span></span>  
  
     <span data-ttu-id="d2add-113">Il <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> valore è <xref:System.Windows.Forms.LinkArea> rappresentato da un contenente due numeri, la posizione del carattere iniziale e il numero di caratteri.</span><span class="sxs-lookup"><span data-stu-id="d2add-113">The <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> value is represented with a <xref:System.Windows.Forms.LinkArea> containing two numbers, the starting character position and the number of characters.</span></span> <span data-ttu-id="d2add-114">Questa operazione può essere eseguita a livello di codice o in fase di progettazione nel **proprietà** finestra.</span><span class="sxs-lookup"><span data-stu-id="d2add-114">This can be done either programmatically or at design time in the **Properties** window.</span></span>  
  
    ```vb  
    LinkLabel1.LinkArea = new LinkArea(6,4)  
    ```  
  
    ```csharp  
    linkLabel1.LinkArea = new LinkArea(6,4);  
    ```  
  
    ```cpp  
    linkLabel1->LinkArea = LinkArea(6,4);  
    ```  
  
4. <span data-ttu-id="d2add-115">Impostare <xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A> la <xref:System.Windows.Forms.LinkBehavior.AlwaysUnderline> <xref:System.Windows.Forms.LinkBehavior.HoverUnderline>proprietà <xref:System.Windows.Forms.LinkBehavior.NeverUnderline>su , , o .</span><span class="sxs-lookup"><span data-stu-id="d2add-115">Set the <xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A> property to <xref:System.Windows.Forms.LinkBehavior.AlwaysUnderline>, <xref:System.Windows.Forms.LinkBehavior.HoverUnderline>, or <xref:System.Windows.Forms.LinkBehavior.NeverUnderline>.</span></span>  
  
     <span data-ttu-id="d2add-116">Se è impostata su <xref:System.Windows.Forms.LinkBehavior.HoverUnderline>, la <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> parte della didascalia determinata da verrà sottolineata solo quando il puntatore viene posizionato su di essa.</span><span class="sxs-lookup"><span data-stu-id="d2add-116">If it is set to <xref:System.Windows.Forms.LinkBehavior.HoverUnderline>, the part of the caption determined by <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> will only be underlined when the pointer rests on it.</span></span>  
  
5. <span data-ttu-id="d2add-117"><xref:System.Windows.Forms.LinkLabel.LinkClicked> Nel gestore eventi impostare la proprietà su <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> `true`.</span><span class="sxs-lookup"><span data-stu-id="d2add-117">In the <xref:System.Windows.Forms.LinkLabel.LinkClicked> event handler, set the <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> property to `true`.</span></span>  
  
     <span data-ttu-id="d2add-118">Quando un link è stato visitato, è pratica comune cambiare il suo aspetto in qualche modo, di solito per colore.</span><span class="sxs-lookup"><span data-stu-id="d2add-118">When a link has been visited, it is common practice to change its appearance in some way, usually by color.</span></span> <span data-ttu-id="d2add-119">Il testo cambierà nel colore <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A> specificato dalla proprietà .</span><span class="sxs-lookup"><span data-stu-id="d2add-119">The text will change to the color specified by the <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A> property.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d2add-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d2add-120">See also</span></span>

- <xref:System.Windows.Forms.LinkLabel.LinkArea%2A>
- <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>
- <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>
- <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A>
- [<span data-ttu-id="d2add-121">Panoramica del controllo LinkLabel</span><span class="sxs-lookup"><span data-stu-id="d2add-121">LinkLabel Control Overview</span></span>](linklabel-control-overview-windows-forms.md)
- [<span data-ttu-id="d2add-122">Procedura: eseguire il collegamento a un oggetto o a una pagina Web con il controllo LinkLabel di Windows Form</span><span class="sxs-lookup"><span data-stu-id="d2add-122">How to: Link to an Object or Web Page with the Windows Forms LinkLabel Control</span></span>](link-to-an-object-or-web-page-with-wf-linklabel-control.md)
- [<span data-ttu-id="d2add-123">Controllo LinkLabel</span><span class="sxs-lookup"><span data-stu-id="d2add-123">LinkLabel Control</span></span>](linklabel-control-windows-forms.md)
