---
title: Ellissi e archi in GDI+
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 71126942f4cde37cc5d26bfba029c5f50f1065a3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ellipses-and-arcs-in-gdi"></a>Ellissi e archi in GDI+
È possibile tracciare ellissi e archi utilizzando il <xref:System.Drawing.Graphics.DrawEllipse%2A> e <xref:System.Drawing.Graphics.DrawArc%2A> metodi di <xref:System.Drawing.Graphics> classe.  
  
## <a name="drawing-an-ellipse"></a>Disegnare un'ellisse  
 Per disegnare un'ellisse, è necessario un <xref:System.Drawing.Graphics> oggetto e un <xref:System.Drawing.Pen> oggetto. Il <xref:System.Drawing.Graphics> oggetto fornisce il <xref:System.Drawing.Graphics.DrawEllipse%2A> (metodo) e <xref:System.Drawing.Pen> oggetto archivia gli attributi, ad esempio spessore e colore della linea utilizzata per eseguire il rendering dell'ellisse. Il <xref:System.Drawing.Pen> oggetto viene passato come uno degli argomenti per il <xref:System.Drawing.Graphics.DrawEllipse%2A> metodo. Gli argomenti rimanenti passati il <xref:System.Drawing.Graphics.DrawEllipse%2A> metodo specificare il rettangolo di delimitazione dell'ellisse. Nella figura seguente mostra un'ellisse con rettangolo di delimitazione.  
  
 ![Ellissi e archi](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art05.gif "Aboutgdip02_art05")  
  
 Nell'esempio seguente disegna un'ellisse. il rettangolo di delimitazione ha una larghezza pari a 80, un'altezza pari a 40 e un angolo superiore sinistro di (100, 50):  
  
 [!code-csharp[LinesCurvesAndShapes#51](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#51)]
 [!code-vb[LinesCurvesAndShapes#51](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#51)]  
  
 <xref:System.Drawing.Graphics.DrawEllipse%2A>un metodo di overload di <xref:System.Drawing.Graphics> classe, pertanto vi sono diversi modi, è possibile fornire argomenti. Ad esempio, è possibile costruire un <xref:System.Drawing.Rectangle> e passare il <xref:System.Drawing.Rectangle> per il <xref:System.Drawing.Graphics.DrawEllipse%2A> metodo come argomento:  
  
 [!code-csharp[LinesCurvesAndShapes#52](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#52)]
 [!code-vb[LinesCurvesAndShapes#52](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#52)]  
  
## <a name="drawing-an-arc"></a>Disegno di un arco  
 Un arco è una parte di un'ellisse. Per disegnare l'arco, si chiama il <xref:System.Drawing.Graphics.DrawArc%2A> metodo la <xref:System.Drawing.Graphics> classe. I parametri del <xref:System.Drawing.Graphics.DrawArc%2A> metodo sono gli stessi parametri del <xref:System.Drawing.Graphics.DrawEllipse%2A> (metodo), con la differenza che <xref:System.Drawing.Graphics.DrawArc%2A> richiede un angolo iniziale e angolo di apertura. Nell'esempio seguente disegna un arco con un angolo iniziale di 30 gradi e un angolo di apertura di 180 gradi:  
  
 [!code-csharp[LinesCurvesAndShapes#53](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#53)]
 [!code-vb[LinesCurvesAndShapes#53](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#53)]  
  
 Nella figura seguente mostra l'arco, i puntini di sospensione e il rettangolo di delimitazione.  
  
 ![Ellissi e archi](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art06.gif "Aboutgdip02_art06")  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Drawing.Graphics?displayProperty=nameWithType>  
 <xref:System.Drawing.Pen?displayProperty=nameWithType>  
 [Linee, curve e forme](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [Procedura: Creare oggetti Graphics per disegnare](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)  
 [Procedura: Creare un oggetto Pen](../../../../docs/framework/winforms/advanced/how-to-create-a-pen.md)  
 [Procedura: Creare una forma con contorno](../../../../docs/framework/winforms/advanced/how-to-draw-an-outlined-shape.md)
