---
title: 'Procedura: Modificare il delimitatore alla fine di una linea o di un segmento'
ms.date: 03/30/2017
helpviewer_keywords:
- Shape elements [WPF], ends
- Shape elements [WPF], caps
- graphics [WPF], Shape caps
ms.assetid: f4bf3416-b3d8-4568-b98e-3eda8f6dbf7a
ms.openlocfilehash: 462e32520393a1c23809cce8eb3c130c13bc882f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59091304"
---
# <a name="how-to-modify-the-cap-at-the-end-of-a-line-or-segment"></a><span data-ttu-id="4d957-102">Procedura: Modificare il delimitatore alla fine di una linea o di un segmento</span><span class="sxs-lookup"><span data-stu-id="4d957-102">How to: Modify the Cap at the End of a Line or Segment</span></span>
<span data-ttu-id="4d957-103">Questo esempio viene illustrato come modificare la forma all'inizio o alla fine di un elemento aperto <xref:System.Windows.Shapes.Shape> elemento.</span><span class="sxs-lookup"><span data-stu-id="4d957-103">This example shows how to modify the shape at the start or end of an open <xref:System.Windows.Shapes.Shape> element.</span></span> <span data-ttu-id="4d957-104">Per modificare il limite all'inizio di un oggetto aperto <xref:System.Windows.Shapes.Shape>, usare il <xref:System.Windows.Shapes.Shape.StrokeStartLineCap%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="4d957-104">To change the cap at the beginning of an open <xref:System.Windows.Shapes.Shape>, use its <xref:System.Windows.Shapes.Shape.StrokeStartLineCap%2A> property.</span></span> <span data-ttu-id="4d957-105">Per modificare il delimitatore alla fine di un oggetto aperto <xref:System.Windows.Shapes.Shape>, usare il <xref:System.Windows.Shapes.Shape.StrokeEndLineCap%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="4d957-105">To change the cap at the end of an open <xref:System.Windows.Shapes.Shape>, use its <xref:System.Windows.Shapes.Shape.StrokeEndLineCap%2A> property.</span></span> <span data-ttu-id="4d957-106">Per visualizzare le terminazioni riga disponibili, vedere il <xref:System.Windows.Media.PenLineCap> enumerazione.</span><span class="sxs-lookup"><span data-stu-id="4d957-106">To view the available line caps, see the <xref:System.Windows.Media.PenLineCap> enumeration.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4d957-107">Questa proprietà influisce solo su una forma aperta, ad esempio un <xref:System.Windows.Shapes.Line>, una <xref:System.Windows.Shapes.Polyline>, o un elemento aperto <xref:System.Windows.Shapes.Path> elemento.</span><span class="sxs-lookup"><span data-stu-id="4d957-107">This property only affects an open shape, such as a <xref:System.Windows.Shapes.Line>, a <xref:System.Windows.Shapes.Polyline>, or an open <xref:System.Windows.Shapes.Path> element.</span></span>  
  
 <span data-ttu-id="4d957-108">L'esempio seguente disegna quattro <xref:System.Windows.Shapes.Polyline> elementi e Usa un set diverso di forme alle estremità della ognuno.</span><span class="sxs-lookup"><span data-stu-id="4d957-108">The following example draws four <xref:System.Windows.Shapes.Polyline> elements and uses a different set of shapes on the ends of each.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4d957-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="4d957-109">Example</span></span>  
 [!code-xaml[drawingwithshapeelements#ShapeLineCaps1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/linecapsandjoinsexample.xaml#shapelinecaps1)]  
  
 <span data-ttu-id="4d957-110">In questo esempio fa parte di un esempio più esaustivo; per l'esempio completo, vedere [esempio di elementi forma](https://go.microsoft.com/fwlink/?LinkID=160037).</span><span class="sxs-lookup"><span data-stu-id="4d957-110">This example is part of a larger sample; for the complete sample, see [Shape Elements Sample](https://go.microsoft.com/fwlink/?LinkID=160037).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d957-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4d957-111">See also</span></span>

- <xref:System.Windows.Shapes.Polyline>
- <xref:System.Windows.Media.PenLineCap>
