---
title: 'Procedura: creare un effetto di testo'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- fonts [WPF], baseline
- text [WPF], decorations
- fonts [WPF], underline
- fonts [WPF], overline
- strikethrough type [WPF]
- fonts [WPF], strikethrough
- overline type [WPF]
- underline type [WPF]
- typography [WPF], text decorations
- baseline type [WPF]
ms.assetid: cf3cb4e7-782a-4be7-b2d4-e0935e21e4e0
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0beb22ba78c6fc99951bc2d780c1c5defa32e637
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-text-decoration"></a><span data-ttu-id="b3179-102">Procedura: creare un effetto di testo</span><span class="sxs-lookup"><span data-stu-id="b3179-102">How to: Create a Text Decoration</span></span>
<span data-ttu-id="b3179-103">Oggetto <xref:System.Windows.TextDecoration> oggetto è un visual ornamenti, è possibile aggiungere testo.</span><span class="sxs-lookup"><span data-stu-id="b3179-103">A <xref:System.Windows.TextDecoration> object is a visual ornamentation you can add to text.</span></span> <span data-ttu-id="b3179-104">Sono disponibili quattro tipi di effetti del testo: sottolineato, linea di base, barrato e linea sopra.</span><span class="sxs-lookup"><span data-stu-id="b3179-104">There are four types of text decorations: underline, baseline, strikethrough, and overline.</span></span> <span data-ttu-id="b3179-105">L'esempio seguente mostra la posizione delle decorazioni di testo rispetto al testo.</span><span class="sxs-lookup"><span data-stu-id="b3179-105">The following example shows the locations of the text decorations relative to the text.</span></span>  
  
 <span data-ttu-id="b3179-106">![Diagramma di posizione delle decorazioni di testo](../../../../docs/framework/wpf/advanced/media/textdecoration01.gif "TextDecoration01")</span><span class="sxs-lookup"><span data-stu-id="b3179-106">![Diagram of text decoration locations](../../../../docs/framework/wpf/advanced/media/textdecoration01.gif "TextDecoration01")</span></span>  
<span data-ttu-id="b3179-107">Esempio di tipi di effetti di testo</span><span class="sxs-lookup"><span data-stu-id="b3179-107">Example of text decoration types</span></span>  
  
 <span data-ttu-id="b3179-108">Per aggiungere un effetto di testo, creare un <xref:System.Windows.TextDecoration> dell'oggetto e modificarne le proprietà.</span><span class="sxs-lookup"><span data-stu-id="b3179-108">To add a text decoration to text, create a <xref:System.Windows.TextDecoration> object and modify its properties.</span></span> <span data-ttu-id="b3179-109">Utilizzare il <xref:System.Windows.TextDecoration.Location%2A> proprietà per specificare dove viene visualizzato l'effetto di testo, quali sottolineato.</span><span class="sxs-lookup"><span data-stu-id="b3179-109">Use the <xref:System.Windows.TextDecoration.Location%2A> property to specify where the text decoration appears, such as underline.</span></span> <span data-ttu-id="b3179-110">Utilizzare il <xref:System.Windows.TextDecoration.Pen%2A> proprietà per specificare l'aspetto dell'effetto di testo, ad esempio un riempimento a tinta unita o sfumatura di colore.</span><span class="sxs-lookup"><span data-stu-id="b3179-110">Use the <xref:System.Windows.TextDecoration.Pen%2A> property to specify the appearance of the text decoration, such as a solid fill or gradient color.</span></span> <span data-ttu-id="b3179-111">Se non si specifica un valore per il <xref:System.Windows.TextDecoration.Pen%2A> proprietà, i valori predefiniti effetti sullo stesso colore del testo.</span><span class="sxs-lookup"><span data-stu-id="b3179-111">If you do not specify a value for the <xref:System.Windows.TextDecoration.Pen%2A> property, the decorations defaults to the same color as the text.</span></span> <span data-ttu-id="b3179-112">Dopo aver definito una <xref:System.Windows.TextDecoration> dell'oggetto, aggiungerlo al <xref:System.Windows.TextDecorations> raccolta dell'oggetto testo desiderato.</span><span class="sxs-lookup"><span data-stu-id="b3179-112">Once you have defined a <xref:System.Windows.TextDecoration> object, add it to the <xref:System.Windows.TextDecorations> collection of the desired text object.</span></span>  
  
 <span data-ttu-id="b3179-113">Nell'esempio seguente viene illustrato un effetto di testo disegnato con pennello sfumato lineare e una penna tratteggiata.</span><span class="sxs-lookup"><span data-stu-id="b3179-113">The following example shows a text decoration that has been styled with a linear gradient brush and a dashed pen.</span></span>  
  
 <span data-ttu-id="b3179-114">![Decorazione di testo con sottolineatura sfumata lineare](../../../../docs/framework/wpf/advanced/media/textdecoration02.png "TextDecoration02")</span><span class="sxs-lookup"><span data-stu-id="b3179-114">![Text decoration with linear gradient underline](../../../../docs/framework/wpf/advanced/media/textdecoration02.png "TextDecoration02")</span></span>  
