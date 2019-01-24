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
ms.openlocfilehash: cd009a66cb106f98727191037d8eef5bafe4d0c9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54590052"
---
# <a name="how-to-use-a-pen-to-draw-rectangles"></a>Procedura: Usare un oggetto Pen per disegnare rettangoli
Per disegnare rettangoli, è necessario un <xref:System.Drawing.Graphics> oggetto e un <xref:System.Drawing.Pen> oggetto. Il <xref:System.Drawing.Graphics> oggetto fornisce le <xref:System.Drawing.Graphics.DrawRectangle%2A> metodo e il <xref:System.Drawing.Pen> oggetto archivia le funzionalità della riga, ad esempio colore e spessore.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente disegna un rettangolo con relativo angolo superiore sinistro a (10, 10). Il rettangolo ha una larghezza pari a 100 e un'altezza pari a 50. Il secondo argomento passato al <xref:System.Drawing.Pen.%23ctor%2A> costruttore indica che la larghezza della penna è 5 pixel.  
  
 Quando viene disegnato il rettangolo, penna coincide con i limiti del rettangolo. Poiché la larghezza della penna è 5, i lati del rettangolo vengono disegnati 5 pixel ampia, ad esempio che 1 pixel viene disegnata in corrispondenza del limite se stesso, 2 pixel vengono disegnati all'interno e 2 pixel vengono disegnati all'esterno. Per ulteriori informazioni sull'allineamento di penna, vedere [come: Impostare larghezza e l'allineamento](../../../../docs/framework/winforms/advanced/how-to-set-pen-width-and-alignment.md).  
  
 La figura seguente mostra il rettangolo risulta. Le linee tratteggiate indicano dove il rettangolo sarebbe stato tracciato se la larghezza della penna fosse stato di un pixel. La visualizzazione ingrandita dell'angolo superiore sinistro del rettangolo mostra che le linee nere thick sono incentrate su tali linee tratteggiate.  
  
 ![Penne](../../../../docs/framework/winforms/advanced/media/pens1.gif "pens1")  
  
 [!code-csharp[System.Drawing.UsingAPen#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.UsingAPen#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs> `e`, ovvero un parametro del <xref:System.Windows.Forms.Control.Paint> gestore dell'evento.  
  
## <a name="see-also"></a>Vedere anche
- [Uso di un oggetto Pen per creare linee e forme](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)
