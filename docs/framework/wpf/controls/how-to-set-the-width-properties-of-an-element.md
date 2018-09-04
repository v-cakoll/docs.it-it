---
title: 'Procedura: impostare le proprietà di larghezza di un elemento'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- width properties [WPF]
- Panel control [WPF], width properties of elements
ms.assetid: 6ee04a9d-63f0-4f5b-a406-0a8cd4c35729
ms.openlocfilehash: 261318e3d1433a47eeec2069f484124efd14653f
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43523811"
---
# <a name="how-to-set-the-width-properties-of-an-element"></a><span data-ttu-id="40171-102">Procedura: impostare le proprietà di larghezza di un elemento</span><span class="sxs-lookup"><span data-stu-id="40171-102">How to: Set the Width Properties of an Element</span></span>
## <a name="example"></a><span data-ttu-id="40171-103">Esempio</span><span class="sxs-lookup"><span data-stu-id="40171-103">Example</span></span>  
 <span data-ttu-id="40171-104">In questo esempio vengono illustrate le differenze nel comportamento di rendering tra le quattro proprietà relative alla larghezza in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="40171-104">This example visually shows the differences in rendering behavior among the four width-related properties in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].</span></span>  
  
 <span data-ttu-id="40171-105">Il <xref:System.Windows.FrameworkElement> classe espone quattro proprietà che descrivono le caratteristiche della larghezza di un elemento.</span><span class="sxs-lookup"><span data-stu-id="40171-105">The <xref:System.Windows.FrameworkElement> class exposes four properties that describe the width characteristics of an element.</span></span> <span data-ttu-id="40171-106">Possono verificarsi conflitti tra queste quattro proprietà e in tal caso, il valore ha la precedenza viene determinato come segue: il <xref:System.Windows.FrameworkElement.MinWidth%2A> valore ha la precedenza sul <xref:System.Windows.FrameworkElement.MaxWidth%2A> valore, che a sua volta ha la precedenza sul <xref:System.Windows.FrameworkElement.Width%2A> valore.</span><span class="sxs-lookup"><span data-stu-id="40171-106">These four properties can conflict, and when they do, the value that takes precedence is determined as follows: the <xref:System.Windows.FrameworkElement.MinWidth%2A> value takes precedence over the <xref:System.Windows.FrameworkElement.MaxWidth%2A> value, which in turn takes precedence over the <xref:System.Windows.FrameworkElement.Width%2A> value.</span></span> <span data-ttu-id="40171-107">Una proprietà di quarta <xref:System.Windows.FrameworkElement.ActualWidth%2A>è di sola lettura e la larghezza effettiva a quanto determinato dalle interazioni con il processo di layout di report.</span><span class="sxs-lookup"><span data-stu-id="40171-107">A fourth property, <xref:System.Windows.FrameworkElement.ActualWidth%2A>, is read-only, and reports the actual width as determined by interactions with the layout process.</span></span>  
  
 <span data-ttu-id="40171-108">Quanto segue [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] negli esempi viene tracciato un <xref:System.Windows.Shapes.Rectangle> elemento (`rect1`) come elemento figlio <xref:System.Windows.Controls.Canvas>.</span><span class="sxs-lookup"><span data-stu-id="40171-108">The following [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] examples draw a <xref:System.Windows.Shapes.Rectangle> element (`rect1`) as a child of <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="40171-109">È possibile modificare le proprietà di larghezza di una <xref:System.Windows.Shapes.Rectangle> tramite una serie di <xref:System.Windows.Controls.ListBox> gli elementi che rappresentano i valori delle proprietà <xref:System.Windows.FrameworkElement.MinWidth%2A>, <xref:System.Windows.FrameworkElement.MaxWidth%2A>, e <xref:System.Windows.FrameworkElement.Width%2A>.</span><span class="sxs-lookup"><span data-stu-id="40171-109">You can change the width properties of a <xref:System.Windows.Shapes.Rectangle> by using a series of <xref:System.Windows.Controls.ListBox> elements that represent the property values of <xref:System.Windows.FrameworkElement.MinWidth%2A>, <xref:System.Windows.FrameworkElement.MaxWidth%2A>, and <xref:System.Windows.FrameworkElement.Width%2A>.</span></span> <span data-ttu-id="40171-110">In questo modo, viene visualizzata in modo visivo la priorità di ogni proprietà.</span><span class="sxs-lookup"><span data-stu-id="40171-110">In this manner, the precedence of each property is visually displayed.</span></span>  
  
 [!code-xaml[WidthMinWidthMaxWidth#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WidthMinWidthMaxWidth/CSharp/Window1.xaml#1)]  
[!code-xaml[WidthMinWidthMaxWidth#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WidthMinWidthMaxWidth/CSharp/Window1.xaml#2)]  
  
 <span data-ttu-id="40171-111">Gli esempi di codice seguenti gestiscono gli eventi che il <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> generati dagli eventi.</span><span class="sxs-lookup"><span data-stu-id="40171-111">The following code-behind examples handle the events that the <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> event raises.</span></span> <span data-ttu-id="40171-112">Ogni metodo personalizzato accetta l'input dal <xref:System.Windows.Controls.ListBox>, analizza il valore come un <xref:System.Double>e applica il valore della proprietà relative alla larghezza specificata.</span><span class="sxs-lookup"><span data-stu-id="40171-112">Each custom method takes the input from the <xref:System.Windows.Controls.ListBox>, parses the value as a <xref:System.Double>, and applies the value to the specified width-related property.</span></span> <span data-ttu-id="40171-113">I valori di larghezza sono inoltre convertiti in una stringa e scritti nei vari <xref:System.Windows.Controls.TextBlock> elementi (definizione di tali elementi non viene visualizzato nella finestra di XAML selezionato).</span><span class="sxs-lookup"><span data-stu-id="40171-113">The width values are also converted to a string and written to various <xref:System.Windows.Controls.TextBlock> elements (definition of those elements is not shown in the selected XAML).</span></span>  
  
 [!code-csharp[WidthMinWidthMaxWidth#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WidthMinWidthMaxWidth/CSharp/Window1.xaml.cs#3)]
 [!code-vb[WidthMinWidthMaxWidth#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WidthMinWidthMaxWidth/VisualBasic/Window1.xaml.vb#3)]  
  
 <span data-ttu-id="40171-114">Per l'esempio completo, vedere [Width Properties Comparison Sample](https://go.microsoft.com/fwlink/?LinkID=160050).</span><span class="sxs-lookup"><span data-stu-id="40171-114">For the complete sample, see [Width Properties Comparison Sample](https://go.microsoft.com/fwlink/?LinkID=160050).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40171-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="40171-115">See Also</span></span>  
 <xref:System.Windows.Controls.ListBox>  
 <xref:System.Windows.FrameworkElement>  
 <xref:System.Windows.FrameworkElement.ActualWidth%2A>  
 <xref:System.Windows.FrameworkElement.MaxWidth%2A>  
 <xref:System.Windows.FrameworkElement.MinWidth%2A>  
 <xref:System.Windows.FrameworkElement.Width%2A>  
 [<span data-ttu-id="40171-116">Cenni preliminari sugli elementi Panel</span><span class="sxs-lookup"><span data-stu-id="40171-116">Panels Overview</span></span>](../../../../docs/framework/wpf/controls/panels-overview.md)  
 [<span data-ttu-id="40171-117">Impostare le proprietà di altezza di un elemento</span><span class="sxs-lookup"><span data-stu-id="40171-117">Set the Height Properties of an Element</span></span>](../../../../docs/framework/wpf/controls/how-to-set-the-height-properties-of-an-element.md)  
 [<span data-ttu-id="40171-118">Width Properties Comparison Sample</span><span class="sxs-lookup"><span data-stu-id="40171-118">Width Properties Comparison Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=160050)
