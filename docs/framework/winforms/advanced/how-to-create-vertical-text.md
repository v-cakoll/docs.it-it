---
title: 'Procedura: creare testo verticale'
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
ms.openlocfilehash: 86401342625f593945b801f7619ef9ca9681317c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182552"
---
# <a name="how-to-create-vertical-text"></a>Procedura: creare testo verticale
È possibile <xref:System.Drawing.StringFormat> utilizzare un oggetto per specificare che il testo venga disegnato verticalmente anziché orizzontalmente.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene <xref:System.Drawing.StringFormatFlags.DirectionVertical> assegnato <xref:System.Drawing.StringFormat.FormatFlags%2A> il <xref:System.Drawing.StringFormat> valore alla proprietà di un oggetto . Tale <xref:System.Drawing.StringFormat> oggetto viene <xref:System.Drawing.Graphics.DrawString%2A> passato al <xref:System.Drawing.Graphics> metodo della classe. Il <xref:System.Drawing.StringFormatFlags.DirectionVertical> valore è un <xref:System.Drawing.StringFormatFlags> membro dell'enumerazione.  
  
 La figura seguente mostra il testo verticale:
  
 ![Immagine che mostra il testo del carattere verticale.](./media/how-to-create-vertical-text/vertical-font-text-graphic.png)  
  
 [!code-csharp[System.Drawing.FontsAndText#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.FontsAndText#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
  
- L'esempio precedente è progettato per l'utilizzo con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs> `e` , che è un parametro di <xref:System.Windows.Forms.PaintEventHandler>.  
  
## <a name="see-also"></a>Vedere anche

- [Procedura: creare testo con GDI](how-to-draw-text-with-gdi.md)
