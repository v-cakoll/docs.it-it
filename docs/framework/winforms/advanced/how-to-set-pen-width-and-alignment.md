---
title: "Procedura: impostare la larghezza e l'allineamento di un oggetto Pen"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- pens [Windows Forms], setting width
- pens [Windows Forms], setting alignment
ms.assetid: a202af36-4d31-4401-a126-b232f51db581
ms.openlocfilehash: 8ac125978405f39cd26680338cdabb661ad92d16
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33522282"
---
# <a name="how-to-set-pen-width-and-alignment"></a>Procedura: impostare la larghezza e l'allineamento di un oggetto Pen
Quando si crea un <xref:System.Drawing.Pen>, è possibile fornire la larghezza della penna come uno degli argomenti del costruttore. È inoltre possibile modificare la larghezza della penna con il <xref:System.Drawing.Pen.Width%2A> proprietà la <xref:System.Drawing.Pen> classe.  
  
 Una linea teorica ha una larghezza pari a 0. Quando si disegna una riga con larghezza pari a 1 pixel, alla linea teorica sono incentrati i pixel. Se si disegna una linea più di un pixel di larghezza, i pixel sono centrati rispetto alla linea teorica o vengono visualizzati su un lato della linea teorica. È possibile impostare la proprietà di allineamento della penna di un <xref:System.Drawing.Pen> per determinare la posizione relativa alle linee teoriche dei pixel disegnati con quella penna.  
  
 I valori <xref:System.Drawing.Drawing2D.PenAlignment.Center>, <xref:System.Drawing.Drawing2D.PenAlignment.Outset>, e <xref:System.Drawing.Drawing2D.PenAlignment.Inset> visualizzati di seguito esempi di codice sono membri del <xref:System.Drawing.Drawing2D.PenAlignment> enumerazione.  
  
 Nell'esempio seguente disegna una linea due volte: una volta con una penna nera della larghezza di 1 e una volta con una penna verde di larghezza 10.  
  
### <a name="to-vary-the-width-of-a-pen"></a>Per variare lo spessore di un oggetto pen  
  
-   Impostare il valore della <xref:System.Drawing.Pen.Alignment%2A> proprietà <xref:System.Drawing.Drawing2D.PenAlignment.Center> (predefinito) per specificare che la linea teorica verrà centrata pixel viene disegnata con la penna di colore verde. Nella figura seguente mostra la riga risulta.  
  
     ![Penne](../../../../docs/framework/winforms/advanced/media/pens1a.gif "pens1A")  
  
     Nell'esempio seguente disegna un rettangolo due volte: una volta con una penna nera della larghezza di 1 e una volta con una penna verde di larghezza 10.  
  
     [!code-csharp[System.Drawing.UsingAPen#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#41)]
     [!code-vb[System.Drawing.UsingAPen#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#41)]  
  
### <a name="to-change-the-alignment-of-a-pen"></a>Per modificare l'allineamento di un oggetto pen  
  
-   Impostare il valore della <xref:System.Drawing.Pen.Alignment%2A> proprietà <xref:System.Drawing.Drawing2D.PenAlignment.Center> per specificare che verrà centrata in corrispondenza del limite del rettangolo di pixel viene disegnata con la penna di colore verde.  
  
     Nella figura seguente viene illustrato il rettangolo risulta.  
  
     ![Penne](../../../../docs/framework/winforms/advanced/media/pens2.gif "pens2")  
  
     [!code-csharp[System.Drawing.UsingAPen#42](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#42)]
     [!code-vb[System.Drawing.UsingAPen#42](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#42)]  
  
### <a name="to-create-an-inset-pen"></a>Per creare la penna di inserimento  
  
-   Modificare l'allineamento della penna verde modificando la terza istruzione nell'esempio di codice precedente come segue:  
  
     [!code-csharp[System.Drawing.UsingAPen#43](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#43)]
     [!code-vb[System.Drawing.UsingAPen#43](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#43)]  
  
     Il pixel in linea verde più larga appaiono all'interno del rettangolo come illustrato nella figura seguente.  
  
     ![Penne](../../../../docs/framework/winforms/advanced/media/pens3.gif "pens3")  
  
## <a name="see-also"></a>Vedere anche  
 [Uso di un oggetto Pen per creare linee e forme](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)  
 [Grafica e disegno in Windows Form](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)
