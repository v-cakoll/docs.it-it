---
title: 'Procedura: Disegnare testo in un Windows Form'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- forms [Windows Forms], drawing text
- text [Windows Forms], drawing
ms.assetid: 5d2447a9-21a1-4adc-b954-5516f2bb9b2c
ms.openlocfilehash: ae7749deedba03f0a63bb74099d071d5da4fe27e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59172978"
---
# <a name="how-to-draw-text-on-a-windows-form"></a>Procedura: Disegnare testo in un Windows Form
Esempio di codice seguente viene illustrato come utilizzare il <xref:System.Drawing.Graphics.DrawString%2A> metodo del <xref:System.Drawing.Graphics> disegnare testo in un form. In alternativa, è possibile usare <xref:System.Windows.Forms.TextRenderer> per disegnare il testo in un form. Per altre informazioni, vedere [Procedura: Creare testo con GDI](how-to-draw-text-with-gdi.md).  
  
## <a name="example"></a>Esempio  
 [!code-cpp[System.Drawing.ConceptualHowTos#7](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#7)]
 [!code-csharp[System.Drawing.ConceptualHowTos#7](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#7)]
 [!code-vb[System.Drawing.ConceptualHowTos#7](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#7)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 Non è possibile chiamare il <xref:System.Drawing.Graphics.DrawString%2A> nel metodo il <xref:System.Windows.Forms.Form.Load> gestore dell'evento. Il contenuto creato non verrà ridisegnato se il form viene ridimensionato o nascosto da un altro form. Per rendere il contenuto viene ridisegnata automaticamente, è necessario eseguire l'override di <xref:System.Windows.Forms.Control.OnPaint%2A> (metodo).  
  
## <a name="robust-programming"></a>Programmazione efficiente  
 Le seguenti condizioni possono generare un'eccezione:  
  
-   Non è installato il tipo di carattere Arial.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Drawing.Graphics.DrawString%2A>
- <xref:System.Windows.Forms.TextRenderer.DrawText%2A>
- <xref:System.Drawing.StringFormat.FormatFlags%2A>
- <xref:System.Drawing.StringFormatFlags>
- <xref:System.Windows.Forms.TextFormatFlags>
- <xref:System.Windows.Forms.Control.OnPaint%2A>
- [Guida introduttiva alla programmazione grafica](getting-started-with-graphics-programming.md)
- [Procedura: Disegnare testo con GDI](how-to-draw-text-with-gdi.md)
