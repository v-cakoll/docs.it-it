---
title: 'Procedura: Disegnare testo in una posizione specificata'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [Windows Forms], drawing at specified locations [Windows Forms]
- drawing text
- drawing text [Windows Forms], specified locations [Windows Forms]
- Windows Forms, drawing text at a specified location
ms.assetid: 60816423-1c38-465e-980d-2c2b64d74086
ms.openlocfilehash: 3bca6cd364ed4e0d0179c13fb378449b7cf05739
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57705346"
---
# <a name="how-to-draw-text-at-a-specified-location"></a>Procedura: Disegnare testo in una posizione specificata
Quando si esegue il disegno personalizzato, è possibile disegnare testo in una singola riga orizzontale iniziando in corrispondenza di un punto specificato. In questo modo è possibile creare testo utilizzando il <xref:System.Drawing.Graphics.DrawString%2A> metodo di overload di <xref:System.Drawing.Graphics> classe che accetta un <xref:System.Drawing.Point> o <xref:System.Drawing.PointF> parametro. Il <xref:System.Drawing.Graphics.DrawString%2A> metodo richiede anche un <xref:System.Drawing.Brush> e <xref:System.Drawing.Font>  
  
 È anche possibile usare la <xref:System.Windows.Forms.TextRenderer.DrawText%2A> metodo di overload di <xref:System.Windows.Forms.TextRenderer> che accetta un <xref:System.Drawing.Point>. <xref:System.Windows.Forms.TextRenderer.DrawText%2A> richiede anche un <xref:System.Drawing.Color> e un <xref:System.Drawing.Font>.  
  
 La figura seguente mostra l'output del testo disegnato in un momento specificato quando si usa il <xref:System.Drawing.Graphics.DrawString%2A> il metodo di overload.  
  
 ![I tipi di carattere testo](./media/csfontstext1.png "csfontstext1")  
  
### <a name="to-draw-a-line-of-text-with-gdi"></a>Per disegnare una riga di testo con GDI+  
  
1.  Usare la <xref:System.Drawing.Graphics.DrawString%2A> metodo, il testo desiderato, passando <xref:System.Drawing.Point> oppure <xref:System.Drawing.PointF>, <xref:System.Drawing.Font>, e <xref:System.Drawing.Brush>.  
  
     [!code-csharp[System.Drawing.AlignDrawnText#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#30)]
     [!code-vb[System.Drawing.AlignDrawnText#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#30)]  
  
### <a name="to-draw-a-line-of-text-with-gdi"></a>Per disegnare una riga di testo con GDI  
  
1.  Usare la <xref:System.Windows.Forms.TextRenderer.DrawText%2A> metodo, il testo desiderato, passando <xref:System.Drawing.Point>, <xref:System.Drawing.Font>, e <xref:System.Drawing.Color>.  
  
     [!code-csharp[System.Drawing.AlignDrawnText#40](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#40)]
     [!code-vb[System.Drawing.AlignDrawnText#40](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#40)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 Gli esempi precedenti è necessario:  
  
-   <xref:System.Windows.Forms.PaintEventArgs>  `e`, ovvero un parametro di <xref:System.Windows.Forms.PaintEventHandler>.  
  
## <a name="see-also"></a>Vedere anche
- [Procedura: Creare testo con GDI](how-to-draw-text-with-gdi.md)
- [Uso di tipi di carattere e testo](using-fonts-and-text.md)
- [Procedura: Costruire i tipi di carattere e famiglie di caratteri](how-to-construct-font-families-and-fonts.md)
- [Procedura: Disegnare testo sottoposto a wrapping in un rettangolo](how-to-draw-wrapped-text-in-a-rectangle.md)
