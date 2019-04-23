---
title: "Procedura: Usare l'antialiasing nel testo"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- strings [Windows Forms], smoothing drawn
- antialiasing [Windows Forms], using with text
- text [Windows Forms], smoothing
- text [Windows Forms], antialiasing
- strings [Windows Forms], antialiasing when drawing
ms.assetid: 48fc34f3-f236-4b01-a0cb-f0752e6d22ae
ms.openlocfilehash: 24d1b1dfbe955bcfa98a16c3be592ab837ec0182
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59227613"
---
# <a name="how-to-use-antialiasing-with-text"></a>Procedura: Usare l'antialiasing nel testo
*Anti-aliasing* si intende l'anti-aliasing dei bordi irregolari della grafica e testo per migliorarne la leggibilità o aspetto disegnati. Con managed [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] classi, è possibile eseguire il rendering di testo con anti-aliasing di elevata qualità, nonché il testo di qualità inferiore. In genere, il rendering di qualità superiore impiega più tempo di elaborazione rispetto il rendering di qualità inferiore. Per impostare il livello di qualità del testo, impostare il <xref:System.Drawing.Graphics.TextRenderingHint%2A> proprietà di un <xref:System.Drawing.Graphics> a uno degli elementi del <xref:System.Drawing.Text.TextRenderingHint> enumerazione  
  
## <a name="example"></a>Esempio  
 Esempio di codice seguente crea testo con due diverse impostazioni di qualità.  
  
 [!code-csharp[System.Drawing.FontsAndText#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.FontsAndText#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#21)]  
 
 Nella figura seguente mostra l'output del codice di esempio:  
  
 ![Screenshot che mostra il testo con due diverse impostazioni di qualità.](./media/how-to-use-antialiasing-with-text/antialiasing-text-quality-settings.png)  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 Esempio di codice precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs> `e`, ovvero un parametro di <xref:System.Windows.Forms.PaintEventHandler>.  
  
## <a name="see-also"></a>Vedere anche

- [Uso di tipi di carattere e testo](using-fonts-and-text.md)
