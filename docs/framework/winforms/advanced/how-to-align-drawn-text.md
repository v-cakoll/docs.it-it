---
title: 'Procedura: Allineare il testo disegnato'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [Windows Forms], aligning
- Windows Forms, aligning drawn text
ms.assetid: 83c10a81-1a90-4b5c-98aa-2c6c4b280079
ms.openlocfilehash: 0e77e4d8eeb9d7a07115b89525ac80074afeb6e8
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59323268"
---
# <a name="how-to-align-drawn-text"></a>Procedura: Allineare il testo disegnato
Quando si esegue il disegno personalizzato, è spesso possibile centrare testo disegnato su un form o controllo. Per facilitare l'allineamento del testo disegnato con la <xref:System.Drawing.Graphics.DrawString%2A> o <xref:System.Windows.Forms.TextRenderer.DrawText%2A> metodi creando l'oggetto di formattazione corretta e impostare i flag di formato appropriato.  
  
### <a name="to-draw-centered-text-with-gdi-drawstring"></a>Per disegnare il testo con GDI + (DrawString) centrato  
  
1. Usare un <xref:System.Drawing.StringFormat> con l'appropriato <xref:System.Drawing.Graphics.DrawString%2A> metodo per specificare il testo centrato.  
  
     [!code-csharp[System.Drawing.AlignDrawnText#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#10)]
     [!code-vb[System.Drawing.AlignDrawnText#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#10)]  
  
### <a name="to-draw-centered-text-with-gdi-drawtext"></a>Per disegnare il testo con GDI (DrawText) centrato  
  
1. Usare la <xref:System.Windows.Forms.TextFormatFlags> enumerazione per il wrapping, nonché verticalmente e orizzontalmente ruotava testo con l'appropriato <xref:System.Windows.Forms.TextRenderer.DrawText%2A> (metodo).  
  
     [!code-csharp[System.Drawing.AlignDrawnText#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#20)]
     [!code-vb[System.Drawing.AlignDrawnText#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#20)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 Gli esempi di codice precedenti sono progettati per l'uso con Windows Form, e richiedono <xref:System.Windows.Forms.PaintEventArgs>`e`, ovvero un parametro di <xref:System.Windows.Forms.PaintEventHandler>.  
  
## <a name="see-also"></a>Vedere anche

- [Procedura: Disegnare testo con GDI](how-to-draw-text-with-gdi.md)
- [Utilizzo di tipi di carattere e testo](using-fonts-and-text.md)
- [Procedura: Creare tipi di carattere e famiglie di caratteri](how-to-construct-font-families-and-fonts.md)
