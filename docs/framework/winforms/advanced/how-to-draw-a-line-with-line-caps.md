---
title: 'Procedura: Disegnare una linea con estremità'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- drawing [Windows Forms], lines
- lines [Windows Forms], drawing
- pens [Windows Forms], drawing lines
- drawing lines [Windows Forms], line caps
ms.assetid: eb68c3e1-c400-4886-8a04-76978a429cb6
ms.openlocfilehash: c4a78569f6c0b14c32154611412d6b3ccd8a84ce
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59146211"
---
# <a name="how-to-draw-a-line-with-line-caps"></a>Procedura: Disegnare una linea con estremità
È possibile disegnare inizio o alla fine di una riga in una delle diverse forme chiamate estremità. [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] supporta diversi limiti di riga, come round, quadrato, a forma di rombo e punta della freccia.  
  
## <a name="example"></a>Esempio  
 È possibile specificare limiti massimi di riga per l'inizio di una riga (estremità di apertura), la fine di una riga (estremità) o i trattini di una linea tratteggiata (cap dash).  
  
 Nell'esempio seguente disegna una linea con una freccia a un'estremità e un'estremità a altra estremità arrotondata. La figura mostra la riga risulta:  
  
 ![Figura che mostra una riga con un'estremità arrotondata.](./media/how-to-draw-a-line-with-line-caps/line-cap-arrowhead-example.gif)  
  
 [!code-csharp[System.Drawing.UsingAPen#71](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#71)]
 [!code-vb[System.Drawing.UsingAPen#71](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#71)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
  
-   Creare un modulo di Windows e la gestione del modulo <xref:System.Windows.Forms.Control.Paint> evento. Incollare il codice di esempio nel <xref:System.Windows.Forms.Control.Paint> gestore dell'evento passando `e` come <xref:System.Windows.Forms.PaintEventArgs>.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Drawing.Pen?displayProperty=nameWithType>
- <xref:System.Drawing.Drawing2D.LineCap?displayProperty=nameWithType>
- [Grafica e disegno in Windows Form](graphics-and-drawing-in-windows-forms.md)
- [Uso di un oggetto Pen per creare linee e forme](using-a-pen-to-draw-lines-and-shapes.md)
