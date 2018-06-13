---
title: 'Procedura: disegnare una linea'
ms.date: 03/30/2017
helpviewer_keywords:
- drawing [WPF], lines
- graphics [WPF], lines
- lines [WPF], drawing
ms.assetid: 0513ee01-6b27-4bb3-85f3-3a3e6710d80e
ms.openlocfilehash: 1093e754912cd3ee3b8474ed7d190913079a9f9e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33560625"
---
# <a name="how-to-draw-a-line"></a>Procedura: disegnare una linea
In questo esempio viene illustrato come disegnare righe utilizzando il <xref:System.Windows.Shapes.Line> elemento.  
  
 Per disegnare una linea, creare un <xref:System.Windows.Shapes.Line> elemento. Utilizzare il relativo <xref:System.Windows.Shapes.Line.X1%2A> e <xref:System.Windows.Shapes.Line.Y1%2A> proprietà per impostare il punto di inizio; e relativo <xref:System.Windows.Shapes.Line.X2%2A> e <xref:System.Windows.Shapes.Line.Y2%2A> proprietà per impostare il punto finale. Infine, impostare il relativo <xref:System.Windows.Shapes.Shape.Stroke%2A> e <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> perché una riga senza tratto è invisibile.  
  
 L'impostazione di <xref:System.Windows.Shapes.Shape.Fill%2A> elemento per una riga non ha alcun effetto perché una riga non ha interno.  
  
 Nell'esempio seguente disegna tre righe all'interno di un <xref:System.Windows.Controls.Canvas> elemento.  
  
## <a name="example"></a>Esempio  
 [!code-xaml[drawingwithshapeelements#LineExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/lineexample.xaml#lineexample1)]  
  
 In questo esempio fa parte di un esempio più ampio; per l'esempio completo, vedere [esempio di elementi forma](http://go.microsoft.com/fwlink/?LinkID=160037).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Shapes.Line>  
 [Esempio di elementi forma](http://go.microsoft.com/fwlink/?LinkID=160037)
