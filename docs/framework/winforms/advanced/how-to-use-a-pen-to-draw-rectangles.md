---
title: 'Procedura: Usare un oggetto Pen per disegnare rettangoli'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- rectangles [Windows Forms], drawing
- pens [Windows Forms], drawing rectangles
ms.assetid: 54a7fa14-3ad8-4d64-b424-2a12005b250c
ms.openlocfilehash: 0e51a1e3a2d14754147dbd36f170127a7e978acd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61954494"
---
# <a name="how-to-use-a-pen-to-draw-rectangles"></a>Procedura: Usare un oggetto Pen per disegnare rettangoli
Per disegnare rettangoli, è necessario un <xref:System.Drawing.Graphics> oggetto e un <xref:System.Drawing.Pen> oggetto. Il <xref:System.Drawing.Graphics> oggetto fornisce le <xref:System.Drawing.Graphics.DrawRectangle%2A> metodo e il <xref:System.Drawing.Pen> oggetto archivia le funzionalità della riga, ad esempio colore e spessore.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente disegna un rettangolo con relativo angolo superiore sinistro a (10, 10). Il rettangolo ha una larghezza pari a 100 e un'altezza pari a 50. Il secondo argomento passato al <xref:System.Drawing.Pen.%23ctor%2A> costruttore indica che la larghezza della penna è 5 pixel.  
  
 Quando viene disegnato il rettangolo, penna coincide con i limiti del rettangolo. Poiché la larghezza della penna è 5, i lati del rettangolo vengono disegnati 5 pixel ampia, ad esempio che 1 pixel viene disegnata in corrispondenza del limite se stesso, 2 pixel vengono disegnati all'interno e 2 pixel vengono disegnati all'esterno. Per ulteriori informazioni sull'allineamento di penna, vedere [come: Impostare larghezza e l'allineamento](how-to-set-pen-width-and-alignment.md).  
  
 La figura seguente mostra il rettangolo risulta. Le linee tratteggiate indicano dove il rettangolo sarebbe stato tracciato se la larghezza della penna fosse stato di un pixel. La visualizzazione ingrandita dell'angolo superiore sinistro del rettangolo mostra che le linee nere thick sono incentrate su tali linee tratteggiate.  
  
 ![Screenshot che mostra il rettangolo disegnato con nero e linee tratteggiate.](./media/how-to-use-a-pen-to-draw-rectangles/drawn-rectangle-black-lines-dotted-lines.gif)  
  
 [!code-csharp[System.Drawing.UsingAPen#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.UsingAPen#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs>`e`, un parametro del gestore eventi <xref:System.Windows.Forms.Control.Paint>.  
  
## <a name="see-also"></a>Vedere anche

- [Uso di un oggetto Pen per creare linee e forme](using-a-pen-to-draw-lines-and-shapes.md)
