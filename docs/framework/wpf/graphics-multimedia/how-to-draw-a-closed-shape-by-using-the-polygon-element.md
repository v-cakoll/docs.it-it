---
title: "Procedura: disegnare una forma chiusa utilizzando l'elemento poligono"
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], Polygon elements
- closed shapes [WPF], drawing with Polygon elements
- Polygon elements [WPF]
- drawing [WPF], closed shapes with Polygon elements
ms.assetid: 4b0ca008-29ce-48dd-8bc3-f3a20ffca6a6
ms.openlocfilehash: 324a5623ee658789b8600a43a89ce26cab7cd6cd
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452974"
---
# <a name="how-to-draw-a-closed-shape-by-using-the-polygon-element"></a>Procedura: disegnare una forma chiusa utilizzando l'elemento poligono
In questo esempio viene illustrato come disegnare una forma chiusa utilizzando l'elemento <xref:System.Windows.Shapes.Polygon>. Per disegnare una forma chiusa, creare un elemento <xref:System.Windows.Shapes.Polygon> e utilizzare la relativa proprietà <xref:System.Windows.Shapes.Polygon.Points%2A> per specificare i vertici di una forma. Viene disegnata automaticamente una linea che connette il primo e l'ultimo punto. Infine, specificare un <xref:System.Windows.Shapes.Shape.Fill%2A>, un <xref:System.Windows.Shapes.Shape.Stroke%2A>o entrambi.  
  
## <a name="example"></a>Esempio  
 In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]la sintassi valida per i punti è un elenco delimitato da spazi di coppie di coordinate x e y separate da virgole.  
  
 [!code-xaml[drawingwithshapeelements#PolygonExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/polygonexample.xaml#polygonexample1)]  
  
 Sebbene nell'esempio venga utilizzato un <xref:System.Windows.Controls.Canvas> per contenere i poligoni, è possibile utilizzare gli elementi Polygon (e tutti gli altri elementi Shape) con qualsiasi <xref:System.Windows.Controls.Panel> o <xref:System.Windows.Controls.Control> che supporti contenuto non di testo.  
  
 Questo esempio fa parte di un esempio più ampio; per l'esempio completo, vedere [esempio di elementi Shape](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements).
