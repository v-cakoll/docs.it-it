---
title: 'Procedura: unire linee'
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
ms.openlocfilehash: cecced7b32af7187cb1ef072921f0ff28f04adad
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33522015"
---
# <a name="how-to-join-lines"></a>Procedura: unire linee
Un'unione di linee è l'area comune è costituito da due righe le cui estremità soddisfa o si sovrappongono. [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] sono disponibili tre stili di join di linee: decorato, rilievo e arrotondato. Stile di linea join è una proprietà del <xref:System.Drawing.Pen> classe. Quando si specifica uno stile di linea join per un <xref:System.Drawing.Pen> dell'oggetto, che verrà applicata a tutte le righe collegate in qualsiasi tipo di join <xref:System.Drawing.Drawing2D.GraphicsPath> oggetto disegnato utilizzando quella penna.  
  
 Nella figura seguente mostra i risultati dell'esempio di join di linee in rilievo.  
  
 ![Penne](../../../../docs/framework/winforms/advanced/media/pens5.gif "pens5")  
  
## <a name="example"></a>Esempio  
 È possibile specificare lo stile di linea join utilizzando il <xref:System.Drawing.Pen.LineJoin%2A> proprietà la <xref:System.Drawing.Pen> classe. Nell'esempio viene illustrato un join di linee in rilievo tra una linea orizzontale e verticale. Nel codice seguente, il valore <xref:System.Drawing.Drawing2D.LineJoin.Bevel> assegnato per il <xref:System.Drawing.Pen.LineJoin%2A> proprietà è un membro del <xref:System.Drawing.Drawing2D.LineJoin> enumerazione. Gli altri membri del <xref:System.Drawing.Drawing2D.LineJoin> enumerazione sono <xref:System.Drawing.Drawing2D.LineJoin.Miter> e <xref:System.Drawing.Drawing2D.LineJoin.Round>.  
  
 [!code-csharp[System.Drawing.UsingAPen#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.UsingAPen#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs> `e`, un parametro del gestore eventi <xref:System.Windows.Forms.Control.Paint>.  
  
## <a name="see-also"></a>Vedere anche  
 [Uso di un oggetto Pen per creare linee e forme](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)
