---
title: "Procedura: utilizzare l'antialiasing nel testo"
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
ms.openlocfilehash: 632ed329173d134495a424b34ca7c71e402607bf
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182478"
---
# <a name="how-to-use-antialiasing-with-text"></a>Procedura: utilizzare l'antialiasing nel testo
*L'antialiasing* si riferisce all'arrotondamento dei bordi frastagliati di grafica e testo disegnati per migliorarne l'aspetto o la leggibilità. Con le classi GDI, è possibile eseguire il rendering di testo con antialiasing di alta qualità, nonché di testo di qualità inferiore. In genere, il rendering di qualità superiore richiede più tempo di elaborazione rispetto al rendering di qualità inferiore. Per impostare il livello <xref:System.Drawing.Graphics.TextRenderingHint%2A> di qualità <xref:System.Drawing.Graphics> del testo, impostare la proprietà di a su uno degli elementi dell'enumerazione <xref:System.Drawing.Text.TextRenderingHint>  
  
## <a name="example"></a>Esempio  
 Esempio di codice seguente disegna testo con due diverse impostazioni di qualità.  
  
 [!code-csharp[System.Drawing.FontsAndText#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.FontsAndText#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#21)]  

 La figura seguente mostra l'output del codice di esempio:  
  
 ![Screenshot che mostra il testo con due diverse impostazioni di qualità.](./media/how-to-use-antialiasing-with-text/antialiasing-text-quality-settings.png)  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio di codice precedente è progettato per <xref:System.Windows.Forms.PaintEventArgs> `e`l'utilizzo con <xref:System.Windows.Forms.PaintEventHandler>Windows Form e richiede , che è un parametro di .  
  
## <a name="see-also"></a>Vedere anche

- [Utilizzo di tipi di carattere e testo](using-fonts-and-text.md)
