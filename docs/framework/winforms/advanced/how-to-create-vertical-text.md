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
ms.openlocfilehash: 7d66bf147a220bdcdfd32a703d3407817a184a54
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33521472"
---
# <a name="how-to-create-vertical-text"></a>Procedura: creare testo verticale
È possibile utilizzare un <xref:System.Drawing.StringFormat> per specificare che il testo da disegnare verticalmente anziché in orizzontale.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene assegnato il valore <xref:System.Drawing.StringFormatFlags.DirectionVertical> per il <xref:System.Drawing.StringFormat.FormatFlags%2A> proprietà di un <xref:System.Drawing.StringFormat> oggetto. Che <xref:System.Drawing.StringFormat> oggetto viene passato per il <xref:System.Drawing.Graphics.DrawString%2A> metodo la <xref:System.Drawing.Graphics> classe. Il valore <xref:System.Drawing.StringFormatFlags.DirectionVertical> è membro il <xref:System.Drawing.StringFormatFlags> enumerazione.  
  
 Nella figura seguente mostra il testo verticale.  
  
 ![Testo caratteri](../../../../docs/framework/winforms/advanced/media/csfontstext5.png "csfontstext5")  
  
 [!code-csharp[System.Drawing.FontsAndText#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.FontsAndText#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
  
-   L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs> `e` , ovvero un parametro di <xref:System.Windows.Forms.PaintEventHandler>.  
  
## <a name="see-also"></a>Vedere anche  
 [Procedura: Creare testo con GDI](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md)
