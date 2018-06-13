---
title: Penne, linee e rettangoli in GDI+
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- lines
- GDI+, lines
- drawing [Windows Forms], rectangles
- rectangles
- drawing [Windows Forms], lines
- GDI+, pens
- examples [Windows Forms], drawing lines and shapes
- examples [Windows Forms], pens
- GDI+, rectangles
- examples [Windows Forms], GDI+
- lines [Windows Forms], dashed
ms.assetid: 30b25aae-e3eb-4479-bdb8-187cf651fc84
ms.openlocfilehash: 86cc51006361d5628dc12999588520e28e62f166
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33527470"
---
# <a name="pens-lines-and-rectangles-in-gdi"></a>Penne, linee e rettangoli in GDI+
Per disegnare linee con [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] è necessario creare un <xref:System.Drawing.Graphics> oggetto e un <xref:System.Drawing.Pen> oggetto. Il <xref:System.Drawing.Graphics> oggetto fornisce metodi che effettivamente svolgono il disegno, e <xref:System.Drawing.Pen> oggetto archivia gli attributi, ad esempio colore, larghezza e stile.  
  
## <a name="drawing-a-line"></a>Creazione di una linea  
 Per disegnare una linea, chiamare il <xref:System.Drawing.Graphics.DrawLine%2A> metodo il <xref:System.Drawing.Graphics> oggetto. Il <xref:System.Drawing.Pen> oggetto viene passato come uno degli argomenti per il <xref:System.Drawing.Graphics.DrawLine%2A> metodo. Nell'esempio seguente disegna una linea tra il punto (4, 2) per il punto (12, 6):  
  
 [!code-csharp[LinesCurvesAndShapes#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#41)]
 [!code-vb[LinesCurvesAndShapes#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#41)]  
  
 <xref:System.Drawing.Graphics.DrawLine%2A> è un metodo di overload del <xref:System.Drawing.Graphics> classe, pertanto vi sono diversi modi, è possibile fornire argomenti. Ad esempio, è possibile creare due <xref:System.Drawing.Point> oggetti e passare il <xref:System.Drawing.Point> oggetti come argomenti il <xref:System.Drawing.Graphics.DrawLine%2A> metodo:  
  
 [!code-csharp[LinesCurvesAndShapes#42](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#42)]
 [!code-vb[LinesCurvesAndShapes#42](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#42)]  
  
## <a name="constructing-a-pen"></a>Creazione di un oggetto Pen  
 È possibile specificare determinati attributi quando si costruisce un <xref:System.Drawing.Pen> oggetto. Ad esempio, uno `Pen` costruttore consente di specificare il colore e larghezza. Nell'esempio seguente disegna una linea blu della larghezza 2 da (0, 0) a (60, 30):  
  
 [!code-csharp[LinesCurvesAndShapes#43](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#43)]
 [!code-vb[LinesCurvesAndShapes#43](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#43)]  
  
## <a name="dashed-lines-and-line-caps"></a>Le linee tratteggiate e delimitatori di riga  
 Il <xref:System.Drawing.Pen> oggetto espone anche le proprietà, ad esempio <xref:System.Drawing.Pen.DashStyle%2A>, che consente di specificare le funzionalità della riga. Nell'esempio seguente disegna una linea tratteggiata da (100, 50) a (300, 80):  
  
 [!code-csharp[LinesCurvesAndShapes#44](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#44)]
 [!code-vb[LinesCurvesAndShapes#44](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#44)]  
  
 È possibile utilizzare le proprietà del <xref:System.Drawing.Pen> oggetto da impostare molti altri attributi della linea. Il <xref:System.Drawing.Pen.StartCap%2A> e <xref:System.Drawing.Pen.EndCap%2A> specificano l'aspetto delle estremità della linea, le entità finali possono anche essere flat quadrati, angoli arrotondati, triangolare, o una forma personalizzata. Il <xref:System.Drawing.Pen.LineJoin%2A> proprietà consente di specificare se le linee connesse siano (unita in join con angoli acuti), smussate, arrotondate o troncate. Nella figura seguente mostra le righe con diversi stili di estremità e join.  
  
 ![Linee](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art04.gif "Aboutgdip02_art04")  
  
## <a name="drawing-a-rectangle"></a>Creazione di un rettangolo  
 Disegno di rettangoli con [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] è simile alla creazione di righe. Per disegnare un rettangolo, è necessario un <xref:System.Drawing.Graphics> oggetto e un <xref:System.Drawing.Pen> oggetto. Il <xref:System.Drawing.Graphics> oggetto fornisce un <xref:System.Drawing.Graphics.DrawRectangle%2A> (metodo) e <xref:System.Drawing.Pen> oggetto archivia gli attributi, ad esempio spessore e colore. Il <xref:System.Drawing.Pen> oggetto viene passato come uno degli argomenti per il <xref:System.Drawing.Graphics.DrawRectangle%2A> metodo. Nell'esempio seguente disegna un rettangolo con il relativo angolo superiore sinistro a (100, 50), una larghezza pari a 80 e l'altezza di 40:  
  
 [!code-csharp[LinesCurvesAndShapes#45](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#45)]
 [!code-vb[LinesCurvesAndShapes#45](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#45)]  
  
 <xref:System.Drawing.Graphics.DrawRectangle%2A> è un metodo di overload del <xref:System.Drawing.Graphics> classe, pertanto vi sono diversi modi, è possibile fornire argomenti. Ad esempio, è possibile costruire un <xref:System.Drawing.Rectangle> , quindi passare il <xref:System.Drawing.Rectangle> dell'oggetto per il <xref:System.Drawing.Graphics.DrawRectangle%2A> metodo come argomento:  
  
 [!code-csharp[LinesCurvesAndShapes#46](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#46)]
 [!code-vb[LinesCurvesAndShapes#46](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#46)]  
  
 Oggetto <xref:System.Drawing.Rectangle> oggetto dispone di metodi e proprietà per la modifica e la raccolta di informazioni relative al rettangolo. Ad esempio, il <xref:System.Drawing.Rectangle.Inflate%2A> e <xref:System.Drawing.Rectangle.Offset%2A> i metodi di modificare le dimensioni e la posizione del rettangolo. Il <xref:System.Drawing.Rectangle.IntersectsWith%2A> metodo indica se il rettangolo interseca un'altra rettangolo specificato e <xref:System.Drawing.Rectangle.Contains%2A> metodo indica se un determinato punto è all'interno del rettangolo.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Drawing.Graphics?displayProperty=nameWithType>  
 <xref:System.Drawing.Pen?displayProperty=nameWithType>  
 <xref:System.Drawing.Rectangle?displayProperty=nameWithType>  
 [Procedura: Creare un oggetto Pen](../../../../docs/framework/winforms/advanced/how-to-create-a-pen.md)  
 [Procedura: Disegnare una linea in un Windows Form](../../../../docs/framework/winforms/advanced/how-to-draw-a-line-on-a-windows-form.md)  
 [Procedura: Creare una forma con contorno](../../../../docs/framework/winforms/advanced/how-to-draw-an-outlined-shape.md)
