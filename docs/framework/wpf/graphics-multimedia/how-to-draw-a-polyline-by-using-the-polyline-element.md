---
title: 'Procedura: disegnare una polilinea utilizzando l''elemento polilinea'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- connected lines [WPF]
- polylines [WPF], drawing
- graphics [WPF], polylines
- lines [WPF], connected (see polylines)
- drawing [WPF], polylines
ms.assetid: 65db8935-d047-4295-87c4-b427ff3ad293
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9b0b027aa34b310413fa02e81149292fabb40f79
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-draw-a-polyline-by-using-the-polyline-element"></a>Procedura: disegnare una polilinea utilizzando l'elemento polilinea
In questo esempio viene illustrato come disegnare una polilinea, ovvero una serie di linee collegate, utilizzando il <xref:System.Windows.Shapes.Polyline> elemento.  
  
 Per disegnare una polilinea, creare un <xref:System.Windows.Shapes.Polyline> elemento e utilizzare il relativo <xref:System.Windows.Shapes.Polyline.Points%2A> proprietà per specificare i vertici della forma. Infine, utilizzare il <xref:System.Windows.Shapes.Shape.Stroke%2A> e <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> per descrivere la polilinea spiegare perché una riga senza tratto è invisibile.  
  
> [!NOTE]
>  Poiché il <xref:System.Windows.Shapes.Polyline> l'elemento non è una forma chiusa, la <xref:System.Windows.Shapes.Shape.Fill%2A> proprietà ha effetto, anche se si chiude intenzionalmente il contorno della forma. Per creare una forma chiusa con un <xref:System.Windows.Shapes.Shape.Fill%2A>, utilizzare un <xref:System.Windows.Shapes.Polygon> elemento.  
  
 Nell'esempio seguente disegna due <xref:System.Windows.Shapes.Polyline> elementi all'interno di un <xref:System.Windows.Controls.Canvas>.  
  
## <a name="example"></a>Esempio  
 In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], la sintassi valida per i punti di è un elenco delimitato da virgole di coppie di coordinate x e y separate da virgole.  
  
 [!code-xaml[drawingwithshapeelements#PolylineExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/polylineexample.xaml#polylineexample1)]  
  
 Sebbene questo esempio viene utilizzato un <xref:System.Windows.Controls.Canvas> per contenere la polilinea, è possibile utilizzare elementi polilinea (e tutti gli altri elementi forma) con qualsiasi <xref:System.Windows.Controls.Panel> o <xref:System.Windows.Controls.Control> che supporta il contenuto non di testo.  
  
 In questo esempio fa parte di un esempio più ampio; per l'esempio completo, vedere [esempio di elementi forma](http://go.microsoft.com/fwlink/?LinkID=160037).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Shapes.Polyline>  
 <xref:System.Windows.Shapes.Polygon>  
 <xref:System.Windows.Shapes.Shape>  
 [Esempio di elementi forma](http://go.microsoft.com/fwlink/?LinkID=160037)  
 [Cenni preliminari sugli oggetti Shape e sulle funzionalità di disegno di base di WPF](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)
