---
title: 'Procedura: modificare la terminazione alla fine di una linea o di un segmento'
ms.date: 03/30/2017
helpviewer_keywords:
- Shape elements [WPF], ends
- Shape elements [WPF], caps
- graphics [WPF], Shape caps
ms.assetid: f4bf3416-b3d8-4568-b98e-3eda8f6dbf7a
ms.openlocfilehash: 5f755d7b4d1682755ea461121f91c0666d450ad1
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452779"
---
# <a name="how-to-modify-the-cap-at-the-end-of-a-line-or-segment"></a><span data-ttu-id="67a81-102">Procedura: modificare la terminazione alla fine di una linea o di un segmento</span><span class="sxs-lookup"><span data-stu-id="67a81-102">How to: Modify the Cap at the End of a Line or Segment</span></span>
<span data-ttu-id="67a81-103">In questo esempio viene illustrato come modificare la forma all'inizio o alla fine di un elemento Open <xref:System.Windows.Shapes.Shape>.</span><span class="sxs-lookup"><span data-stu-id="67a81-103">This example shows how to modify the shape at the start or end of an open <xref:System.Windows.Shapes.Shape> element.</span></span> <span data-ttu-id="67a81-104">Per modificare il limite all'inizio di un <xref:System.Windows.Shapes.Shape>aperto, utilizzare la relativa proprietà <xref:System.Windows.Shapes.Shape.StrokeStartLineCap%2A>.</span><span class="sxs-lookup"><span data-stu-id="67a81-104">To change the cap at the beginning of an open <xref:System.Windows.Shapes.Shape>, use its <xref:System.Windows.Shapes.Shape.StrokeStartLineCap%2A> property.</span></span> <span data-ttu-id="67a81-105">Per modificare il limite alla fine di un <xref:System.Windows.Shapes.Shape>aperto, utilizzare la relativa proprietà <xref:System.Windows.Shapes.Shape.StrokeEndLineCap%2A>.</span><span class="sxs-lookup"><span data-stu-id="67a81-105">To change the cap at the end of an open <xref:System.Windows.Shapes.Shape>, use its <xref:System.Windows.Shapes.Shape.StrokeEndLineCap%2A> property.</span></span> <span data-ttu-id="67a81-106">Per visualizzare i limiti di riga disponibili, vedere l'enumerazione <xref:System.Windows.Media.PenLineCap>.</span><span class="sxs-lookup"><span data-stu-id="67a81-106">To view the available line caps, see the <xref:System.Windows.Media.PenLineCap> enumeration.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="67a81-107">Questa proprietà ha effetto solo su una forma aperta, ad esempio un <xref:System.Windows.Shapes.Line>, un <xref:System.Windows.Shapes.Polyline>o un elemento <xref:System.Windows.Shapes.Path> aperto.</span><span class="sxs-lookup"><span data-stu-id="67a81-107">This property only affects an open shape, such as a <xref:System.Windows.Shapes.Line>, a <xref:System.Windows.Shapes.Polyline>, or an open <xref:System.Windows.Shapes.Path> element.</span></span>  
  
 <span data-ttu-id="67a81-108">Nell'esempio seguente vengono disegnati quattro elementi <xref:System.Windows.Shapes.Polyline> e viene utilizzato un set di forme diverso alle estremità di ogni.</span><span class="sxs-lookup"><span data-stu-id="67a81-108">The following example draws four <xref:System.Windows.Shapes.Polyline> elements and uses a different set of shapes on the ends of each.</span></span>  
  
## <a name="example"></a><span data-ttu-id="67a81-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="67a81-109">Example</span></span>  
 [!code-xaml[drawingwithshapeelements#ShapeLineCaps1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/linecapsandjoinsexample.xaml#shapelinecaps1)]  
  
 <span data-ttu-id="67a81-110">Questo esempio fa parte di un esempio più ampio; per l'esempio completo, vedere [esempio di elementi Shape](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements).</span><span class="sxs-lookup"><span data-stu-id="67a81-110">This example is part of a larger sample; for the complete sample, see [Shape Elements Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67a81-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="67a81-111">See also</span></span>

- <xref:System.Windows.Shapes.Polyline>
- <xref:System.Windows.Media.PenLineCap>
