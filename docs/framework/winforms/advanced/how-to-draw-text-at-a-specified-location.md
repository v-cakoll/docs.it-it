---
title: 'Procedura: creare testo in una posizione specificata'
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
ms.openlocfilehash: e55afd0629c1b9e6d30c8b31116ec28a718fcb4d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-draw-text-at-a-specified-location"></a>Procedura: creare testo in una posizione specificata
Quando si esegue il disegno personalizzato, è possibile disegnare testo in una singola riga orizzontale, a partire da un punto specificato. In questo modo è possibile creare testo utilizzando il <xref:System.Drawing.Graphics.DrawString%2A> metodo di overload di <xref:System.Drawing.Graphics> classe che accetta un <xref:System.Drawing.Point> o <xref:System.Drawing.PointF> parametro. Il <xref:System.Drawing.Graphics.DrawString%2A> metodo richiede anche un <xref:System.Drawing.Brush> e <xref:System.Drawing.Font>  
  
 È inoltre possibile utilizzare il <xref:System.Windows.Forms.TextRenderer.DrawText%2A> metodo di overload di <xref:System.Windows.Forms.TextRenderer> che accetta un <xref:System.Drawing.Point>. <xref:System.Windows.Forms.TextRenderer.DrawText%2A> richiede anche un <xref:System.Drawing.Color> e un <xref:System.Drawing.Font>.  
  
 Nella figura seguente mostra l'output di testo creato in un punto specificato quando si utilizza il <xref:System.Drawing.Graphics.DrawString%2A> il metodo di overload.  
  
 ![Testo caratteri](../../../../docs/framework/winforms/advanced/media/csfontstext1.png "csfontstext1")  
  
### <a name="to-draw-a-line-of-text-with-gdi"></a>Per disegnare una riga di testo con GDI+  
  
1.  Utilizzare il <xref:System.Drawing.Graphics.DrawString%2A> , passando il testo desiderato, <xref:System.Drawing.Point> o <xref:System.Drawing.PointF>, <xref:System.Drawing.Font>, e <xref:System.Drawing.Brush>.  
  
     [!code-csharp[System.Drawing.AlignDrawnText#30](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#30)]
     [!code-vb[System.Drawing.AlignDrawnText#30](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#30)]  
  
### <a name="to-draw-a-line-of-text-with-gdi"></a>Per disegnare una riga di testo con GDI  
  
1.  Utilizzare il <xref:System.Windows.Forms.TextRenderer.DrawText%2A> , passando il testo desiderato, <xref:System.Drawing.Point>, <xref:System.Drawing.Font>, e <xref:System.Drawing.Color>.  
  
     [!code-csharp[System.Drawing.AlignDrawnText#40](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#40)]
     [!code-vb[System.Drawing.AlignDrawnText#40](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#40)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 Gli esempi precedenti richiedono:  
  
-   <xref:System.Windows.Forms.PaintEventArgs>  `e`, ovvero un parametro di <xref:System.Windows.Forms.PaintEventHandler>.  
  
## <a name="see-also"></a>Vedere anche  
 [Procedura: Creare testo con GDI](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md)  
 [Uso di tipi di carattere e testo](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)  
 [Procedura: Creare caratteri e gruppi di caratteri](../../../../docs/framework/winforms/advanced/how-to-construct-font-families-and-fonts.md)  
 [Procedura: Creare testo disposto su più righe in un rettangolo](../../../../docs/framework/winforms/advanced/how-to-draw-wrapped-text-in-a-rectangle.md)
