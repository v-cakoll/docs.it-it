---
title: "Procedura: disegnare una polilinea utilizzando l'elemento polilinea"
ms.date: 03/30/2017
helpviewer_keywords:
- connected lines [WPF]
- polylines [WPF], drawing
- graphics [WPF], polylines
- lines [WPF], connected (see polylines)
- drawing [WPF], polylines
ms.assetid: 65db8935-d047-4295-87c4-b427ff3ad293
ms.openlocfilehash: d065d3cead1ed9746a9615ce2bb6d3ec4cbd614d
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2018
ms.locfileid: "43855430"
---
# <a name="how-to-draw-a-polyline-by-using-the-polyline-element"></a>Procedura: disegnare una polilinea utilizzando l'elemento polilinea
Questo esempio illustra come disegnare una polilinea, ovvero una serie di linee collegate, usando il <xref:System.Windows.Shapes.Polyline> elemento.  
  
 Per disegnare una polilinea, creare un <xref:System.Windows.Shapes.Polyline> elemento e utilizzo relativi <xref:System.Windows.Shapes.Polyline.Points%2A> proprietà per specificare i vertici della forma. Infine, usare il <xref:System.Windows.Shapes.Shape.Stroke%2A> e <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> definite dalle proprietà che descrivono la polilinea perché non è visibile una riga senza un tratto.  
  
> [!NOTE]
>  Poiché il <xref:System.Windows.Shapes.Polyline> elemento non è una forma chiusa, il <xref:System.Windows.Shapes.Shape.Fill%2A> proprietà non ha alcun effetto, anche se si chiude intenzionalmente il contorno della forma. Per creare una forma chiusa con un <xref:System.Windows.Shapes.Shape.Fill%2A>, usare un <xref:System.Windows.Shapes.Polygon> elemento.  
  
 L'esempio seguente disegna due <xref:System.Windows.Shapes.Polyline> elementi all'interno di un <xref:System.Windows.Controls.Canvas>.  
  
## <a name="example"></a>Esempio  
 In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], le sintassi valide per i punti di sono un elenco delimitato da spazi di coppie di coordinate x e y separate da virgole.  
  
 [!code-xaml[drawingwithshapeelements#PolylineExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/polylineexample.xaml#polylineexample1)]  
  
 Sebbene questo esempio Usa un' <xref:System.Windows.Controls.Canvas> per contenere le polilinee, è possibile usare gli elementi polyline (e tutti gli altri elementi forma) con qualsiasi <xref:System.Windows.Controls.Panel> o <xref:System.Windows.Controls.Control> che supporta il contenuto non di testo.  
  
 In questo esempio fa parte di un esempio più esaustivo; per l'esempio completo, vedere [esempio di elementi forma](https://go.microsoft.com/fwlink/?LinkID=160037).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Shapes.Polyline>  
 <xref:System.Windows.Shapes.Polygon>  
 <xref:System.Windows.Shapes.Shape>  
 [Esempio di elementi forma](https://go.microsoft.com/fwlink/?LinkID=160037)  
 [Cenni preliminari sugli oggetti Shape e sulle funzionalità di disegno di base di WPF](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)