<span data-ttu-id="b3179-115">Esempio di un carattere di sottolineatura disegnata con una sfumatura lineare pennello e penna tratteggiata</span><span class="sxs-lookup"><span data-stu-id="b3179-115">Example of an underline styled with a linear gradient brush and dashed pen</span></span>  
  
 <span data-ttu-id="b3179-116">Il <xref:System.Windows.Documents.Hyperlink> oggetto è un elemento di contenuto di flusso di livello inline che consente di ospitare collegamenti ipertestuali all'interno del contenuto di flusso.</span><span class="sxs-lookup"><span data-stu-id="b3179-116">The <xref:System.Windows.Documents.Hyperlink> object is an inline-level flow content element that allows you to host hyperlinks within the flow content.</span></span> <span data-ttu-id="b3179-117">Per impostazione predefinita, <xref:System.Windows.Documents.Hyperlink> utilizza un <xref:System.Windows.TextDecoration> oggetto per visualizzare un carattere di sottolineatura.</span><span class="sxs-lookup"><span data-stu-id="b3179-117">By default, <xref:System.Windows.Documents.Hyperlink> uses a <xref:System.Windows.TextDecoration> object to display an underline.</span></span> <span data-ttu-id="b3179-118"><xref:System.Windows.TextDecoration>gli oggetti possono essere prestazioni elevate per creare un'istanza, in particolare se si dispone di numerosi <xref:System.Windows.Documents.Hyperlink> oggetti.</span><span class="sxs-lookup"><span data-stu-id="b3179-118"><xref:System.Windows.TextDecoration> objects can be performance intensive to instantiate, particularly if you have many <xref:System.Windows.Documents.Hyperlink> objects.</span></span> <span data-ttu-id="b3179-119">Se si usano ampiamente <xref:System.Windows.Documents.Hyperlink> elementi, si consiglia di provare a visualizzare un carattere di sottolineatura solo al momento della generazione di un evento, ad esempio il <xref:System.Windows.ContentElement.MouseEnter> evento.</span><span class="sxs-lookup"><span data-stu-id="b3179-119">If you make extensive use of <xref:System.Windows.Documents.Hyperlink> elements, you may want to consider showing an underline only when triggering an event, such as the <xref:System.Windows.ContentElement.MouseEnter> event.</span></span>  
  
 <span data-ttu-id="b3179-120">Nell'esempio seguente, la sottolineatura per il collegamento "My MSN" è dinamica, viene visualizzata solo quando il <xref:System.Windows.ContentElement.MouseEnter> evento viene generato.</span><span class="sxs-lookup"><span data-stu-id="b3179-120">In the following example, the underline for the "My MSN" link is dynamic—it only appears when the <xref:System.Windows.ContentElement.MouseEnter> event is triggered.</span></span>  
  
 <span data-ttu-id="b3179-121">![Collegamenti ipertestuali con TextDecoration](../../../../docs/framework/wpf/advanced/media/textdecoration03.png "TextDecoration03")</span><span class="sxs-lookup"><span data-stu-id="b3179-121">![Hyperlinks displaying TextDecorations](../../../../docs/framework/wpf/advanced/media/textdecoration03.png "TextDecoration03")</span></span>  
