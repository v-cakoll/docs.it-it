---
title: 'Procedura: visualizzare le barre di scorrimento nel controllo RichTextBox Windows Form'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- text boxes [Windows Forms], displaying scroll bars
- scroll bars [Windows Forms], displaying in controls
- RichTextBox control [Windows Forms], displaying scroll bars
ms.assetid: cdeb42e1-86e8-410c-ba46-18aec264ef5f
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3b20c526b27eb185bf79eaf0ace47e5a9fded42a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-display-scroll-bars-in-the-windows-forms-richtextbox-control"></a><span data-ttu-id="b2e1b-102">Procedura: visualizzare le barre di scorrimento nel controllo RichTextBox Windows Form</span><span class="sxs-lookup"><span data-stu-id="b2e1b-102">How to: Display Scroll Bars in the Windows Forms RichTextBox Control</span></span>
<span data-ttu-id="b2e1b-103">Per impostazione predefinita, Windows Form <xref:System.Windows.Forms.RichTextBox> controllo vengono visualizzate barre di scorrimento orizzontale e verticale in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="b2e1b-103">By default, the Windows Forms <xref:System.Windows.Forms.RichTextBox> control displays horizontal and vertical scroll bars as necessary.</span></span> <span data-ttu-id="b2e1b-104">Esistono sette valori possibili per il <xref:System.Windows.Forms.RichTextBox.ScrollBars%2A> proprietà del <xref:System.Windows.Forms.RichTextBox> controllo, che sono descritte nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="b2e1b-104">There are seven possible values for the <xref:System.Windows.Forms.RichTextBox.ScrollBars%2A> property of the <xref:System.Windows.Forms.RichTextBox> control, which are described in the table below.</span></span>  
  
### <a name="to-display-scroll-bars-in-a-richtextbox-control"></a><span data-ttu-id="b2e1b-105">Per visualizzare le barre di scorrimento in un controllo RichTextBox</span><span class="sxs-lookup"><span data-stu-id="b2e1b-105">To display scroll bars in a RichTextBox control</span></span>  
  
1.  <span data-ttu-id="b2e1b-106">Impostare la proprietà <xref:System.Windows.Forms.RichTextBox.Multiline%2A> su `true`.</span><span class="sxs-lookup"><span data-stu-id="b2e1b-106">Set the <xref:System.Windows.Forms.RichTextBox.Multiline%2A> property to `true`.</span></span> <span data-ttu-id="b2e1b-107">Nessun tipo di barra di scorrimento, tra cui orizzontale, verrà visualizzato se il <xref:System.Windows.Forms.RichTextBox.Multiline%2A> è impostata su `false`.</span><span class="sxs-lookup"><span data-stu-id="b2e1b-107">No type of scroll bar, including horizontal, will display if the <xref:System.Windows.Forms.RichTextBox.Multiline%2A> property is set to `false`.</span></span>  
  
