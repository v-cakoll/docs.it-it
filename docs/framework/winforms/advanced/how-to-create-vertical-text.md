---
title: 'Procedura: Creare testo verticale'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [Windows Forms], drawing vertical
- Windows Forms, drawing vertical text
- strings [Windows Forms], drawing vertical
- vertical text [Windows Forms], drawing
ms.assetid: 50c69046-4188-47d9-b949-cc2610ffd337
ms.openlocfilehash: 8398b3f18b764743bac19022b69e7f6fac0f7d57
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64625989"
---
# <a name="how-to-create-vertical-text"></a>Procedura: Creare testo verticale
È possibile usare un <xref:System.Drawing.StringFormat> oggetto per specificare che il testo da disegnare verticalmente anziché in orizzontale.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente assegna il valore <xref:System.Drawing.StringFormatFlags.DirectionVertical> per il <xref:System.Drawing.StringFormat.FormatFlags%2A> proprietà di un <xref:System.Drawing.StringFormat> oggetto. Che <xref:System.Drawing.StringFormat> oggetto viene passato per il <xref:System.Drawing.Graphics.DrawString%2A> metodo del <xref:System.Drawing.Graphics> classe. Il valore <xref:System.Drawing.StringFormatFlags.DirectionVertical> è un membro del <xref:System.Drawing.StringFormatFlags> enumerazione.  
  
 La figura seguente mostra il testo verticale: 
  
 ![Grafico che mostra il testo verticale del tipo di carattere.](./media/how-to-create-vertical-text/vertical-font-text-graphic.png)  
  
 [!code-csharp[System.Drawing.FontsAndText#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.FontsAndText#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
  
- L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs> `e` , ovvero un parametro di <xref:System.Windows.Forms.PaintEventHandler>.  
  
## <a name="see-also"></a>Vedere anche

- [Procedura: Creare testo con GDI](how-to-draw-text-with-gdi.md)