<span data-ttu-id="b3179-122">Collegamenti ipertestuali definiti con TextDecorations</span><span class="sxs-lookup"><span data-stu-id="b3179-122">Hyperlinks defined with TextDecorations</span></span>  
  
 <span data-ttu-id="b3179-123">Per altre informazioni, vedere [Specificare se un collegamento ipertestuale è sottolineato](../../../../docs/framework/wpf/advanced/how-to-specify-whether-a-hyperlink-is-underlined.md).</span><span class="sxs-lookup"><span data-stu-id="b3179-123">For more information, see [Specify Whether a Hyperlink is Underlined](../../../../docs/framework/wpf/advanced/how-to-specify-whether-a-hyperlink-is-underlined.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b3179-124">Esempio</span><span class="sxs-lookup"><span data-stu-id="b3179-124">Example</span></span>  
 <span data-ttu-id="b3179-125">Nell'esempio di codice seguente, un effetto di testo sottolineato viene utilizzato il valore di tipo di carattere predefinito.</span><span class="sxs-lookup"><span data-stu-id="b3179-125">In the following code example, an underline text decoration uses the default font value.</span></span>  
  
 [!code-csharp[TextDecorationSnippets#TextDecorationSnippets1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml.cs#textdecorationsnippets1)]
 [!code-vb[TextDecorationSnippets#TextDecorationSnippets1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextDecorationSnippets/visualbasic/window1.xaml.vb#textdecorationsnippets1)]
 [!code-xaml[TextDecorationSnippets#TextDecorationSnippets1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml#textdecorationsnippets1)]  
  
 <span data-ttu-id="b3179-126">Nell'esempio di codice riportato di seguito, un effetto di testo sottolineato viene creato con un pennello tinta unita per la penna.</span><span class="sxs-lookup"><span data-stu-id="b3179-126">In the following code example, an underline text decoration is created with a solid color brush for the pen.</span></span>  
  
 [!code-csharp[TextDecorationSnippets#TextDecorationSnippets2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml.cs#textdecorationsnippets2)]
 [!code-vb[TextDecorationSnippets#TextDecorationSnippets2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextDecorationSnippets/visualbasic/window1.xaml.vb#textdecorationsnippets2)]
 [!code-xaml[TextDecorationSnippets#TextDecorationSnippets2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml#textdecorationsnippets2)]  
  
 <span data-ttu-id="b3179-127">Nell'esempio di codice seguente viene creato un effetto di testo sottolineato con pennello sfumato lineare per la penna tratteggiata.</span><span class="sxs-lookup"><span data-stu-id="b3179-127">In the following code example, an underline text decoration is created with a linear gradient brush for the dashed pen.</span></span>  
  
 [!code-csharp[TextDecorationSnippets#TextDecorationSnippets3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml.cs#textdecorationsnippets3)]
 [!code-vb[TextDecorationSnippets#TextDecorationSnippets3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextDecorationSnippets/visualbasic/window1.xaml.vb#textdecorationsnippets3)]
 [!code-xaml[TextDecorationSnippets#TextDecorationSnippets3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml#textdecorationsnippets3)]  
  
## <a name="see-also"></a><span data-ttu-id="b3179-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b3179-128">See Also</span></span>  
 <xref:System.Windows.TextDecoration>  
 <xref:System.Windows.Documents.Hyperlink>  
 [<span data-ttu-id="b3179-129">Specificare se un collegamento ipertestuale è sottolineato</span><span class="sxs-lookup"><span data-stu-id="b3179-129">Specify Whether a Hyperlink is Underlined</span></span>](../../../../docs/framework/wpf/advanced/how-to-specify-whether-a-hyperlink-is-underlined.md)
