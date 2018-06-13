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
# <a name="how-to-draw-a-line"></a><span data-ttu-id="1b324-102">Procedura: disegnare una linea</span><span class="sxs-lookup"><span data-stu-id="1b324-102">How to: Draw a Line</span></span>
<span data-ttu-id="1b324-103">In questo esempio viene illustrato come disegnare righe utilizzando il <xref:System.Windows.Shapes.Line> elemento.</span><span class="sxs-lookup"><span data-stu-id="1b324-103">This example shows you how to draw lines by using the <xref:System.Windows.Shapes.Line> element.</span></span>  
  
 <span data-ttu-id="1b324-104">Per disegnare una linea, creare un <xref:System.Windows.Shapes.Line> elemento.</span><span class="sxs-lookup"><span data-stu-id="1b324-104">To draw a line, create a <xref:System.Windows.Shapes.Line> element.</span></span> <span data-ttu-id="1b324-105">Utilizzare il relativo <xref:System.Windows.Shapes.Line.X1%2A> e <xref:System.Windows.Shapes.Line.Y1%2A> proprietà per impostare il punto di inizio; e relativo <xref:System.Windows.Shapes.Line.X2%2A> e <xref:System.Windows.Shapes.Line.Y2%2A> proprietà per impostare il punto finale.</span><span class="sxs-lookup"><span data-stu-id="1b324-105">Use its <xref:System.Windows.Shapes.Line.X1%2A> and <xref:System.Windows.Shapes.Line.Y1%2A> properties to set its start point; and use its <xref:System.Windows.Shapes.Line.X2%2A> and <xref:System.Windows.Shapes.Line.Y2%2A> properties to set its end point.</span></span> <span data-ttu-id="1b324-106">Infine, impostare il relativo <xref:System.Windows.Shapes.Shape.Stroke%2A> e <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> perché una riga senza tratto è invisibile.</span><span class="sxs-lookup"><span data-stu-id="1b324-106">Finally, set its <xref:System.Windows.Shapes.Shape.Stroke%2A> and <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> because a line without a stroke is invisible.</span></span>  
  
 <span data-ttu-id="1b324-107">L'impostazione di <xref:System.Windows.Shapes.Shape.Fill%2A> elemento per una riga non ha alcun effetto perché una riga non ha interno.</span><span class="sxs-lookup"><span data-stu-id="1b324-107">Setting the <xref:System.Windows.Shapes.Shape.Fill%2A> element for a line has no effect, because a line has no interior.</span></span>  
  
 <span data-ttu-id="1b324-108">Nell'esempio seguente disegna tre righe all'interno di un <xref:System.Windows.Controls.Canvas> elemento.</span><span class="sxs-lookup"><span data-stu-id="1b324-108">The following example draws three lines inside a <xref:System.Windows.Controls.Canvas> element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1b324-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="1b324-109">Example</span></span>  
 [!code-xaml[drawingwithshapeelements#LineExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/lineexample.xaml#lineexample1)]  
  
 <span data-ttu-id="1b324-110">In questo esempio fa parte di un esempio più ampio; per l'esempio completo, vedere [esempio di elementi forma](http://go.microsoft.com/fwlink/?LinkID=160037).</span><span class="sxs-lookup"><span data-stu-id="1b324-110">This example is part of a larger sample; for the complete sample, see [Shape Elements Sample](http://go.microsoft.com/fwlink/?LinkID=160037).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b324-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1b324-111">See Also</span></span>  
 <xref:System.Windows.Shapes.Line>  
 [<span data-ttu-id="1b324-112">Esempio di elementi forma</span><span class="sxs-lookup"><span data-stu-id="1b324-112">Shape Elements Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=160037)
