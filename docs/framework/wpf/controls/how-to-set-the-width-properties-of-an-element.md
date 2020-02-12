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
ms.openlocfilehash: 682929625612114d042e4619d8388617988b3c48
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/11/2020
ms.locfileid: "77124273"
---
# <a name="how-to-set-the-width-properties-of-an-element"></a><span data-ttu-id="d5f3c-102">Procedura: impostare le proprietà di larghezza di un elemento</span><span class="sxs-lookup"><span data-stu-id="d5f3c-102">How to: Set the Width Properties of an Element</span></span>
## <a name="example"></a><span data-ttu-id="d5f3c-103">Esempio</span><span class="sxs-lookup"><span data-stu-id="d5f3c-103">Example</span></span>  
 <span data-ttu-id="d5f3c-104">Questo esempio mostra visivamente le differenze nel comportamento di rendering tra le quattro proprietà correlate alla larghezza in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d5f3c-104">This example visually shows the differences in rendering behavior among the four width-related properties in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].</span></span>  
  
 <span data-ttu-id="d5f3c-105">La classe <xref:System.Windows.FrameworkElement> espone quattro proprietà che descrivono le caratteristiche di larghezza di un elemento.</span><span class="sxs-lookup"><span data-stu-id="d5f3c-105">The <xref:System.Windows.FrameworkElement> class exposes four properties that describe the width characteristics of an element.</span></span> <span data-ttu-id="d5f3c-106">Queste quattro proprietà possono entrare in conflitto e, quando lo fanno, il valore che ha la precedenza viene determinato nel modo seguente: il valore <xref:System.Windows.FrameworkElement.MinWidth%2A> ha la precedenza sul valore <xref:System.Windows.FrameworkElement.MaxWidth%2A>, che a sua volta ha la precedenza sul valore di <xref:System.Windows.FrameworkElement.Width%2A>.</span><span class="sxs-lookup"><span data-stu-id="d5f3c-106">These four properties can conflict, and when they do, the value that takes precedence is determined as follows: the <xref:System.Windows.FrameworkElement.MinWidth%2A> value takes precedence over the <xref:System.Windows.FrameworkElement.MaxWidth%2A> value, which in turn takes precedence over the <xref:System.Windows.FrameworkElement.Width%2A> value.</span></span> <span data-ttu-id="d5f3c-107">Una quarta proprietà, <xref:System.Windows.FrameworkElement.ActualWidth%2A>, è di sola lettura e indica la larghezza effettiva determinata dalle interazioni con il processo di layout.</span><span class="sxs-lookup"><span data-stu-id="d5f3c-107">A fourth property, <xref:System.Windows.FrameworkElement.ActualWidth%2A>, is read-only, and reports the actual width as determined by interactions with the layout process.</span></span>  
  
 <span data-ttu-id="d5f3c-108">Negli esempi di [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] seguenti viene disegnato un elemento <xref:System.Windows.Shapes.Rectangle> (`rect1`) come figlio di <xref:System.Windows.Controls.Canvas>.</span><span class="sxs-lookup"><span data-stu-id="d5f3c-108">The following [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] examples draw a <xref:System.Windows.Shapes.Rectangle> element (`rect1`) as a child of <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="d5f3c-109">È possibile modificare le proprietà di larghezza di un <xref:System.Windows.Shapes.Rectangle> usando una serie di <xref:System.Windows.Controls.ListBox> elementi che rappresentano i valori delle proprietà di <xref:System.Windows.FrameworkElement.MinWidth%2A>, <xref:System.Windows.FrameworkElement.MaxWidth%2A>e <xref:System.Windows.FrameworkElement.Width%2A>.</span><span class="sxs-lookup"><span data-stu-id="d5f3c-109">You can change the width properties of a <xref:System.Windows.Shapes.Rectangle> by using a series of <xref:System.Windows.Controls.ListBox> elements that represent the property values of <xref:System.Windows.FrameworkElement.MinWidth%2A>, <xref:System.Windows.FrameworkElement.MaxWidth%2A>, and <xref:System.Windows.FrameworkElement.Width%2A>.</span></span> <span data-ttu-id="d5f3c-110">In questo modo, la precedenza di ogni proprietà viene visualizzata visivamente.</span><span class="sxs-lookup"><span data-stu-id="d5f3c-110">In this manner, the precedence of each property is visually displayed.</span></span>  
  
 [!code-xaml[WidthMinWidthMaxWidth#1](~/samples/snippets/csharp/VS_Snippets_Wpf/WidthMinWidthMaxWidth/CSharp/Window1.xaml#1)]  
[!code-xaml[WidthMinWidthMaxWidth#2](~/samples/snippets/csharp/VS_Snippets_Wpf/WidthMinWidthMaxWidth/CSharp/Window1.xaml#2)]  
  
 <span data-ttu-id="d5f3c-111">Gli esempi code-behind seguenti gestiscono gli eventi generati dall'evento <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged>.</span><span class="sxs-lookup"><span data-stu-id="d5f3c-111">The following code-behind examples handle the events that the <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> event raises.</span></span> <span data-ttu-id="d5f3c-112">Ogni metodo personalizzato accetta l'input dalla <xref:System.Windows.Controls.ListBox>, analizza il valore come <xref:System.Double>e applica il valore alla proprietà relativa alla larghezza specificata.</span><span class="sxs-lookup"><span data-stu-id="d5f3c-112">Each custom method takes the input from the <xref:System.Windows.Controls.ListBox>, parses the value as a <xref:System.Double>, and applies the value to the specified width-related property.</span></span> <span data-ttu-id="d5f3c-113">I valori di larghezza vengono inoltre convertiti in una stringa e scritti in vari elementi di <xref:System.Windows.Controls.TextBlock> (la definizione di tali elementi non viene visualizzata nel codice XAML selezionato).</span><span class="sxs-lookup"><span data-stu-id="d5f3c-113">The width values are also converted to a string and written to various <xref:System.Windows.Controls.TextBlock> elements (definition of those elements is not shown in the selected XAML).</span></span>  
  
 [!code-csharp[WidthMinWidthMaxWidth#3](~/samples/snippets/csharp/VS_Snippets_Wpf/WidthMinWidthMaxWidth/CSharp/Window1.xaml.cs#3)]
 [!code-vb[WidthMinWidthMaxWidth#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WidthMinWidthMaxWidth/VisualBasic/Window1.xaml.vb#3)]  
  
 <span data-ttu-id="d5f3c-114">Per l'esempio completo, vedere [esempio di confronto delle proprietà Width](https://github.com/Microsoft/WPF-Samples/tree/master/Elements/WidthProperties).</span><span class="sxs-lookup"><span data-stu-id="d5f3c-114">For the complete sample, see [Width Properties Comparison Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Elements/WidthProperties).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5f3c-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d5f3c-115">See also</span></span>

- <xref:System.Windows.Controls.ListBox>
- <xref:System.Windows.FrameworkElement>
- <xref:System.Windows.FrameworkElement.ActualWidth%2A>
- <xref:System.Windows.FrameworkElement.MaxWidth%2A>
- <xref:System.Windows.FrameworkElement.MinWidth%2A>
- <xref:System.Windows.FrameworkElement.Width%2A>
- [<span data-ttu-id="d5f3c-116">Cenni preliminari sugli elementi Panel</span><span class="sxs-lookup"><span data-stu-id="d5f3c-116">Panels Overview</span></span>](panels-overview.md)
- [<span data-ttu-id="d5f3c-117">Impostare le proprietà di altezza di un elemento</span><span class="sxs-lookup"><span data-stu-id="d5f3c-117">Set the Height Properties of an Element</span></span>](how-to-set-the-height-properties-of-an-element.md)
- [<span data-ttu-id="d5f3c-118">Esempio di confronto delle proprietà Width</span><span class="sxs-lookup"><span data-stu-id="d5f3c-118">Width Properties Comparison Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Elements/WidthProperties)
