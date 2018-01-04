---
title: 'Procedura: allineare il testo creato'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [Windows Forms], aligning
- Windows Forms, aligning drawn text
ms.assetid: 83c10a81-1a90-4b5c-98aa-2c6c4b280079
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6be28641073bf430b1dc51c428228d0fb114d4cc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-align-drawn-text"></a>Procedura: allineare il testo creato
Quando si esegue il disegno personalizzato, è spesso necessario allineare al centro il testo disegnato su un form o controllo. Per facilitare l'allineamento del testo disegnato con il <xref:System.Drawing.Graphics.DrawString%2A> o <xref:System.Windows.Forms.TextRenderer.DrawText%2A> metodi di creazione dell'oggetto di formattazione corretta e impostando il flag di formato appropriati.  
  
### <a name="to-draw-centered-text-with-gdi-drawstring"></a>Per disegnare il testo centrato con GDI+ (DrawString)  
  
1.  Utilizzare un <xref:System.Drawing.StringFormat> con l'appropriato <xref:System.Drawing.Graphics.DrawString%2A> per specificare il testo centrato.  
  
     [!code-csharp[System.Drawing.AlignDrawnText#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#10)]
     [!code-vb[System.Drawing.AlignDrawnText#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#10)]  
  
### <a name="to-draw-centered-text-with-gdi-drawtext"></a>Per disegnare il testo centrato con GDI (DrawText)  
  
1.  Utilizzare il <xref:System.Windows.Forms.TextFormatFlags> enumerazione per il wrapping di centratura verticalmente e orizzontalmente testo con l'appropriato <xref:System.Windows.Forms.TextRenderer.DrawText%2A> metodo.  
  
     [!code-csharp[System.Drawing.AlignDrawnText#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#20)]
     [!code-vb[System.Drawing.AlignDrawnText#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#20)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 Gli esempi di codice precedente sono progettati per l'uso con Windows Form e richiedono <xref:System.Windows.Forms.PaintEventArgs> `e`, ovvero un parametro di <xref:System.Windows.Forms.PaintEventHandler>.  
  
## <a name="see-also"></a>Vedere anche  
 [Procedura: Creare testo con GDI](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md)  
 [Uso di tipi di carattere e testo](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)  
 [Procedura: Creare caratteri e gruppi di caratteri](../../../../docs/framework/winforms/advanced/how-to-construct-font-families-and-fonts.md)
