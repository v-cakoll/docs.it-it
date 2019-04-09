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
# <a name="how-to-modify-the-cap-at-the-end-of-a-line-or-segment"></a>Procedura: Modificare il delimitatore alla fine di una linea o di un segmento
Questo esempio viene illustrato come modificare la forma all'inizio o alla fine di un elemento aperto <xref:System.Windows.Shapes.Shape> elemento. Per modificare il limite all'inizio di un oggetto aperto <xref:System.Windows.Shapes.Shape>, usare il <xref:System.Windows.Shapes.Shape.StrokeStartLineCap%2A> proprietà. Per modificare il delimitatore alla fine di un oggetto aperto <xref:System.Windows.Shapes.Shape>, usare il <xref:System.Windows.Shapes.Shape.StrokeEndLineCap%2A> proprietà. Per visualizzare le terminazioni riga disponibili, vedere il <xref:System.Windows.Media.PenLineCap> enumerazione.  
  
> [!NOTE]
>  Questa proprietà influisce solo su una forma aperta, ad esempio un <xref:System.Windows.Shapes.Line>, una <xref:System.Windows.Shapes.Polyline>, o un elemento aperto <xref:System.Windows.Shapes.Path> elemento.  
  
 L'esempio seguente disegna quattro <xref:System.Windows.Shapes.Polyline> elementi e Usa un set diverso di forme alle estremità della ognuno.  
  
## <a name="example"></a>Esempio  
 [!code-xaml[drawingwithshapeelements#ShapeLineCaps1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/linecapsandjoinsexample.xaml#shapelinecaps1)]  
  
 In questo esempio fa parte di un esempio più esaustivo; per l'esempio completo, vedere [esempio di elementi forma](https://go.microsoft.com/fwlink/?LinkID=160037).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Shapes.Polyline>
- <xref:System.Windows.Media.PenLineCap>
