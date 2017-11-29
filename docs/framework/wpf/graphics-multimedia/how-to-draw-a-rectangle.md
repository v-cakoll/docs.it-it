---
title: 'Procedura: disegnare un rettangolo'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- drawing [WPF], rectangles
- graphics [WPF], rectangles
- rectangles [WPF], drawing
ms.assetid: beeb57ef-fab5-4446-a38a-1588f97b4c2f
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4c163897af27c9b34c8cd87a3b197047f86d21ab
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-draw-a-rectangle"></a><span data-ttu-id="97914-102">Procedura: disegnare un rettangolo</span><span class="sxs-lookup"><span data-stu-id="97914-102">How to: Draw a Rectangle</span></span>
<span data-ttu-id="97914-103">In questo esempio viene illustrato come disegnare un rettangolo utilizzando il <xref:System.Windows.Shapes.Rectangle> elemento.</span><span class="sxs-lookup"><span data-stu-id="97914-103">This example shows how to draw a rectangle by using the <xref:System.Windows.Shapes.Rectangle> element.</span></span>  
  
 <span data-ttu-id="97914-104">Per disegnare un rettangolo, creare un <xref:System.Windows.Shapes.Rectangle> elemento e specificare il relativo <xref:System.Windows.FrameworkElement.Width%2A> e <xref:System.Windows.FrameworkElement.Height%2A>.</span><span class="sxs-lookup"><span data-stu-id="97914-104">To draw a rectangle, create a <xref:System.Windows.Shapes.Rectangle> element and specify its <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A>.</span></span> <span data-ttu-id="97914-105">Per disegnare l'interno del rettangolo, impostare il relativo <xref:System.Windows.Shapes.Shape.Fill%2A>.</span><span class="sxs-lookup"><span data-stu-id="97914-105">To paint the inside of the rectangle, set its <xref:System.Windows.Shapes.Shape.Fill%2A>.</span></span> <span data-ttu-id="97914-106">Per assegnare il rettangolo di una struttura, utilizzare il relativo <xref:System.Windows.Shapes.Shape.Stroke%2A> e <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="97914-106">To give the rectangle an outline, use its <xref:System.Windows.Shapes.Shape.Stroke%2A> and <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> properties.</span></span>  
  
 <span data-ttu-id="97914-107">Per impostare il rettangolo angoli arrotondati, specificare l'opzione facoltativa <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> e <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="97914-107">To give the rectangle rounded corners, specify the optional <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> and <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> properties.</span></span> <span data-ttu-id="97914-108">Il <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> e <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> impostano i raggi di assi x e y dell'ellisse utilizzata per arrotondare gli angoli del rettangolo.</span><span class="sxs-lookup"><span data-stu-id="97914-108">The <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> and <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> properties set the x-axis and y-axis radii of the ellipse that is used to round the corners of the rectangle.</span></span>  
  
 <span data-ttu-id="97914-109">Nell'esempio seguente, due <xref:System.Windows.Shapes.Rectangle> vengono disegnati gli elementi in un <xref:System.Windows.Controls.Canvas>.</span><span class="sxs-lookup"><span data-stu-id="97914-109">In the following example, two <xref:System.Windows.Shapes.Rectangle> elements are drawn in a <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="97914-110">Il primo rettangolo ha un <xref:System.Windows.Media.Brushes.Blue%2A> interni.</span><span class="sxs-lookup"><span data-stu-id="97914-110">The first rectangle has a <xref:System.Windows.Media.Brushes.Blue%2A> interior.</span></span> <span data-ttu-id="97914-111">Il secondo rettangolo ha un <xref:System.Windows.Media.Brushes.Blue%2A> interno, un <xref:System.Windows.Media.Brushes.Black%2A> struttura e gli angoli arrotondati.</span><span class="sxs-lookup"><span data-stu-id="97914-111">The second rectangle has a <xref:System.Windows.Media.Brushes.Blue%2A> interior, a <xref:System.Windows.Media.Brushes.Black%2A> outline, and rounded corners.</span></span>  
  
## <a name="example"></a><span data-ttu-id="97914-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="97914-112">Example</span></span>  
 [!code-xaml[drawingwithshapeelements#Rectangle1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/rectangleexample.xaml#rectangle1)]  
  
 <span data-ttu-id="97914-113">Sebbene questo esempio viene utilizzato un <xref:System.Windows.Controls.Canvas> per contenere i rettangoli, è possibile utilizzare gli elementi rettangolo (e tutti gli altri elementi forma) con qualsiasi <xref:System.Windows.Controls.Panel> o <xref:System.Windows.Controls.Control> che supporta il contenuto non di testo.</span><span class="sxs-lookup"><span data-stu-id="97914-113">Although this example uses a <xref:System.Windows.Controls.Canvas> to contain the rectangles, you can use rectangle elements (and all the other shape elements) with any <xref:System.Windows.Controls.Panel> or <xref:System.Windows.Controls.Control> that supports non-text content.</span></span> <span data-ttu-id="97914-114">Infatti, i rettangoli sono particolarmente utili per fornire gli sfondi delle parti di <xref:System.Windows.Controls.Grid> pannelli.</span><span class="sxs-lookup"><span data-stu-id="97914-114">In fact, rectangles are particularly useful for providing backgrounds for portions of <xref:System.Windows.Controls.Grid> panels.</span></span> <span data-ttu-id="97914-115">Per un esempio, vedere il [Cenni preliminari su tabella](../../../../docs/framework/wpf/advanced/table-overview.md).</span><span class="sxs-lookup"><span data-stu-id="97914-115">For an example, see the [Table Overview](../../../../docs/framework/wpf/advanced/table-overview.md).</span></span>  
  
 <span data-ttu-id="97914-116">In questo esempio fa parte di un esempio più ampio; per l'esempio completo, vedere [esempio di elementi forma](http://go.microsoft.com/fwlink/?LinkID=160037).</span><span class="sxs-lookup"><span data-stu-id="97914-116">This example is part of a larger sample; for the complete sample, see [Shape Elements Sample](http://go.microsoft.com/fwlink/?LinkID=160037).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97914-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="97914-117">See Also</span></span>  
 <xref:System.Windows.Shapes.Rectangle>  
 [<span data-ttu-id="97914-118">Esempio di elementi forma</span><span class="sxs-lookup"><span data-stu-id="97914-118">Shape Elements Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=160037)  
 [<span data-ttu-id="97914-119">Cenni preliminari sugli oggetti Shape e sulle funzionalità di disegno di base di WPF</span><span class="sxs-lookup"><span data-stu-id="97914-119">Shapes and Basic Drawing in WPF Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)  
 [<span data-ttu-id="97914-120">Cenni preliminari sull'elemento Table</span><span class="sxs-lookup"><span data-stu-id="97914-120">Table Overview</span></span>](../../../../docs/framework/wpf/advanced/table-overview.md)
