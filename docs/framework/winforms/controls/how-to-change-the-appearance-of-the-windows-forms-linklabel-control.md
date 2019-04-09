---
title: "Procedura: Modificare l'aspetto del controllo LinkLabel di Windows Forms"
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
ms.openlocfilehash: be2f6e8e10d9f9b23b4f57fa696f1fb88c4726c0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59105027"
---
# <a name="how-to-change-the-appearance-of-the-windows-forms-linklabel-control"></a><span data-ttu-id="fede8-102">Procedura: Modificare l'aspetto del controllo LinkLabel di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="fede8-102">How to: Change the Appearance of the Windows Forms LinkLabel Control</span></span>
<span data-ttu-id="fede8-103">È possibile modificare il testo visualizzato dal <xref:System.Windows.Forms.LinkLabel> controllo in base alle diverse esigenze.</span><span class="sxs-lookup"><span data-stu-id="fede8-103">You can change the text displayed by the <xref:System.Windows.Forms.LinkLabel> control to suit a variety of purposes.</span></span> <span data-ttu-id="fede8-104">Ad esempio, è pratica comune per indicare all'utente che è possibile fare clic sul testo, impostare il testo da visualizzare in un colore specifico con un carattere di sottolineatura.</span><span class="sxs-lookup"><span data-stu-id="fede8-104">For example, it is common practice to indicate to the user that text can be clicked by setting the text to appear in a specific color with an underline.</span></span> <span data-ttu-id="fede8-105">L'utente seleziona il testo, cambia il colore in un colore diverso.</span><span class="sxs-lookup"><span data-stu-id="fede8-105">After the user clicks the text, the color changes to a different color.</span></span> <span data-ttu-id="fede8-106">Per controllare questo comportamento, è possibile impostare diverse cinque proprietà: il <xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A>, <xref:System.Windows.Forms.LinkLabel.LinkArea%2A>, <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>, <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>, e <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="fede8-106">To control this behavior, you can set five different properties: the <xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A>, <xref:System.Windows.Forms.LinkLabel.LinkArea%2A>, <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>, <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>, and <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> properties.</span></span>  
  
### <a name="to-change-the-appearance-of-a-linklabel-control"></a><span data-ttu-id="fede8-107">Per modificare l'aspetto di un controllo LinkLabel</span><span class="sxs-lookup"><span data-stu-id="fede8-107">To change the appearance of a LinkLabel control</span></span>  
  
1.  <span data-ttu-id="fede8-108">Impostare il <xref:System.Windows.Forms.LinkLabel.LinkColor%2A> e <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A> proprietà per i colori desiderati.</span><span class="sxs-lookup"><span data-stu-id="fede8-108">Set the <xref:System.Windows.Forms.LinkLabel.LinkColor%2A> and <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A> properties to the colors you want.</span></span>  
  
     <span data-ttu-id="fede8-109">Questa operazione può essere eseguita sia a livello di programmazione o in fase di progettazione nel **proprietà** finestra.</span><span class="sxs-lookup"><span data-stu-id="fede8-109">This can be done either programmatically or at design time in the **Properties** window.</span></span>  
  
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
  
2.  <span data-ttu-id="fede8-110">Impostare il <xref:System.Windows.Forms.LinkLabel.Text%2A> proprietà su un titolo appropriato.</span><span class="sxs-lookup"><span data-stu-id="fede8-110">Set the <xref:System.Windows.Forms.LinkLabel.Text%2A> property to an appropriate caption.</span></span>  
  
     <span data-ttu-id="fede8-111">Questa operazione può essere eseguita sia a livello di programmazione o in fase di progettazione nel **proprietà** finestra.</span><span class="sxs-lookup"><span data-stu-id="fede8-111">This can be done either programmatically or at design time in the **Properties** window.</span></span>  
  
    ```vb  
    LinkLabel1.Text = "Click here to see more."  
    ```  
  
    ```csharp  
    linkLabel1.Text = "Click here to see more.";  
    ```  
  
    ```cpp  
    linkLabel1->Text = "Click here to see more.";  
    ```  
  
