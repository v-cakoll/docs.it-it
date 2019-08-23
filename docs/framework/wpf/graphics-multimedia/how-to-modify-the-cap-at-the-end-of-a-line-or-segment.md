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
# <a name="how-to-modify-the-cap-at-the-end-of-a-line-or-segment"></a>Procedura: Modificare il delimitatore alla fine di una linea o di un segmento
Questo esempio illustra come modificare la forma all'inizio o alla fine di un elemento aperto <xref:System.Windows.Shapes.Shape> . Per modificare la terminazione all'inizio di un oggetto <xref:System.Windows.Shapes.Shape>aperto, utilizzare <xref:System.Windows.Shapes.Shape.StrokeStartLineCap%2A> la relativa proprietà. Per modificare la terminazione alla fine di un oggetto <xref:System.Windows.Shapes.Shape>aperto, utilizzare <xref:System.Windows.Shapes.Shape.StrokeEndLineCap%2A> la relativa proprietà. Per visualizzare i limiti di riga disponibili, vedere <xref:System.Windows.Media.PenLineCap> l'enumerazione.  
  
> [!NOTE]
> Questa proprietà ha effetto solo su una forma aperta, ad <xref:System.Windows.Shapes.Line>esempio un <xref:System.Windows.Shapes.Polyline>oggetto, un oggetto <xref:System.Windows.Shapes.Path> o un elemento aperto.  
  
 Nell'esempio seguente vengono disegnati quattro <xref:System.Windows.Shapes.Polyline> elementi e viene utilizzato un set di forme diverso alle estremità di ogni.  
  
## <a name="example"></a>Esempio  
 [!code-xaml[drawingwithshapeelements#ShapeLineCaps1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/linecapsandjoinsexample.xaml#shapelinecaps1)]  
  
 Questo esempio fa parte di un esempio più ampio; per l'esempio completo, vedere [esempio di elementi Shape](https://go.microsoft.com/fwlink/?LinkID=160037).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Shapes.Polyline>
- <xref:System.Windows.Media.PenLineCap>
