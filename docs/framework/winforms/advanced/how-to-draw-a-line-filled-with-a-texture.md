---
title: 'Procedura: disegnare una linea con riempimento a trama'
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
- drawing [Windows Forms], lines
- lines [Windows Forms], texture
- drawing lines [Windows Forms], texture
ms.assetid: dc9118cc-f3c2-42e5-8173-f46d41d18fd5
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 33374a16e6fee80dd45227acd4c5860d5bfc4545
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-draw-a-line-filled-with-a-texture"></a>Procedura: disegnare una linea con riempimento a trama
Anziché disegnare una riga con un colore a tinta unita, è possibile disegnare una riga con una trama. Per disegnare linee e curve con una trama, creare un <xref:System.Drawing.TextureBrush> dell'oggetto e passare tale <xref:System.Drawing.TextureBrush> l'oggetto in un <xref:System.Drawing.Pen.%23ctor%2A> costruttore. La bitmap associata al pennello trama viene utilizzata per affiancare il piano (in modo invisibile) e quando la penna Disegna una linea o una curva, il tratto di penna vengono evidenziati alcuni pixel della trama affiancata.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene creato un <xref:System.Drawing.Bitmap> oggetto dal file `Texture1.jpg`. La bitmap viene utilizzato per costruire un <xref:System.Drawing.TextureBrush> oggetto e <xref:System.Drawing.TextureBrush> oggetto viene utilizzato per costruire un <xref:System.Drawing.Pen> oggetto. La chiamata a <xref:System.Drawing.Graphics.DrawImage%2A> Disegna la bitmap con il relativo angolo superiore sinistro a (0, 0). La chiamata a <xref:System.Drawing.Graphics.DrawEllipse%2A> utilizza il <xref:System.Drawing.Pen> oggetto su cui disegnare un'ellisse a trama.  
  
 Nella figura seguente mostra la bitmap e la trama ellisse.  
  
 ![Penne](../../../../docs/framework/winforms/advanced/media/pens7.png "pens7")  
  
 [!code-csharp[System.Drawing.UsingAPen#61](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#61)]
 [!code-vb[System.Drawing.UsingAPen#61](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#61)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 Creare un Windows Form e gestire il modulo <xref:System.Windows.Forms.Control.Paint> evento. Incollare il codice precedente nel <xref:System.Windows.Forms.Control.Paint> gestore dell'evento. Sostituire `Texture.jpg` con un'immagine disponibile nel sistema.  
  
## <a name="see-also"></a>Vedere anche  
 [Uso di un oggetto Pen per creare linee e forme](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)  
 [Grafica e disegno in Windows Form](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)
