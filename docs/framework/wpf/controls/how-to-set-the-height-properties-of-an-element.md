---
title: 'Procedura: impostare le proprietà di altezza di un elemento'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- height properties [WPF]
- Panel control [WPF], height properties of elements
ms.assetid: 5ab9e781-dbb8-469a-a3c8-cf38ce312647
ms.openlocfilehash: 6500af3c637092820e538d79894d600d617953bf
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/11/2020
ms.locfileid: "77124286"
---
# <a name="how-to-set-the-height-properties-of-an-element"></a><span data-ttu-id="011fb-102">Procedura: impostare le proprietà di altezza di un elemento</span><span class="sxs-lookup"><span data-stu-id="011fb-102">How to: Set the Height Properties of an Element</span></span>
## <a name="example"></a><span data-ttu-id="011fb-103">Esempio</span><span class="sxs-lookup"><span data-stu-id="011fb-103">Example</span></span>  
 <span data-ttu-id="011fb-104">Questo esempio mostra visivamente le differenze nel comportamento di rendering tra le quattro proprietà correlate all'altezza in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="011fb-104">This example visually shows the differences in rendering behavior among the four height-related properties in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].</span></span>  
  
 <span data-ttu-id="011fb-105">La classe <xref:System.Windows.FrameworkElement> espone quattro proprietà che descrivono le caratteristiche di altezza di un elemento.</span><span class="sxs-lookup"><span data-stu-id="011fb-105">The <xref:System.Windows.FrameworkElement> class exposes four properties that describe the height characteristics of an element.</span></span> <span data-ttu-id="011fb-106">Queste quattro proprietà possono entrare in conflitto e, quando lo fanno, il valore che ha la precedenza viene determinato nel modo seguente: il valore <xref:System.Windows.FrameworkElement.MinHeight%2A> ha la precedenza sul valore <xref:System.Windows.FrameworkElement.MaxHeight%2A>, che a sua volta ha la precedenza sul valore di <xref:System.Windows.FrameworkElement.Height%2A>.</span><span class="sxs-lookup"><span data-stu-id="011fb-106">These four properties can conflict, and when they do, the value that takes precedence is determined as follows: the <xref:System.Windows.FrameworkElement.MinHeight%2A> value takes precedence over the <xref:System.Windows.FrameworkElement.MaxHeight%2A> value, which in turn takes precedence over the <xref:System.Windows.FrameworkElement.Height%2A> value.</span></span> <span data-ttu-id="011fb-107">Una quarta proprietà, <xref:System.Windows.FrameworkElement.ActualHeight%2A>, è di sola lettura e indica l'altezza effettiva determinata dalle interazioni con il processo di layout.</span><span class="sxs-lookup"><span data-stu-id="011fb-107">A fourth property, <xref:System.Windows.FrameworkElement.ActualHeight%2A>, is read-only, and reports the actual height as determined by interactions with the layout process.</span></span>  
  
 <span data-ttu-id="011fb-108">Negli esempi di [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] seguenti viene disegnato un elemento <xref:System.Windows.Shapes.Rectangle> (`rect1`) come figlio di <xref:System.Windows.Controls.Canvas>.</span><span class="sxs-lookup"><span data-stu-id="011fb-108">The following [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] examples draw a <xref:System.Windows.Shapes.Rectangle> element (`rect1`) as a child of <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="011fb-109">È possibile modificare le proprietà di altezza di un <xref:System.Windows.Shapes.Rectangle> usando una serie di <xref:System.Windows.Controls.ListBox> elementi che rappresentano i valori delle proprietà di <xref:System.Windows.FrameworkElement.MinHeight%2A>, <xref:System.Windows.FrameworkElement.MaxHeight%2A>e <xref:System.Windows.FrameworkElement.Height%2A>.</span><span class="sxs-lookup"><span data-stu-id="011fb-109">You can change the height properties of a <xref:System.Windows.Shapes.Rectangle> by using a series of <xref:System.Windows.Controls.ListBox> elements that represent the property values of <xref:System.Windows.FrameworkElement.MinHeight%2A>, <xref:System.Windows.FrameworkElement.MaxHeight%2A>, and <xref:System.Windows.FrameworkElement.Height%2A>.</span></span> <span data-ttu-id="011fb-110">In questo modo, la precedenza di ogni proprietà viene visualizzata visivamente.</span><span class="sxs-lookup"><span data-stu-id="011fb-110">In this manner, the precedence of each property is visually displayed.</span></span>  
  
 [!code-xaml[HeightMinHeightMaxHeight#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HeightMinHeightMaxHeight/CSharp/Window1.xaml#1)]  
[!code-xaml[HeightMinHeightMaxHeight#2](~/samples/snippets/csharp/VS_Snippets_Wpf/HeightMinHeightMaxHeight/CSharp/Window1.xaml#2)]  
  
 <span data-ttu-id="011fb-111">Gli esempi code-behind seguenti gestiscono gli eventi generati dall'evento <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged>.</span><span class="sxs-lookup"><span data-stu-id="011fb-111">The following code-behind examples handle the events that the <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> event raises.</span></span> <span data-ttu-id="011fb-112">Ogni gestore accetta l'input dalla <xref:System.Windows.Controls.ListBox>, analizza il valore come <xref:System.Double>e applica il valore alla proprietà relativa all'altezza specificata.</span><span class="sxs-lookup"><span data-stu-id="011fb-112">Each handler takes the input from the <xref:System.Windows.Controls.ListBox>, parses the value as a <xref:System.Double>, and applies the value to the specified height-related property.</span></span> <span data-ttu-id="011fb-113">I valori di altezza vengono inoltre convertiti in una stringa e scritti in vari elementi di <xref:System.Windows.Controls.TextBlock> (la definizione di tali elementi non viene visualizzata nel codice XAML selezionato).</span><span class="sxs-lookup"><span data-stu-id="011fb-113">The height values are also converted to a string and written to various <xref:System.Windows.Controls.TextBlock> elements (definition of those elements is not shown in the selected XAML).</span></span>  
  
 [!code-csharp[HeightMinHeightMaxHeight#3](~/samples/snippets/csharp/VS_Snippets_Wpf/HeightMinHeightMaxHeight/CSharp/Window1.xaml.cs#3)]
 [!code-vb[HeightMinHeightMaxHeight#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HeightMinHeightMaxHeight/VisualBasic/Window1.xaml.vb#3)]  
  
 <span data-ttu-id="011fb-114">Per l'esempio completo, vedere [esempio di proprietà Height](https://github.com/microsoft/WPF-Samples/tree/master/Elements/HeightProperties).</span><span class="sxs-lookup"><span data-stu-id="011fb-114">For the complete sample, see [Height Properties Sample](https://github.com/microsoft/WPF-Samples/tree/master/Elements/HeightProperties).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="011fb-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="011fb-115">See also</span></span>

- <xref:System.Windows.FrameworkElement>
- <xref:System.Windows.Controls.ListBox>
- <xref:System.Windows.FrameworkElement.ActualHeight%2A>
- <xref:System.Windows.FrameworkElement.MaxHeight%2A>
- <xref:System.Windows.FrameworkElement.MinHeight%2A>
- <xref:System.Windows.FrameworkElement.Height%2A>
- [<span data-ttu-id="011fb-116">Impostare le proprietà di larghezza di un elemento</span><span class="sxs-lookup"><span data-stu-id="011fb-116">Set the Width Properties of an Element</span></span>](how-to-set-the-width-properties-of-an-element.md)
- [<span data-ttu-id="011fb-117">Cenni preliminari sugli elementi Panel</span><span class="sxs-lookup"><span data-stu-id="011fb-117">Panels Overview</span></span>](panels-overview.md)
- [<span data-ttu-id="011fb-118">Esempio di proprietà Height</span><span class="sxs-lookup"><span data-stu-id="011fb-118">Height Properties Sample</span></span>](https://github.com/microsoft/WPF-Samples/tree/master/Elements/HeightProperties)
