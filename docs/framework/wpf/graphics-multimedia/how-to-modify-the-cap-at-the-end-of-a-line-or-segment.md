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
