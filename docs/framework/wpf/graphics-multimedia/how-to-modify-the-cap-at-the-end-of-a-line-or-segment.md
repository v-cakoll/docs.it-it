---
title: 'Procedura: modificare la terminazione alla fine di una linea o di un segmento'
ms.date: 03/30/2017
helpviewer_keywords:
- Shape elements [WPF], ends
- Shape elements [WPF], caps
- graphics [WPF], Shape caps
ms.assetid: f4bf3416-b3d8-4568-b98e-3eda8f6dbf7a
ms.openlocfilehash: e69f461d426fc6a587263cea7a18478da53b5b09
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-modify-the-cap-at-the-end-of-a-line-or-segment"></a>Procedura: modificare la terminazione alla fine di una linea o di un segmento
In questo esempio viene illustrato come modificare la forma all'inizio o alla fine di un elemento aperto <xref:System.Windows.Shapes.Shape> elemento. Per modificare la terminazione all'inizio di un oggetto aperto <xref:System.Windows.Shapes.Shape>, utilizzare il relativo <xref:System.Windows.Shapes.Shape.StrokeStartLineCap%2A> proprietà. Per modificare la terminazione alla fine di un oggetto aperto <xref:System.Windows.Shapes.Shape>, utilizzare il relativo <xref:System.Windows.Shapes.Shape.StrokeEndLineCap%2A> proprietà. Per visualizzare le terminazioni riga disponibili, vedere il <xref:System.Windows.Media.PenLineCap> enumerazione.  
  
> [!NOTE]
>  Questa proprietà influisce solo una forma aperta, ad esempio un <xref:System.Windows.Shapes.Line>, <xref:System.Windows.Shapes.Polyline>, open o <xref:System.Windows.Shapes.Path> elemento.  
  
 Nell'esempio seguente disegna quattro <xref:System.Windows.Shapes.Polyline> elementi e viene utilizzato un set diverso di forme alle estremità di ogni.  
  
## <a name="example"></a>Esempio  
 [!code-xaml[drawingwithshapeelements#ShapeLineCaps1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/linecapsandjoinsexample.xaml#shapelinecaps1)]  
  
 In questo esempio fa parte di un esempio più ampio; per l'esempio completo, vedere [esempio di elementi forma](http://go.microsoft.com/fwlink/?LinkID=160037).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Shapes.Polyline>  
 <xref:System.Windows.Media.PenLineCap>
