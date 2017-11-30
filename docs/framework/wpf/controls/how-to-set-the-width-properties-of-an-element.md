---
title: "Procedura: impostare le proprietà di larghezza di un elemento"
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
- width properties [WPF]
- Panel control [WPF], width properties of elements
ms.assetid: 6ee04a9d-63f0-4f5b-a406-0a8cd4c35729
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 830289f13ac89601f0d3539e2f4400e56a2476f5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-set-the-width-properties-of-an-element"></a><span data-ttu-id="42b4a-102">Procedura: impostare le proprietà di larghezza di un elemento</span><span class="sxs-lookup"><span data-stu-id="42b4a-102">How to: Set the Width Properties of an Element</span></span>
## <a name="example"></a><span data-ttu-id="42b4a-103">Esempio</span><span class="sxs-lookup"><span data-stu-id="42b4a-103">Example</span></span>  
 <span data-ttu-id="42b4a-104">In questo esempio vengono illustrate le differenze nel comportamento di rendering tra le quattro proprietà correlate alla larghezza in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="42b4a-104">This example visually shows the differences in rendering behavior among the four width-related properties in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].</span></span>  
  
 <span data-ttu-id="42b4a-105">La <xref:System.Windows.FrameworkElement> classe espone quattro proprietà che descrivono le caratteristiche di larghezza di un elemento.</span><span class="sxs-lookup"><span data-stu-id="42b4a-105">The <xref:System.Windows.FrameworkElement> class exposes four properties that describe the width characteristics of an element.</span></span> <span data-ttu-id="42b4a-106">Queste quattro proprietà possono essere in conflitto, e in tal caso, il valore ha la precedenza è determinato come segue: il <xref:System.Windows.FrameworkElement.MinWidth%2A> valore ha la precedenza sul <xref:System.Windows.FrameworkElement.MaxWidth%2A> valore, che a sua volta ha la precedenza sul <xref:System.Windows.FrameworkElement.Width%2A> valore.</span><span class="sxs-lookup"><span data-stu-id="42b4a-106">These four properties can conflict, and when they do, the value that takes precedence is determined as follows: the <xref:System.Windows.FrameworkElement.MinWidth%2A> value takes precedence over the <xref:System.Windows.FrameworkElement.MaxWidth%2A> value, which in turn takes precedence over the <xref:System.Windows.FrameworkElement.Width%2A> value.</span></span> <span data-ttu-id="42b4a-107">Una quarta proprietà <xref:System.Windows.FrameworkElement.ActualWidth%2A>è di sola lettura e la larghezza effettiva determinata dalle interazioni con il processo di layout di report.</span><span class="sxs-lookup"><span data-stu-id="42b4a-107">A fourth property, <xref:System.Windows.FrameworkElement.ActualWidth%2A>, is read-only, and reports the actual width as determined by interactions with the layout process.</span></span>  
  
 <span data-ttu-id="42b4a-108">Nell'esempio [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] esempi disegno un <xref:System.Windows.Shapes.Rectangle> elemento (`rect1`) come figlio di <xref:System.Windows.Controls.Canvas>.</span><span class="sxs-lookup"><span data-stu-id="42b4a-108">The following [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] examples draw a <xref:System.Windows.Shapes.Rectangle> element (`rect1`) as a child of <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="42b4a-109">È possibile modificare le proprietà di larghezza di un <xref:System.Windows.Shapes.Rectangle> mediante una serie di <xref:System.Windows.Controls.ListBox> gli elementi che rappresentano i valori delle proprietà <xref:System.Windows.FrameworkElement.MinWidth%2A>, <xref:System.Windows.FrameworkElement.MaxWidth%2A>, e <xref:System.Windows.FrameworkElement.Width%2A>.</span><span class="sxs-lookup"><span data-stu-id="42b4a-109">You can change the width properties of a <xref:System.Windows.Shapes.Rectangle> by using a series of <xref:System.Windows.Controls.ListBox> elements that represent the property values of <xref:System.Windows.FrameworkElement.MinWidth%2A>, <xref:System.Windows.FrameworkElement.MaxWidth%2A>, and <xref:System.Windows.FrameworkElement.Width%2A>.</span></span> <span data-ttu-id="42b4a-110">In questo modo, viene visualizzata in modo visivo la priorità di ogni proprietà.</span><span class="sxs-lookup"><span data-stu-id="42b4a-110">In this manner, the precedence of each property is visually displayed.</span></span>  
  
 [!code-xaml[WidthMinWidthMaxWidth#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WidthMinWidthMaxWidth/CSharp/Window1.xaml#1)]  
[!code-xaml[WidthMinWidthMaxWidth#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WidthMinWidthMaxWidth/CSharp/Window1.xaml#2)]  
  
 <span data-ttu-id="42b4a-111">Gli esempi di codice seguenti gestiscono gli eventi che il <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> genera eventi.</span><span class="sxs-lookup"><span data-stu-id="42b4a-111">The following code-behind examples handle the events that the <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> event raises.</span></span> <span data-ttu-id="42b4a-112">Ogni metodo personalizzato accetta l'input di <xref:System.Windows.Controls.ListBox>, analizza il valore come un <xref:System.Double>e applica il valore della proprietà correlate alla larghezza specificata.</span><span class="sxs-lookup"><span data-stu-id="42b4a-112">Each custom method takes the input from the <xref:System.Windows.Controls.ListBox>, parses the value as a <xref:System.Double>, and applies the value to the specified width-related property.</span></span> <span data-ttu-id="42b4a-113">I valori di larghezza sono inoltre convertiti in una stringa e scritti nei vari <xref:System.Windows.Controls.TextBlock> elementi (definizione di tali elementi non è illustrato nel codice XAML selezionato).</span><span class="sxs-lookup"><span data-stu-id="42b4a-113">The width values are also converted to a string and written to various <xref:System.Windows.Controls.TextBlock> elements (definition of those elements is not shown in the selected XAML).</span></span>  
  
 [!code-csharp[WidthMinWidthMaxWidth#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WidthMinWidthMaxWidth/CSharp/Window1.xaml.cs#3)]
 [!code-vb[WidthMinWidthMaxWidth#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WidthMinWidthMaxWidth/VisualBasic/Window1.xaml.vb#3)]  
  
 <span data-ttu-id="42b4a-114">Per l'esempio completo, vedere [esempio confronto proprietà Width](http://go.microsoft.com/fwlink/?LinkID=160050).</span><span class="sxs-lookup"><span data-stu-id="42b4a-114">For the complete sample, see [Width Properties Comparison Sample](http://go.microsoft.com/fwlink/?LinkID=160050).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42b4a-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="42b4a-115">See Also</span></span>  
 <xref:System.Windows.Controls.ListBox>  
 <xref:System.Windows.FrameworkElement>  
 <xref:System.Windows.FrameworkElement.ActualWidth%2A>  
 <xref:System.Windows.FrameworkElement.MaxWidth%2A>  
 <xref:System.Windows.FrameworkElement.MinWidth%2A>  
 <xref:System.Windows.FrameworkElement.Width%2A>  
 [<span data-ttu-id="42b4a-116">Cenni preliminari sugli elementi Panel</span><span class="sxs-lookup"><span data-stu-id="42b4a-116">Panels Overview</span></span>](../../../../docs/framework/wpf/controls/panels-overview.md)  
 [<span data-ttu-id="42b4a-117">Impostare le proprietà di altezza di un elemento</span><span class="sxs-lookup"><span data-stu-id="42b4a-117">Set the Height Properties of an Element</span></span>](../../../../docs/framework/wpf/controls/how-to-set-the-height-properties-of-an-element.md)  
 [<span data-ttu-id="42b4a-118">Esempio di confronto di proprietà Width</span><span class="sxs-lookup"><span data-stu-id="42b4a-118">Width Properties Comparison Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=160050)
