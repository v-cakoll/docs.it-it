---
title: 'Procedura: modificare la terminazione alla fine di una linea o di un segmento'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Shape elements [WPF], ends
- Shape elements [WPF], caps
- graphics [WPF], Shape caps
ms.assetid: f4bf3416-b3d8-4568-b98e-3eda8f6dbf7a
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e062b82e698a99705a2b06588aa9aae3a0c93157
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-modify-the-cap-at-the-end-of-a-line-or-segment"></a><span data-ttu-id="ee942-102">Procedura: modificare la terminazione alla fine di una linea o di un segmento</span><span class="sxs-lookup"><span data-stu-id="ee942-102">How to: Modify the Cap at the End of a Line or Segment</span></span>
<span data-ttu-id="ee942-103">In questo esempio viene illustrato come modificare la forma all'inizio o alla fine di un elemento aperto <xref:System.Windows.Shapes.Shape> elemento.</span><span class="sxs-lookup"><span data-stu-id="ee942-103">This example shows how to modify the shape at the start or end of an open <xref:System.Windows.Shapes.Shape> element.</span></span> <span data-ttu-id="ee942-104">Per modificare la terminazione all'inizio di un oggetto aperto <xref:System.Windows.Shapes.Shape>, utilizzare il relativo <xref:System.Windows.Shapes.Shape.StrokeStartLineCap%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="ee942-104">To change the cap at the beginning of an open <xref:System.Windows.Shapes.Shape>, use its <xref:System.Windows.Shapes.Shape.StrokeStartLineCap%2A> property.</span></span> <span data-ttu-id="ee942-105">Per modificare la terminazione alla fine di un oggetto aperto <xref:System.Windows.Shapes.Shape>, utilizzare il relativo <xref:System.Windows.Shapes.Shape.StrokeEndLineCap%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="ee942-105">To change the cap at the end of an open <xref:System.Windows.Shapes.Shape>, use its <xref:System.Windows.Shapes.Shape.StrokeEndLineCap%2A> property.</span></span> <span data-ttu-id="ee942-106">Per visualizzare le terminazioni riga disponibili, vedere il <xref:System.Windows.Media.PenLineCap> enumerazione.</span><span class="sxs-lookup"><span data-stu-id="ee942-106">To view the available line caps, see the <xref:System.Windows.Media.PenLineCap> enumeration.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ee942-107">Questa proprietà influisce solo una forma aperta, ad esempio un <xref:System.Windows.Shapes.Line>, <xref:System.Windows.Shapes.Polyline>, open o <xref:System.Windows.Shapes.Path> elemento.</span><span class="sxs-lookup"><span data-stu-id="ee942-107">This property only affects an open shape, such as a <xref:System.Windows.Shapes.Line>, a <xref:System.Windows.Shapes.Polyline>, or an open <xref:System.Windows.Shapes.Path> element.</span></span>  
  
 <span data-ttu-id="ee942-108">Nell'esempio seguente disegna quattro <xref:System.Windows.Shapes.Polyline> elementi e viene utilizzato un set diverso di forme alle estremità di ogni.</span><span class="sxs-lookup"><span data-stu-id="ee942-108">The following example draws four <xref:System.Windows.Shapes.Polyline> elements and uses a different set of shapes on the ends of each.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ee942-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="ee942-109">Example</span></span>  
 [!code-xaml[drawingwithshapeelements#ShapeLineCaps1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/linecapsandjoinsexample.xaml#shapelinecaps1)]  
  
 <span data-ttu-id="ee942-110">In questo esempio fa parte di un esempio più ampio; per l'esempio completo, vedere [esempio di elementi forma](http://go.microsoft.com/fwlink/?LinkID=160037).</span><span class="sxs-lookup"><span data-stu-id="ee942-110">This example is part of a larger sample; for the complete sample, see [Shape Elements Sample](http://go.microsoft.com/fwlink/?LinkID=160037).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee942-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ee942-111">See Also</span></span>  
 <xref:System.Windows.Shapes.Polyline>  
 <xref:System.Windows.Media.PenLineCap>
