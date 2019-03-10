---
title: 'Procedura: Linee di join'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- miter line join style
- bevel line join style
- line join
- drawing [Windows Forms], joining lines
- GraphicsPath object
- round line join style
- lines [Windows Forms], joining
- graphics [Windows Forms], joining lines
ms.assetid: 9fc480c2-3c75-4fd1-8ab5-296a99e820e2
ms.openlocfilehash: a95ccddd89c85c5439c4d73f77a6ed67198dc7ba
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57709863"
---
# <a name="how-to-join-lines"></a>Procedura: Linee di join
Un join di riga è l'area comune in cui è costituito da due righe di cui end soddisfare o si sovrappongono. [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] sono disponibili tre stili di linea join: decorato, rilievo e arrotondato. Stile di linea join è una proprietà del <xref:System.Drawing.Pen> classe. Quando si specifica un stile della linea join per un <xref:System.Drawing.Pen> dell'oggetto, che verrà applicata a tutte le righe connessione in qualsiasi tipo di join <xref:System.Drawing.Drawing2D.GraphicsPath> oggetto viene disegnato utilizzando la penna.  
  
 La figura seguente mostra i risultati dell'esempio di join di linee in rilievo.  
  
 ![Penne](./media/pens5.gif "pens5")  
  
## <a name="example"></a>Esempio  
 È possibile specificare lo stile della linea join tramite il <xref:System.Drawing.Pen.LineJoin%2A> proprietà del <xref:System.Drawing.Pen> classe. Nell'esempio viene illustrato un join di linee in rilievo tra una riga orizzontale e una linea verticale. Nel codice seguente, il valore <xref:System.Drawing.Drawing2D.LineJoin.Bevel> assegnato per il <xref:System.Drawing.Pen.LineJoin%2A> proprietà è un membro del <xref:System.Drawing.Drawing2D.LineJoin> enumerazione. Gli altri membri della <xref:System.Drawing.Drawing2D.LineJoin> enumerazione vengono <xref:System.Drawing.Drawing2D.LineJoin.Miter> e <xref:System.Drawing.Drawing2D.LineJoin.Round>.  
  
 [!code-csharp[System.Drawing.UsingAPen#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.UsingAPen#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs> `e`, un parametro del gestore eventi <xref:System.Windows.Forms.Control.Paint>.  
  
## <a name="see-also"></a>Vedere anche
- [Uso di un oggetto Pen per creare linee e forme](using-a-pen-to-draw-lines-and-shapes.md)
