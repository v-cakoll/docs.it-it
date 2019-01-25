---
title: 'Procedura: Disegnare una linea con riempita a trama'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- drawing [Windows Forms], lines
- lines [Windows Forms], texture
- drawing lines [Windows Forms], texture
ms.assetid: dc9118cc-f3c2-42e5-8173-f46d41d18fd5
ms.openlocfilehash: 65d830ca2d01c63288ef73b6b3a3a94f328fe32b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54676240"
---
# <a name="how-to-draw-a-line-filled-with-a-texture"></a>Procedura: Disegnare una linea con riempita a trama
Invece di tracciare una linea con un colore a tinta unita, è possibile disegnare una linea con una trama. Per tracciare linee e curve con una trama, creare un <xref:System.Drawing.TextureBrush> dell'oggetto e passarlo <xref:System.Drawing.TextureBrush> dell'oggetto a un <xref:System.Drawing.Pen.%23ctor%2A> costruttore. La bitmap associata al pennello trama viene utilizzata per affiancare il piano (in modo invisibile) e quando la penna Disegna una linea o una curva, il tratto di penna permette di ottenere determinate pixel della trama affiancata.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente crea una <xref:System.Drawing.Bitmap> oggetto dal file `Texture1.jpg`. La bitmap viene usato per costruire una <xref:System.Drawing.TextureBrush> oggetti e il <xref:System.Drawing.TextureBrush> oggetto viene usato per costruire un <xref:System.Drawing.Pen> oggetto. La chiamata a <xref:System.Drawing.Graphics.DrawImage%2A> consente di disegnare la bitmap con relativo angolo superiore sinistro a (0, 0). La chiamata a <xref:System.Drawing.Graphics.DrawEllipse%2A> utilizza il <xref:System.Drawing.Pen> oggetto su cui disegnare un'ellisse con trama.  
  
 La figura seguente mostra la bitmap e la trama ellisse.  
  
 ![Penne](../../../../docs/framework/winforms/advanced/media/pens7.png "pens7")  
  
 [!code-csharp[System.Drawing.UsingAPen#61](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#61)]
 [!code-vb[System.Drawing.UsingAPen#61](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#61)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 Creare un modulo di Windows e la gestione del modulo <xref:System.Windows.Forms.Control.Paint> evento. Incollare il codice precedente nel <xref:System.Windows.Forms.Control.Paint> gestore dell'evento. Sostituire `Texture.jpg` con un'immagine valida nel sistema.  
  
## <a name="see-also"></a>Vedere anche
- [Uso di un oggetto Pen per creare linee e forme](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)
- [Grafica e disegno in Windows Form](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)