3.  <span data-ttu-id="fede8-112">Impostare il <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> proprietà per determinare quale parte della didascalia verrà indicato come collegamento.</span><span class="sxs-lookup"><span data-stu-id="fede8-112">Set the <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> property to determine which part of the caption will be indicated as a link.</span></span>  
  
     <span data-ttu-id="fede8-113">Il <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> valore è rappresentato con una <xref:System.Windows.Forms.LinkArea> contenente due numeri, la posizione del carattere iniziale e il numero di caratteri.</span><span class="sxs-lookup"><span data-stu-id="fede8-113">The <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> value is represented with a <xref:System.Windows.Forms.LinkArea> containing two numbers, the starting character position and the number of characters.</span></span> <span data-ttu-id="fede8-114">Questa operazione può essere eseguita sia a livello di programmazione o in fase di progettazione nel **proprietà** finestra.</span><span class="sxs-lookup"><span data-stu-id="fede8-114">This can be done either programmatically or at design time in the **Properties** window.</span></span>  
  
    ```vb  
    LinkLabel1.LinkArea = new LinkArea(6,4)  
    ```  
  
    ```csharp  
    linkLabel1.LinkArea = new LinkArea(6,4);  
    ```  
  
    ```cpp  
    linkLabel1->LinkArea = LinkArea(6,4);  
    ```  
  
4.  <span data-ttu-id="fede8-115">Impostare il <xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A> proprietà <xref:System.Windows.Forms.LinkBehavior.AlwaysUnderline>, <xref:System.Windows.Forms.LinkBehavior.HoverUnderline>, o <xref:System.Windows.Forms.LinkBehavior.NeverUnderline>.</span><span class="sxs-lookup"><span data-stu-id="fede8-115">Set the <xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A> property to <xref:System.Windows.Forms.LinkBehavior.AlwaysUnderline>, <xref:System.Windows.Forms.LinkBehavior.HoverUnderline>, or <xref:System.Windows.Forms.LinkBehavior.NeverUnderline>.</span></span>  
  
     <span data-ttu-id="fede8-116">Se è impostato su <xref:System.Windows.Forms.LinkBehavior.HoverUnderline>, la parte della didascalia determinata dal <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> sarà sottolineato solo quando il puntatore è posizionato su di esso.</span><span class="sxs-lookup"><span data-stu-id="fede8-116">If it is set to <xref:System.Windows.Forms.LinkBehavior.HoverUnderline>, the part of the caption determined by <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> will only be underlined when the pointer rests on it.</span></span>  
  
5.  <span data-ttu-id="fede8-117">Nel <xref:System.Windows.Forms.LinkLabel.LinkClicked> gestore dell'evento, impostare il <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> proprietà `true`.</span><span class="sxs-lookup"><span data-stu-id="fede8-117">In the <xref:System.Windows.Forms.LinkLabel.LinkClicked> event handler, set the <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> property to `true`.</span></span>  
  
     <span data-ttu-id="fede8-118">Quando è stato visitato un collegamento, è pratica comune per modificarne l'aspetto in qualche modo, in genere in base al colore.</span><span class="sxs-lookup"><span data-stu-id="fede8-118">When a link has been visited, it is common practice to change its appearance in some way, usually by color.</span></span> <span data-ttu-id="fede8-119">Il testo cambierà il colore specificato da di <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="fede8-119">The text will change to the color specified by the <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A> property.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="fede8-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fede8-120">See also</span></span>

- <xref:System.Windows.Forms.LinkLabel.LinkArea%2A>
- <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>
- <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>
- <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A>
- [<span data-ttu-id="fede8-121">Panoramica del controllo LinkLabel</span><span class="sxs-lookup"><span data-stu-id="fede8-121">LinkLabel Control Overview</span></span>](linklabel-control-overview-windows-forms.md)
- [<span data-ttu-id="fede8-122">Procedura: Eseguire il collegamento a un oggetto o a una pagina Web con il controllo LinkLabel di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="fede8-122">How to: Link to an Object or Web Page with the Windows Forms LinkLabel Control</span></span>](link-to-an-object-or-web-page-with-wf-linklabel-control.md)
- [<span data-ttu-id="fede8-123">Controllo LinkLabel</span><span class="sxs-lookup"><span data-stu-id="fede8-123">LinkLabel Control</span></span>](linklabel-control-windows-forms.md)
