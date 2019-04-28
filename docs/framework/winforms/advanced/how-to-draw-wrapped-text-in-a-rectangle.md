---
title: 'Procedura: Disegnare testo disposto su più righe in un rettangolo'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, drawing text in a rectangle
- text [Windows Forms], drawing in a rectangle
- strings [Windows Forms], drawing in a rectangle
ms.assetid: e1fb432a-dc90-48b5-9b6b-acc14507133d
ms.openlocfilehash: 8e5c7cab1f977bef0570b2e540d7bf3a630aceb0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61781406"
---
# <a name="how-to-draw-wrapped-text-in-a-rectangle"></a>Procedura: Disegnare testo disposto su più righe in un rettangolo
È possibile disegnare testo sottoposto a wrapping in un rettangolo utilizzando il <xref:System.Drawing.Graphics.DrawString%2A> metodo di overload di <xref:System.Drawing.Graphics> classe che accetta un <xref:System.Drawing.Rectangle> o <xref:System.Drawing.RectangleF> parametro. Si utilizzerà inoltre un <xref:System.Drawing.Brush> e un <xref:System.Drawing.Font>.  
  
 È anche possibile disegnare testo sottoposto a wrapping in un rettangolo utilizzando il <xref:System.Windows.Forms.TextRenderer.DrawText%2A> metodo di overload di <xref:System.Windows.Forms.TextRenderer> che accetta un <xref:System.Drawing.Rectangle> e un <xref:System.Windows.Forms.TextFormatFlags> parametro. Si utilizzerà inoltre un <xref:System.Drawing.Color> e un <xref:System.Drawing.Font>.  
  
 La figura seguente mostra l'output del testo disegnato nel rettangolo, quando si usa il <xref:System.Drawing.Graphics.DrawString%2A> metodo:
  
 ![Screenshot che mostra l'output quando si usa il metodo DrawString.](./media/how-to-draw-wrapped-text-in-a-rectangle/drawstring-method-font-text.png)  
  
### <a name="to-draw-wrapped-text-in-a-rectangle-with-gdi"></a>Per disegnare il wrapping di testo in un rettangolo con GDI+  
  
1. Usare la <xref:System.Drawing.Graphics.DrawString%2A> sottoposti a overload di metodo, il testo desiderato, passando <xref:System.Drawing.Rectangle> o <xref:System.Drawing.RectangleF>, <xref:System.Drawing.Font> e <xref:System.Drawing.Brush>.  
  
     [!code-csharp[System.Drawing.AlignDrawnText#50](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#50)]
     [!code-vb[System.Drawing.AlignDrawnText#50](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#50)]  
  
### <a name="to-draw-wrapped-text-in-a-rectangle-with-gdi"></a>Per disegnare il wrapping di testo in un rettangolo con GDI  
  
1. Usare la <xref:System.Windows.Forms.TextFormatFlags> valore di enumerazione per specificare il testo deve essere racchiuso tra parentesi il <xref:System.Windows.Forms.TextRenderer.DrawText%2A> sottoposto a overload, passando il testo desiderato, <xref:System.Drawing.Rectangle>, <xref:System.Drawing.Font> e <xref:System.Drawing.Color>.  
  
     [!code-csharp[System.Drawing.AlignDrawnText#60](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#60)]
     [!code-vb[System.Drawing.AlignDrawnText#60](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#60)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 Gli esempi precedenti è necessario:  
  
- <xref:System.Windows.Forms.PaintEventArgs> `e`, ovvero un parametro di <xref:System.Windows.Forms.PaintEventHandler>.  
  
## <a name="see-also"></a>Vedere anche

- [Procedura: Creare testo con GDI](how-to-draw-text-with-gdi.md)
- [Uso di tipi di carattere e testo](using-fonts-and-text.md)
- [Procedura: Costruire i tipi di carattere e famiglie di caratteri](how-to-construct-font-families-and-fonts.md)
- [Procedura: Disegnare testo in una posizione specificata](how-to-draw-text-at-a-specified-location.md)
