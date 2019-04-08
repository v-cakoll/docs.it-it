---
title: "Procedura: Impostare la larghezza e l'allineamento di un oggetto Pen"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- pens [Windows Forms], setting width
- pens [Windows Forms], setting alignment
ms.assetid: a202af36-4d31-4401-a126-b232f51db581
ms.openlocfilehash: bc2ac2587554215ef3b2c2580413fbbb894aa687
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59074976"
---
# <a name="how-to-set-pen-width-and-alignment"></a>Procedura: Impostare la larghezza e l'allineamento di un oggetto Pen
Quando si crea un <xref:System.Drawing.Pen>, è possibile fornire la larghezza della penna come uno degli argomenti del costruttore. È anche possibile modificare la larghezza della penna con i <xref:System.Drawing.Pen.Width%2A> proprietà del <xref:System.Drawing.Pen> classe.  
  
 Una linea teorica ha una larghezza pari a 0. Quando si disegna una linea che larghezza pari a 1 pixel, dei pixel sono incentrati su linea teorica. Se si disegna una linea che è pari a più di 1 pixel, dei pixel sono centrati nella linea teorica o vengono visualizzati al uno lato della linea teorica. È possibile impostare la proprietà di allineamento della penna di un <xref:System.Drawing.Pen> per determinare la posizione dei pixel disegnati con la penna rispetto alla righe teoriche.  
  
 I valori <xref:System.Drawing.Drawing2D.PenAlignment.Center>, <xref:System.Drawing.Drawing2D.PenAlignment.Outset>, e <xref:System.Drawing.Drawing2D.PenAlignment.Inset> che vengono visualizzati di seguito esempi di codice sono membri del <xref:System.Drawing.Drawing2D.PenAlignment> enumerazione.  
  
 Esempio di codice seguente consente di disegnare una riga due volte: una volta con una penna black della larghezza di 1 e una volta con una penna verde di larghezza 10.  
  
### <a name="to-vary-the-width-of-a-pen"></a>Per variare lo spessore di un oggetto pen  
  
-   Impostare il valore della <xref:System.Drawing.Pen.Alignment%2A> proprietà <xref:System.Drawing.Drawing2D.PenAlignment.Center> (predefinito) per specificare che disegnate con pen verde pixel verrà centrata nella linea teorica. La figura seguente mostra la riga risulta.  
  
     ![Una linea sottile nera con evidenziazione verde.](./media/how-to-set-pen-width-and-alignment/green-pixels-centered-line.gif)  
  
     Esempio di codice seguente consente di disegnare un rettangolo due volte: una volta con una penna black della larghezza di 1 e una volta con una penna verde di larghezza 10.  
  
     [!code-csharp[System.Drawing.UsingAPen#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#41)]
     [!code-vb[System.Drawing.UsingAPen#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#41)]  
  
### <a name="to-change-the-alignment-of-a-pen"></a>Per modificare l'allineamento di un oggetto pen  
  
-   Impostare il valore della <xref:System.Drawing.Pen.Alignment%2A> proprietà <xref:System.Drawing.Drawing2D.PenAlignment.Center> per specificare che verranno centrati i pixel disegnati con pen verde in corrispondenza del limite del rettangolo.  
  
     La figura seguente mostra il rettangolo risulta:
  
     ![Rettangolo disegnato con righe sottile nere con evidenziazione verde.](./media/how-to-set-pen-width-and-alignment/green-pixels-centered-rectangle.gif)  
  
     [!code-csharp[System.Drawing.UsingAPen#42](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#42)]
     [!code-vb[System.Drawing.UsingAPen#42](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#42)]  
  
### <a name="to-create-an-inset-pen"></a>Per creare la penna di inserimento  
  
-   Modificare l'allineamento della penna verde modificando la terza istruzione nell'esempio di codice precedente come indicato di seguito:  
  
     [!code-csharp[System.Drawing.UsingAPen#43](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#43)]
     [!code-vb[System.Drawing.UsingAPen#43](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#43)]  
  
     A questo punto i pixel nella linea verde wide vengono visualizzati all'interno del rettangolo come illustrato nella figura seguente:
  
     ![Rettangolo disegnato con linee nere con la linea verde a livello interno.](./media/how-to-set-pen-width-and-alignment/green-pixels-inside-rectangle.gif)  
  
## <a name="see-also"></a>Vedere anche

- [Utilizzo di un oggetto Pen per creare linee e forme](using-a-pen-to-draw-lines-and-shapes.md)
- [Grafica e disegno in Windows Form](graphics-and-drawing-in-windows-forms.md)
