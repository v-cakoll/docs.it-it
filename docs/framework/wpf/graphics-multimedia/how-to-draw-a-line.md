---
title: 'Procedura: disegnare una linea'
ms.date: 03/30/2017
helpviewer_keywords:
- drawing [WPF], lines
- graphics [WPF], lines
- lines [WPF], drawing
ms.assetid: 0513ee01-6b27-4bb3-85f3-3a3e6710d80e
ms.openlocfilehash: a803c1be01086ca8911ef4cc33bd67697239e2c0
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452948"
---
# <a name="how-to-draw-a-line"></a>Procedura: disegnare una linea
Questo esempio illustra come creare linee usando l'elemento <xref:System.Windows.Shapes.Line>.  
  
 Per creare una linea, creare un elemento <xref:System.Windows.Shapes.Line>. Usare le proprietà <xref:System.Windows.Shapes.Line.X1%2A> e <xref:System.Windows.Shapes.Line.Y1%2A> per impostare il punto di inizio; e utilizzano le proprietà <xref:System.Windows.Shapes.Line.X2%2A> e <xref:System.Windows.Shapes.Line.Y2%2A> per impostare il punto finale. Infine, impostare il <xref:System.Windows.Shapes.Shape.Stroke%2A> e il <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> perché una riga priva di tratto è invisibile.  
  
 L'impostazione dell'elemento <xref:System.Windows.Shapes.Shape.Fill%2A> per una riga non ha alcun effetto, perché una linea non ha interni.  
  
 Nell'esempio seguente vengono disegnate tre righe all'interno di un elemento <xref:System.Windows.Controls.Canvas>.  
  
## <a name="example"></a>Esempio  
 [!code-xaml[drawingwithshapeelements#LineExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/lineexample.xaml#lineexample1)]  
  
 Questo esempio fa parte di un esempio più ampio; per l'esempio completo, vedere [esempio di elementi Shape](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Shapes.Line>
- [Esempio di elementi Shape](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements)
