---
title: Ellissi e archi in GDI+
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- arcs
- GDI+, arcs
- drawing [Windows Forms], ellipses
- GDI+, ellipses
- ellipses
- drawing [Windows Forms], arcs
ms.assetid: 34f35133-a835-4ca4-81f6-0dfedee8b683
ms.openlocfilehash: 93f82d35449c42772e9fbd1b7454364885b38769
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54697205"
---
# <a name="ellipses-and-arcs-in-gdi"></a>Ellissi e archi in GDI+
È possibile disegnare facilmente ellissi e archi usando il <xref:System.Drawing.Graphics.DrawEllipse%2A> e <xref:System.Drawing.Graphics.DrawArc%2A> metodi del <xref:System.Drawing.Graphics> classe.  
  
## <a name="drawing-an-ellipse"></a>Disegnare un'ellisse  
 Per disegnare un'ellisse, è necessario un <xref:System.Drawing.Graphics> oggetto e un <xref:System.Drawing.Pen> oggetto. Il <xref:System.Drawing.Graphics> oggetto fornisce le <xref:System.Drawing.Graphics.DrawEllipse%2A> metodo e il <xref:System.Drawing.Pen> oggetto archivia gli attributi, ad esempio la larghezza e il colore della linea utilizzata per eseguire il rendering dell'ellisse. Il <xref:System.Drawing.Pen> oggetto viene passato come uno degli argomenti per il <xref:System.Drawing.Graphics.DrawEllipse%2A> (metodo). I restanti argomenti passati al <xref:System.Drawing.Graphics.DrawEllipse%2A> metodo specifica il rettangolo di delimitazione dell'ellisse. La figura seguente mostra un'ellisse con il rettangolo di delimitazione.  
  
 ![Ellissi e archi](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art05.gif "Aboutgdip02_art05")  
  
 L'esempio seguente disegna un'ellisse. il rettangolo di delimitazione abbia una larghezza pari a 80, un'altezza pari a 40 e un angolo superiore sinistro di (100, 50):  
  
 [!code-csharp[LinesCurvesAndShapes#51](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#51)]
 [!code-vb[LinesCurvesAndShapes#51](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#51)]  
  
 <xref:System.Drawing.Graphics.DrawEllipse%2A> un metodo di overload di <xref:System.Drawing.Graphics> classe, quindi esistono diversi modi, è possibile fornire argomenti. Ad esempio, è possibile costruire una <xref:System.Drawing.Rectangle> e passare il <xref:System.Drawing.Rectangle> per il <xref:System.Drawing.Graphics.DrawEllipse%2A> metodo come argomento:  
  
 [!code-csharp[LinesCurvesAndShapes#52](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#52)]
 [!code-vb[LinesCurvesAndShapes#52](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#52)]  
  
## <a name="drawing-an-arc"></a>Disegnare un arco  
 Un arco è una parte di un'ellisse. Per disegnare un arco, si chiama il <xref:System.Drawing.Graphics.DrawArc%2A> metodo di <xref:System.Drawing.Graphics> classe. I parametri del <xref:System.Drawing.Graphics.DrawArc%2A> metodo sono gli stessi parametri del <xref:System.Drawing.Graphics.DrawEllipse%2A> metodo, con la differenza che <xref:System.Drawing.Graphics.DrawArc%2A> richiede un angolo iniziale e angolo di apertura. Nell'esempio seguente disegna un arco con un angolo iniziale di 30 gradi e un angolo di apertura di 180 gradi:  
  
 [!code-csharp[LinesCurvesAndShapes#53](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#53)]
 [!code-vb[LinesCurvesAndShapes#53](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#53)]  
  
 La figura seguente mostra l'arco, i puntini di sospensione e il rettangolo di delimitazione.  
  
 ![Ellissi e archi](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art06.gif "Aboutgdip02_art06")  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Drawing.Graphics?displayProperty=nameWithType>
- <xref:System.Drawing.Pen?displayProperty=nameWithType>
- [Linee, curve e forme](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)
- [Procedura: Creare oggetti Graphics per disegnare](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)
- [Procedura: Creare un oggetto Pen](../../../../docs/framework/winforms/advanced/how-to-create-a-pen.md)
- [Procedura: Disegnare una forma con contorno](../../../../docs/framework/winforms/advanced/how-to-draw-an-outlined-shape.md)
