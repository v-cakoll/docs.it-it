---
title: 'Procedura: Modificare il delimitatore alla fine di una linea o di un segmento'
ms.date: 03/30/2017
helpviewer_keywords:
- Shape elements [WPF], ends
- Shape elements [WPF], caps
- graphics [WPF], Shape caps
ms.assetid: f4bf3416-b3d8-4568-b98e-3eda8f6dbf7a
ms.openlocfilehash: 53487417636dae8d855fe70b7b9255351a2dfb1e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69916125"
---
# <a name="how-to-modify-the-cap-at-the-end-of-a-line-or-segment"></a><span data-ttu-id="f25c5-102">Procedura: Modificare il delimitatore alla fine di una linea o di un segmento</span><span class="sxs-lookup"><span data-stu-id="f25c5-102">How to: Modify the Cap at the End of a Line or Segment</span></span>
<span data-ttu-id="f25c5-103">Questo esempio illustra come modificare la forma all'inizio o alla fine di un elemento aperto <xref:System.Windows.Shapes.Shape> .</span><span class="sxs-lookup"><span data-stu-id="f25c5-103">This example shows how to modify the shape at the start or end of an open <xref:System.Windows.Shapes.Shape> element.</span></span> <span data-ttu-id="f25c5-104">Per modificare la terminazione all'inizio di un oggetto <xref:System.Windows.Shapes.Shape>aperto, utilizzare <xref:System.Windows.Shapes.Shape.StrokeStartLineCap%2A> la relativa proprietà.</span><span class="sxs-lookup"><span data-stu-id="f25c5-104">To change the cap at the beginning of an open <xref:System.Windows.Shapes.Shape>, use its <xref:System.Windows.Shapes.Shape.StrokeStartLineCap%2A> property.</span></span> <span data-ttu-id="f25c5-105">Per modificare la terminazione alla fine di un oggetto <xref:System.Windows.Shapes.Shape>aperto, utilizzare <xref:System.Windows.Shapes.Shape.StrokeEndLineCap%2A> la relativa proprietà.</span><span class="sxs-lookup"><span data-stu-id="f25c5-105">To change the cap at the end of an open <xref:System.Windows.Shapes.Shape>, use its <xref:System.Windows.Shapes.Shape.StrokeEndLineCap%2A> property.</span></span> <span data-ttu-id="f25c5-106">Per visualizzare i limiti di riga disponibili, vedere <xref:System.Windows.Media.PenLineCap> l'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="f25c5-106">To view the available line caps, see the <xref:System.Windows.Media.PenLineCap> enumeration.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f25c5-107">Questa proprietà ha effetto solo su una forma aperta, ad <xref:System.Windows.Shapes.Line>esempio un <xref:System.Windows.Shapes.Polyline>oggetto, un oggetto <xref:System.Windows.Shapes.Path> o un elemento aperto.</span><span class="sxs-lookup"><span data-stu-id="f25c5-107">This property only affects an open shape, such as a <xref:System.Windows.Shapes.Line>, a <xref:System.Windows.Shapes.Polyline>, or an open <xref:System.Windows.Shapes.Path> element.</span></span>  
  
 <span data-ttu-id="f25c5-108">Nell'esempio seguente vengono disegnati quattro <xref:System.Windows.Shapes.Polyline> elementi e viene utilizzato un set di forme diverso alle estremità di ogni.</span><span class="sxs-lookup"><span data-stu-id="f25c5-108">The following example draws four <xref:System.Windows.Shapes.Polyline> elements and uses a different set of shapes on the ends of each.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f25c5-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="f25c5-109">Example</span></span>  
 [!code-xaml[drawingwithshapeelements#ShapeLineCaps1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/linecapsandjoinsexample.xaml#shapelinecaps1)]  
  
 <span data-ttu-id="f25c5-110">Questo esempio fa parte di un esempio più ampio; per l'esempio completo, vedere [esempio di elementi Shape](https://go.microsoft.com/fwlink/?LinkID=160037).</span><span class="sxs-lookup"><span data-stu-id="f25c5-110">This example is part of a larger sample; for the complete sample, see [Shape Elements Sample](https://go.microsoft.com/fwlink/?LinkID=160037).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f25c5-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f25c5-111">See also</span></span>

- <xref:System.Windows.Shapes.Polyline>
- <xref:System.Windows.Media.PenLineCap>