2.  <span data-ttu-id="b2e1b-108">Impostare il <xref:System.Windows.Forms.RichTextBox.ScrollBars%2A> proprietà su un valore appropriato per il <xref:System.Windows.Forms.RichTextBoxScrollBars> enumerazione.</span><span class="sxs-lookup"><span data-stu-id="b2e1b-108">Set the <xref:System.Windows.Forms.RichTextBox.ScrollBars%2A> property to an appropriate value of the <xref:System.Windows.Forms.RichTextBoxScrollBars> enumeration.</span></span>  
  
    |<span data-ttu-id="b2e1b-109">Valore</span><span class="sxs-lookup"><span data-stu-id="b2e1b-109">Value</span></span>|<span data-ttu-id="b2e1b-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b2e1b-110">Description</span></span>|  
    |-----------|-----------------|  
    |<span data-ttu-id="b2e1b-111"><xref:System.Windows.Forms.RichTextBoxScrollBars.Both> (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="b2e1b-111"><xref:System.Windows.Forms.RichTextBoxScrollBars.Both> (default)</span></span>|<span data-ttu-id="b2e1b-112">Consente di visualizzare le barre di scorrimento orizzontale o verticale, o entrambi, solo quando il testo supera la larghezza o la lunghezza del controllo.</span><span class="sxs-lookup"><span data-stu-id="b2e1b-112">Displays horizontal or vertical scroll bars, or both, only when text exceeds the width or length of the control.</span></span>|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.None>|<span data-ttu-id="b2e1b-113">Non visualizza mai qualsiasi tipo di barra di scorrimento.</span><span class="sxs-lookup"><span data-stu-id="b2e1b-113">Never displays any type of scroll bar.</span></span>|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.Horizontal>|<span data-ttu-id="b2e1b-114">Visualizza una barra solo quando il testo supera la larghezza del controllo di scorrimento orizzontale.</span><span class="sxs-lookup"><span data-stu-id="b2e1b-114">Displays a horizontal scroll bar only when the text exceeds the width of the control.</span></span> <span data-ttu-id="b2e1b-115">(A questo scopo, il <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> proprietà deve essere impostata su `false`.)</span><span class="sxs-lookup"><span data-stu-id="b2e1b-115">(For this to occur, the <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> property must be set to `false`.)</span></span>|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.Vertical>|<span data-ttu-id="b2e1b-116">Visualizza una barra solo quando il testo supera l'altezza del controllo di scorrimento verticale.</span><span class="sxs-lookup"><span data-stu-id="b2e1b-116">Displays a vertical scroll bar only when the text exceeds the height of the control.</span></span>|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.ForcedHorizontal>|<span data-ttu-id="b2e1b-117">Viene visualizzata quando della barra di scorrimento orizzontale di <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> è impostata su `false`.</span><span class="sxs-lookup"><span data-stu-id="b2e1b-117">Displays a horizontal scroll bar when the <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> property is set to `false`.</span></span> <span data-ttu-id="b2e1b-118">La barra di scorrimento non è disponibile quando il testo supera la larghezza del controllo.</span><span class="sxs-lookup"><span data-stu-id="b2e1b-118">The scroll bar appears dimmed when text does not exceed the width of the control.</span></span>|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.ForcedVertical>|<span data-ttu-id="b2e1b-119">Visualizza sempre una barra di scorrimento verticale.</span><span class="sxs-lookup"><span data-stu-id="b2e1b-119">Always displays a vertical scroll bar.</span></span> <span data-ttu-id="b2e1b-120">La barra di scorrimento non è disponibile quando il testo supera la lunghezza del controllo.</span><span class="sxs-lookup"><span data-stu-id="b2e1b-120">The scroll bar appears dimmed when text does not exceed the length of the control.</span></span>|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.ForcedBoth>|<span data-ttu-id="b2e1b-121">Visualizza sempre una barra di scorrimento verticale.</span><span class="sxs-lookup"><span data-stu-id="b2e1b-121">Always displays a vertical scrollbar.</span></span> <span data-ttu-id="b2e1b-122">Viene visualizzata quando della barra di scorrimento orizzontale di <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> è impostata su `false`.</span><span class="sxs-lookup"><span data-stu-id="b2e1b-122">Displays a horizontal scroll bar when the <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> property is set to `false`.</span></span> <span data-ttu-id="b2e1b-123">Le barre di scorrimento non sono disponibili quando il testo supera la larghezza o la lunghezza del controllo.</span><span class="sxs-lookup"><span data-stu-id="b2e1b-123">The scroll bars appear grayed when text does not exceed the width or length of the control.</span></span>|  
  
3.  <span data-ttu-id="b2e1b-124">Impostare la proprietà <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> su un valore appropriato.</span><span class="sxs-lookup"><span data-stu-id="b2e1b-124">Set the <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> property to an appropriate value.</span></span>  
  
    |<span data-ttu-id="b2e1b-125">Valore</span><span class="sxs-lookup"><span data-stu-id="b2e1b-125">Value</span></span>|<span data-ttu-id="b2e1b-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b2e1b-126">Description</span></span>|  
    |-----------|-----------------|  
    |`false`|<span data-ttu-id="b2e1b-127">Il testo del controllo non viene regolato automaticamente in base alla larghezza del controllo, in modo che verrà scorrere verso destra fino a quando non viene raggiunta un'interruzione di riga.</span><span class="sxs-lookup"><span data-stu-id="b2e1b-127">Text in the control is not automatically adjusted to fit the width of the control, so it will scroll to the right until a line break is reached.</span></span> <span data-ttu-id="b2e1b-128">Utilizzare questo valore se si sceglie di barre di scorrimento orizzontale o entrambi, in precedenza.</span><span class="sxs-lookup"><span data-stu-id="b2e1b-128">Use this value if you chose horizontal scroll bars or both, above.</span></span>|  
    |<span data-ttu-id="b2e1b-129">`true` (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="b2e1b-129">`true` (default)</span></span>|<span data-ttu-id="b2e1b-130">Il testo del controllo viene regolato automaticamente in base alla larghezza del controllo.</span><span class="sxs-lookup"><span data-stu-id="b2e1b-130">Text in the control is automatically adjusted to fit the width of the control.</span></span> <span data-ttu-id="b2e1b-131">Non verrà visualizzata la barra di scorrimento orizzontale.</span><span class="sxs-lookup"><span data-stu-id="b2e1b-131">The horizontal scrollbar will not appear.</span></span> <span data-ttu-id="b2e1b-132">Utilizzare questo valore se si sceglie le barre di scorrimento verticale sopra, per visualizzare uno o più paragrafi.</span><span class="sxs-lookup"><span data-stu-id="b2e1b-132">Use this value if you chose vertical scroll bars or none, above, to display one or more paragraphs.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b2e1b-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b2e1b-133">See Also</span></span>  
 <xref:System.Windows.Forms.RichTextBoxScrollBars>  
 <xref:System.Windows.Forms.RichTextBox>  
 [<span data-ttu-id="b2e1b-134">Controllo RichTextBox</span><span class="sxs-lookup"><span data-stu-id="b2e1b-134">RichTextBox Control</span></span>](../../../../docs/framework/winforms/controls/richtextbox-control-windows-forms.md)  
 [<span data-ttu-id="b2e1b-135">Controlli da usare in Windows Form</span><span class="sxs-lookup"><span data-stu-id="b2e1b-135">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)
