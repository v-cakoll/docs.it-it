---
title: 'Procedura: creare un effetto di testo'
ms.date: 03/30/2017
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
ms.openlocfilehash: cf3b3c3bcb75153a0be4f7ced03b38134b79a930
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185927"
---
# <a name="how-to-create-a-text-decoration"></a><span data-ttu-id="1bef5-102">Procedura: creare un effetto di testo</span><span class="sxs-lookup"><span data-stu-id="1bef5-102">How to: Create a Text Decoration</span></span>
<span data-ttu-id="1bef5-103">Un <xref:System.Windows.TextDecoration> oggetto è un ornamento visivo che è possibile aggiungere al testo.</span><span class="sxs-lookup"><span data-stu-id="1bef5-103">A <xref:System.Windows.TextDecoration> object is a visual ornamentation you can add to text.</span></span> <span data-ttu-id="1bef5-104">Esistono quattro tipi di decorazioni di testo: sottolineatura, linea di base, barrato e overline.</span><span class="sxs-lookup"><span data-stu-id="1bef5-104">There are four types of text decorations: underline, baseline, strikethrough, and overline.</span></span> <span data-ttu-id="1bef5-105">L'esempio seguente mostra le posizioni delle decorazioni di testo relative al testo.</span><span class="sxs-lookup"><span data-stu-id="1bef5-105">The following example shows the locations of the text decorations relative to the text.</span></span>  
  
 ![Diagramma dei tipi di decorazione del testo](./media/how-to-create-a-text-decoration/text-decoration-types.gif)  
  
 <span data-ttu-id="1bef5-107">Per aggiungere una decorazione di <xref:System.Windows.TextDecoration> testo al testo, creare un oggetto e modificarne le proprietà.</span><span class="sxs-lookup"><span data-stu-id="1bef5-107">To add a text decoration to text, create a <xref:System.Windows.TextDecoration> object and modify its properties.</span></span> <span data-ttu-id="1bef5-108">Utilizzare <xref:System.Windows.TextDecoration.Location%2A> la proprietà per specificare dove viene visualizzata la decorazione di testo, ad esempio sottolineatura.</span><span class="sxs-lookup"><span data-stu-id="1bef5-108">Use the <xref:System.Windows.TextDecoration.Location%2A> property to specify where the text decoration appears, such as underline.</span></span> <span data-ttu-id="1bef5-109">Utilizzare <xref:System.Windows.TextDecoration.Pen%2A> la proprietà per specificare l'aspetto della decorazione di testo, ad esempio un riempimento a tinta unita o un colore sfumato.</span><span class="sxs-lookup"><span data-stu-id="1bef5-109">Use the <xref:System.Windows.TextDecoration.Pen%2A> property to specify the appearance of the text decoration, such as a solid fill or gradient color.</span></span> <span data-ttu-id="1bef5-110">Se non si specifica un <xref:System.Windows.TextDecoration.Pen%2A> valore per la proprietà, per impostazione predefinita le decorazioni hanno lo stesso colore del testo.</span><span class="sxs-lookup"><span data-stu-id="1bef5-110">If you do not specify a value for the <xref:System.Windows.TextDecoration.Pen%2A> property, the decorations defaults to the same color as the text.</span></span> <span data-ttu-id="1bef5-111">Dopo aver definito <xref:System.Windows.TextDecoration> un oggetto, <xref:System.Windows.TextDecorations> aggiungerlo alla raccolta dell'oggetto di testo desiderato.</span><span class="sxs-lookup"><span data-stu-id="1bef5-111">Once you have defined a <xref:System.Windows.TextDecoration> object, add it to the <xref:System.Windows.TextDecorations> collection of the desired text object.</span></span>  
  
 <span data-ttu-id="1bef5-112">L'esempio seguente mostra una decorazione di testo a cui è stata creata uno stile con un pennello sfumato lineare e una penna tratteggiata.</span><span class="sxs-lookup"><span data-stu-id="1bef5-112">The following example shows a text decoration that has been styled with a linear gradient brush and a dashed pen.</span></span>  
  
 ![Decorazione di testo con sottolineatura sfumata lineare](./media/how-to-create-a-text-decoration/text-decoration-gradient.png)  
  
 <span data-ttu-id="1bef5-114">L'oggetto <xref:System.Windows.Documents.Hyperlink> è un elemento di contenuto del flusso di livello inline che consente di ospitare collegamenti ipertestuali all'interno del contenuto del flusso.</span><span class="sxs-lookup"><span data-stu-id="1bef5-114">The <xref:System.Windows.Documents.Hyperlink> object is an inline-level flow content element that allows you to host hyperlinks within the flow content.</span></span> <span data-ttu-id="1bef5-115">Per impostazione <xref:System.Windows.Documents.Hyperlink> <xref:System.Windows.TextDecoration> predefinita, utilizza un oggetto per visualizzare una sottolineatura.</span><span class="sxs-lookup"><span data-stu-id="1bef5-115">By default, <xref:System.Windows.Documents.Hyperlink> uses a <xref:System.Windows.TextDecoration> object to display an underline.</span></span> <span data-ttu-id="1bef5-116"><xref:System.Windows.TextDecoration>Gli oggetti possono richiedere un utilizzo intensivo delle prestazioni per creare un'istanza, in particolare se si dispone di molti <xref:System.Windows.Documents.Hyperlink> oggetti.</span><span class="sxs-lookup"><span data-stu-id="1bef5-116"><xref:System.Windows.TextDecoration> objects can be performance intensive to instantiate, particularly if you have many <xref:System.Windows.Documents.Hyperlink> objects.</span></span> <span data-ttu-id="1bef5-117">Se si fa <xref:System.Windows.Documents.Hyperlink> ampio uso di elementi, è consigliabile visualizzare una sottolineatura <xref:System.Windows.ContentElement.MouseEnter> solo quando si attiva un evento, ad esempio l'evento.</span><span class="sxs-lookup"><span data-stu-id="1bef5-117">If you make extensive use of <xref:System.Windows.Documents.Hyperlink> elements, you may want to consider showing an underline only when triggering an event, such as the <xref:System.Windows.ContentElement.MouseEnter> event.</span></span>  
  
 <span data-ttu-id="1bef5-118">Nell'esempio seguente, la sottolineatura per il collegamento "Msn" <xref:System.Windows.ContentElement.MouseEnter> è dinamica, ma viene visualizzata solo quando l'evento viene attivato.</span><span class="sxs-lookup"><span data-stu-id="1bef5-118">In the following example, the underline for the "My MSN" link is dynamic—it only appears when the <xref:System.Windows.ContentElement.MouseEnter> event is triggered.</span></span>  
  
 ![Collegamenti ipertestuali con TextDecoration](./media/how-to-create-a-text-decoration/text-decorations-hyperlinks.png)  

 <span data-ttu-id="1bef5-120">Per altre informazioni, vedere [Specificare se un collegamento ipertestuale è sottolineato](how-to-specify-whether-a-hyperlink-is-underlined.md).</span><span class="sxs-lookup"><span data-stu-id="1bef5-120">For more information, see [Specify Whether a Hyperlink is Underlined](how-to-specify-whether-a-hyperlink-is-underlined.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1bef5-121">Esempio</span><span class="sxs-lookup"><span data-stu-id="1bef5-121">Example</span></span>  
 <span data-ttu-id="1bef5-122">Nell'esempio di codice seguente, una decorazione di testo sottolineato utilizza il valore del carattere predefinito.</span><span class="sxs-lookup"><span data-stu-id="1bef5-122">In the following code example, an underline text decoration uses the default font value.</span></span>  
  
 [!code-csharp[TextDecorationSnippets#TextDecorationSnippets1](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml.cs#textdecorationsnippets1)]
 [!code-vb[TextDecorationSnippets#TextDecorationSnippets1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextDecorationSnippets/visualbasic/window1.xaml.vb#textdecorationsnippets1)]
 [!code-xaml[TextDecorationSnippets#TextDecorationSnippets1](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml#textdecorationsnippets1)]  
  
 <span data-ttu-id="1bef5-123">Nell'esempio di codice seguente viene creata una decorazione di testo sottolineato con un pennello a tinta unita per la penna.</span><span class="sxs-lookup"><span data-stu-id="1bef5-123">In the following code example, an underline text decoration is created with a solid color brush for the pen.</span></span>  
  
 [!code-csharp[TextDecorationSnippets#TextDecorationSnippets2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml.cs#textdecorationsnippets2)]
 [!code-vb[TextDecorationSnippets#TextDecorationSnippets2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextDecorationSnippets/visualbasic/window1.xaml.vb#textdecorationsnippets2)]
 [!code-xaml[TextDecorationSnippets#TextDecorationSnippets2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml#textdecorationsnippets2)]  
  
 <span data-ttu-id="1bef5-124">Nell'esempio di codice seguente viene creata una decorazione di testo sottolineato con un pennello sfumato lineare per la penna tratteggiata.</span><span class="sxs-lookup"><span data-stu-id="1bef5-124">In the following code example, an underline text decoration is created with a linear gradient brush for the dashed pen.</span></span>  
  
 [!code-csharp[TextDecorationSnippets#TextDecorationSnippets3](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml.cs#textdecorationsnippets3)]
 [!code-vb[TextDecorationSnippets#TextDecorationSnippets3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextDecorationSnippets/visualbasic/window1.xaml.vb#textdecorationsnippets3)]
 [!code-xaml[TextDecorationSnippets#TextDecorationSnippets3](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml#textdecorationsnippets3)]  
  
## <a name="see-also"></a><span data-ttu-id="1bef5-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1bef5-125">See also</span></span>

- <xref:System.Windows.TextDecoration>
- <xref:System.Windows.Documents.Hyperlink>
- [<span data-ttu-id="1bef5-126">Specificare se un collegamento ipertestuale è sottolineato</span><span class="sxs-lookup"><span data-stu-id="1bef5-126">Specify Whether a Hyperlink is Underlined</span></span>](how-to-specify-whether-a-hyperlink-is-underlined.md)
