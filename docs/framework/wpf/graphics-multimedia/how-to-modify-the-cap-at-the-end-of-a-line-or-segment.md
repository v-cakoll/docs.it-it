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
# <a name="how-to-modify-the-cap-at-the-end-of-a-line-or-segment"></a>Procedura: modificare la terminazione alla fine di una linea o di un segmento
In questo esempio viene illustrato come modificare la forma all'inizio o alla fine di un elemento Open <xref:System.Windows.Shapes.Shape>. Per modificare il limite all'inizio di un <xref:System.Windows.Shapes.Shape>aperto, utilizzare la relativa proprietà <xref:System.Windows.Shapes.Shape.StrokeStartLineCap%2A>. Per modificare il limite alla fine di un <xref:System.Windows.Shapes.Shape>aperto, utilizzare la relativa proprietà <xref:System.Windows.Shapes.Shape.StrokeEndLineCap%2A>. Per visualizzare i limiti di riga disponibili, vedere l'enumerazione <xref:System.Windows.Media.PenLineCap>.  
  
> [!NOTE]
> Questa proprietà ha effetto solo su una forma aperta, ad esempio un <xref:System.Windows.Shapes.Line>, un <xref:System.Windows.Shapes.Polyline>o un elemento <xref:System.Windows.Shapes.Path> aperto.  
  
 Nell'esempio seguente vengono disegnati quattro elementi <xref:System.Windows.Shapes.Polyline> e viene utilizzato un set di forme diverso alle estremità di ogni.  
  
## <a name="example"></a>Esempio  
 [!code-xaml[drawingwithshapeelements#ShapeLineCaps1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/linecapsandjoinsexample.xaml#shapelinecaps1)]  
  
 Questo esempio fa parte di un esempio più ampio; per l'esempio completo, vedere [esempio di elementi Shape](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Shapes.Polyline>
- <xref:System.Windows.Media.PenLineCap>
