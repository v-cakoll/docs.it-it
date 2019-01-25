---
title: 'Procedura: Creare testo con GDI'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- GDI [Windows Forms], drawing text [Windows Forms]
- text [Windows Forms], drawing with TextRenderer
- drawing [Windows Forms], text
- Windows Forms, drawing text with GDI
ms.assetid: 2a19fe5d-2ace-451c-94db-01cb1118ef7b
ms.openlocfilehash: 3cb67f01f145a55e4e8a68642a37ad287ee94b1a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54685923"
---
# <a name="how-to-draw-text-with-gdi"></a>Procedura: Creare testo con GDI
Con il <xref:System.Windows.Forms.TextRenderer.DrawText%2A> metodo nella <xref:System.Windows.Forms.TextRenderer> (classe), è possibile accedere [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] funzionalità per il disegno di testo in un form o controllo. [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] il rendering del testo offre in genere prestazioni migliori e misurazione del testo più accurata [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].  
  
> [!NOTE]
>  Il <xref:System.Windows.Forms.TextRenderer.DrawText%2A> metodi del <xref:System.Windows.Forms.TextRenderer> classe non sono supportati per la stampa. Quando si stampa, utilizzare sempre il <xref:System.Drawing.Graphics.DrawString%2A> metodi del <xref:System.Drawing.Graphics> classe.  
  
## <a name="example"></a>Esempio  
 Esempio di codice seguente viene illustrato come creare testo su più righe all'interno di un rettangolo utilizzando il <xref:System.Windows.Forms.TextRenderer.DrawText%2A> (metodo).  
  
 [!code-csharp[System.Windows.Forms.TextRendererExamples#7](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.TextRendererExamples/CS/Form1.cs#7)]
 [!code-vb[System.Windows.Forms.TextRendererExamples#7](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.TextRendererExamples/VB/Form1.vb#7)]  
  
 Per il rendering del testo con il <xref:System.Windows.Forms.TextRenderer> (classe), è necessario un <xref:System.Drawing.IDeviceContext>, ad esempio un <xref:System.Drawing.Graphics> e un <xref:System.Drawing.Font>, un percorso in cui disegnare il testo e il colore in cui deve essere disegnato. Facoltativamente, è possibile specificare il formattazione del testo utilizzando il <xref:System.Windows.Forms.TextFormatFlags> enumerazione.  
  
 Per altre informazioni su come ottenere un <xref:System.Drawing.Graphics>, vedere [come: Creare oggetti Graphics per disegnare](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md). Per altre informazioni sulla creazione di un <xref:System.Drawing.Font>, vedere [come: Creare le famiglie di caratteri e caratteri](../../../../docs/framework/winforms/advanced/how-to-construct-font-families-and-fonts.md).  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 Esempio di codice precedente è progettato per l'uso con Windows Form e richiede la <xref:System.Windows.Forms.PaintEventArgs> `e`, ovvero un parametro di <xref:System.Windows.Forms.PaintEventHandler>.  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.Forms.TextRenderer>
- <xref:System.Drawing.Font>
- <xref:System.Drawing.Color>
- <xref:System.Drawing.Color>
- [Uso di tipi di carattere e testo](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)
