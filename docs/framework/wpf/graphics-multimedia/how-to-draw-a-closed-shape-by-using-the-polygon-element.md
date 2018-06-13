---
title: "Procedura: disegnare una forma chiusa utilizzando l'elemento poligono"
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], Polygon elements
- closed shapes [WPF], drawing with Polygon elements
- Polygon elements [WPF]
- drawing [WPF], closed shapes with Polygon elements
ms.assetid: 4b0ca008-29ce-48dd-8bc3-f3a20ffca6a6
ms.openlocfilehash: 4105139e159783cf0197f4e56c82001835077cbf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33559462"
---
# <a name="how-to-draw-a-closed-shape-by-using-the-polygon-element"></a>Procedura: disegnare una forma chiusa utilizzando l'elemento poligono
In questo esempio viene illustrato come disegnare una forma chiusa utilizzando il <xref:System.Windows.Shapes.Polygon> elemento. Per disegnare una forma chiusa, creare un <xref:System.Windows.Shapes.Polygon> elemento e utilizzare il relativo <xref:System.Windows.Shapes.Polygon.Points%2A> proprietà per specificare i vertici di una forma. Viene automaticamente disegnare una linea che connette il primo e ultimo punto. Infine, specificare un <xref:System.Windows.Shapes.Shape.Fill%2A>, <xref:System.Windows.Shapes.Shape.Stroke%2A>, o entrambi.  
  
## <a name="example"></a>Esempio  
 In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], la sintassi valida per i punti di è un elenco delimitato da virgole di coppie di coordinate x e y separate da virgole.  
  
 [!code-xaml[drawingwithshapeelements#PolygonExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/polygonexample.xaml#polygonexample1)]  
  
 Sebbene nell'esempio viene utilizzato un <xref:System.Windows.Controls.Canvas> per contenere i poligoni, è possibile utilizzare elementi poligono (e tutti gli altri elementi forma) con qualsiasi <xref:System.Windows.Controls.Panel> o <xref:System.Windows.Controls.Control> che supporta il contenuto non di testo.  
  
 In questo esempio fa parte di un esempio più ampio; per l'esempio completo, vedere [esempio di elementi forma](http://go.microsoft.com/fwlink/?LinkID=160037).
