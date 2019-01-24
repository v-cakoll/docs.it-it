---
title: 'Procedura: Allineare il testo creato'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [Windows Forms], aligning
- Windows Forms, aligning drawn text
ms.assetid: 83c10a81-1a90-4b5c-98aa-2c6c4b280079
ms.openlocfilehash: 1cd6566e5eb5b60128206458c6e82b8eecf5492e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54632374"
---
# <a name="how-to-align-drawn-text"></a>Procedura: Allineare il testo creato
Quando si esegue il disegno personalizzato, è spesso possibile centrare testo disegnato su un form o controllo. Per facilitare l'allineamento del testo disegnato con la <xref:System.Drawing.Graphics.DrawString%2A> o <xref:System.Windows.Forms.TextRenderer.DrawText%2A> metodi creando l'oggetto di formattazione corretta e impostare i flag di formato appropriato.  
  
### <a name="to-draw-centered-text-with-gdi-drawstring"></a>Per disegnare il testo con GDI + (DrawString) centrato  
  
1.  Usare un <xref:System.Drawing.StringFormat> con l'appropriato <xref:System.Drawing.Graphics.DrawString%2A> metodo per specificare il testo centrato.  
  
     [!code-csharp[System.Drawing.AlignDrawnText#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#10)]
     [!code-vb[System.Drawing.AlignDrawnText#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#10)]  
  
### <a name="to-draw-centered-text-with-gdi-drawtext"></a>Per disegnare il testo con GDI (DrawText) centrato  
  
1.  Usare la <xref:System.Windows.Forms.TextFormatFlags> enumerazione per il wrapping, nonché verticalmente e orizzontalmente ruotava testo con l'appropriato <xref:System.Windows.Forms.TextRenderer.DrawText%2A> (metodo).  
  
     [!code-csharp[System.Drawing.AlignDrawnText#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#20)]
     [!code-vb[System.Drawing.AlignDrawnText#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#20)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 Gli esempi di codice precedenti sono progettati per l'uso con Windows Form, e richiedono <xref:System.Windows.Forms.PaintEventArgs> `e`, ovvero un parametro di <xref:System.Windows.Forms.PaintEventHandler>.  
  
## <a name="see-also"></a>Vedere anche
- [Procedura: Creare testo con GDI](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md)
- [Uso di tipi di carattere e testo](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)
- [Procedura: Costruire i tipi di carattere e famiglie di caratteri](../../../../docs/framework/winforms/advanced/how-to-construct-font-families-and-fonts.md)
