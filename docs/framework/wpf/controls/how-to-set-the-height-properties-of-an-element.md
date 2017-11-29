---
title: "Procedura: impostare le proprietà di altezza di un elemento"
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
- height properties [WPF]
- Panel control [WPF], height properties of elements
ms.assetid: 5ab9e781-dbb8-469a-a3c8-cf38ce312647
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8ae66e60375cfbc45a4f1e8834b6420bc5c0b70a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-set-the-height-properties-of-an-element"></a><span data-ttu-id="5ca4b-102">Procedura: impostare le proprietà di altezza di un elemento</span><span class="sxs-lookup"><span data-stu-id="5ca4b-102">How to: Set the Height Properties of an Element</span></span>
## <a name="example"></a><span data-ttu-id="5ca4b-103">Esempio</span><span class="sxs-lookup"><span data-stu-id="5ca4b-103">Example</span></span>  
 <span data-ttu-id="5ca4b-104">In questo esempio vengono illustrate le differenze nel comportamento di rendering tra le quattro proprietà correlate all'altezza in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5ca4b-104">This example visually shows the differences in rendering behavior among the four height-related properties in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].</span></span>  
  
 <span data-ttu-id="5ca4b-105">La <xref:System.Windows.FrameworkElement> classe espone quattro proprietà che descrivono le caratteristiche dell'altezza di un elemento.</span><span class="sxs-lookup"><span data-stu-id="5ca4b-105">The <xref:System.Windows.FrameworkElement> class exposes four properties that describe the height characteristics of an element.</span></span> <span data-ttu-id="5ca4b-106">Queste quattro proprietà possono essere in conflitto, e in tal caso, il valore ha la precedenza è determinato come segue: il <xref:System.Windows.FrameworkElement.MinHeight%2A> valore ha la precedenza sul <xref:System.Windows.FrameworkElement.MaxHeight%2A> valore, che a sua volta ha la precedenza sul <xref:System.Windows.FrameworkElement.Height%2A> valore.</span><span class="sxs-lookup"><span data-stu-id="5ca4b-106">These four properties can conflict, and when they do, the value that takes precedence is determined as follows: the <xref:System.Windows.FrameworkElement.MinHeight%2A> value takes precedence over the <xref:System.Windows.FrameworkElement.MaxHeight%2A> value, which in turn takes precedence over the <xref:System.Windows.FrameworkElement.Height%2A> value.</span></span> <span data-ttu-id="5ca4b-107">Una quarta proprietà <xref:System.Windows.FrameworkElement.ActualHeight%2A>è di sola lettura e l'altezza effettiva determinata dalle interazioni con il processo di layout di report.</span><span class="sxs-lookup"><span data-stu-id="5ca4b-107">A fourth property, <xref:System.Windows.FrameworkElement.ActualHeight%2A>, is read-only, and reports the actual height as determined by interactions with the layout process.</span></span>  
  
 <span data-ttu-id="5ca4b-108">Nell'esempio [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] esempi disegno un <xref:System.Windows.Shapes.Rectangle> elemento (`rect1`) come figlio di <xref:System.Windows.Controls.Canvas>.</span><span class="sxs-lookup"><span data-stu-id="5ca4b-108">The following [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] examples draw a <xref:System.Windows.Shapes.Rectangle> element (`rect1`) as a child of <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="5ca4b-109">È possibile modificare le proprietà di altezza di un <xref:System.Windows.Shapes.Rectangle> mediante una serie di <xref:System.Windows.Controls.ListBox> gli elementi che rappresentano i valori delle proprietà <xref:System.Windows.FrameworkElement.MinHeight%2A>, <xref:System.Windows.FrameworkElement.MaxHeight%2A>, e <xref:System.Windows.FrameworkElement.Height%2A>.</span><span class="sxs-lookup"><span data-stu-id="5ca4b-109">You can change the height properties of a <xref:System.Windows.Shapes.Rectangle> by using a series of <xref:System.Windows.Controls.ListBox> elements that represent the property values of <xref:System.Windows.FrameworkElement.MinHeight%2A>, <xref:System.Windows.FrameworkElement.MaxHeight%2A>, and <xref:System.Windows.FrameworkElement.Height%2A>.</span></span> <span data-ttu-id="5ca4b-110">In questo modo, viene visualizzata in modo visivo la priorità di ogni proprietà.</span><span class="sxs-lookup"><span data-stu-id="5ca4b-110">In this manner, the precedence of each property is visually displayed.</span></span>  
  
 [!code-xaml[HeightMinHeightMaxHeight#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HeightMinHeightMaxHeight/CSharp/Window1.xaml#1)]  
[!code-xaml[HeightMinHeightMaxHeight#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HeightMinHeightMaxHeight/CSharp/Window1.xaml#2)]  
  
 <span data-ttu-id="5ca4b-111">Gli esempi di codice seguenti gestiscono gli eventi che il <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> genera eventi.</span><span class="sxs-lookup"><span data-stu-id="5ca4b-111">The following code-behind examples handle the events that the <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> event raises.</span></span> <span data-ttu-id="5ca4b-112">Ogni gestore accetta l'input di <xref:System.Windows.Controls.ListBox>, analizza il valore come un <xref:System.Double>e applica il valore della proprietà correlate altezza specificata.</span><span class="sxs-lookup"><span data-stu-id="5ca4b-112">Each handler takes the input from the <xref:System.Windows.Controls.ListBox>, parses the value as a <xref:System.Double>, and applies the value to the specified height-related property.</span></span> <span data-ttu-id="5ca4b-113">I valori di altezza vengono inoltre convertiti in una stringa e scritti nei vari <xref:System.Windows.Controls.TextBlock> elementi (definizione di tali elementi non è illustrato nel codice XAML selezionato).</span><span class="sxs-lookup"><span data-stu-id="5ca4b-113">The height values are also converted to a string and written to various <xref:System.Windows.Controls.TextBlock> elements (definition of those elements is not shown in the selected XAML).</span></span>  
  
 [!code-csharp[HeightMinHeightMaxHeight#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HeightMinHeightMaxHeight/CSharp/Window1.xaml.cs#3)]
 [!code-vb[HeightMinHeightMaxHeight#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HeightMinHeightMaxHeight/VisualBasic/Window1.xaml.vb#3)]  
  
 <span data-ttu-id="5ca4b-114">Per l'esempio completo, vedere [esempio di proprietà di altezza](http://go.microsoft.com/fwlink/?LinkID=159993).</span><span class="sxs-lookup"><span data-stu-id="5ca4b-114">For the complete sample, see [Height Properties Sample](http://go.microsoft.com/fwlink/?LinkID=159993).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ca4b-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5ca4b-115">See Also</span></span>  
 <xref:System.Windows.FrameworkElement>  
 <xref:System.Windows.Controls.ListBox>  
 <xref:System.Windows.FrameworkElement.ActualHeight%2A>  
 <xref:System.Windows.FrameworkElement.MaxHeight%2A>  
 <xref:System.Windows.FrameworkElement.MinHeight%2A>  
 <xref:System.Windows.FrameworkElement.Height%2A>  
 [<span data-ttu-id="5ca4b-116">Impostare le proprietà di larghezza di un elemento</span><span class="sxs-lookup"><span data-stu-id="5ca4b-116">Set the Width Properties of an Element</span></span>](../../../../docs/framework/wpf/controls/how-to-set-the-width-properties-of-an-element.md)  
 [<span data-ttu-id="5ca4b-117">Cenni preliminari sugli elementi Panel</span><span class="sxs-lookup"><span data-stu-id="5ca4b-117">Panels Overview</span></span>](../../../../docs/framework/wpf/controls/panels-overview.md)  
 [<span data-ttu-id="5ca4b-118">Esempio di proprietà di altezza</span><span class="sxs-lookup"><span data-stu-id="5ca4b-118">Height Properties Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=159993)
