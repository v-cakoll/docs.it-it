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
ms.openlocfilehash: a2f2f6bd088ad58277839cf7e32a98d67ca3bd15
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-align-drawn-text"></a><span data-ttu-id="c5090-102">Procedura: allineare il testo creato</span><span class="sxs-lookup"><span data-stu-id="c5090-102">How to: Align Drawn Text</span></span>
<span data-ttu-id="c5090-103">Quando si esegue il disegno personalizzato, è spesso necessario allineare al centro il testo disegnato su un form o controllo.</span><span class="sxs-lookup"><span data-stu-id="c5090-103">When you perform custom drawing, you may often want to center drawn text on a form or control.</span></span> <span data-ttu-id="c5090-104">Per facilitare l'allineamento del testo disegnato con il <xref:System.Drawing.Graphics.DrawString%2A> o <xref:System.Windows.Forms.TextRenderer.DrawText%2A> metodi di creazione dell'oggetto di formattazione corretta e impostando il flag di formato appropriati.</span><span class="sxs-lookup"><span data-stu-id="c5090-104">You can easily align text drawn with the <xref:System.Drawing.Graphics.DrawString%2A> or <xref:System.Windows.Forms.TextRenderer.DrawText%2A> methods by creating the correct formatting object and setting the appropriate format flags.</span></span>  
  
### <a name="to-draw-centered-text-with-gdi-drawstring"></a><span data-ttu-id="c5090-105">Per disegnare il testo centrato con GDI+ (DrawString)</span><span class="sxs-lookup"><span data-stu-id="c5090-105">To draw centered text with GDI+ (DrawString)</span></span>  
  
1.  <span data-ttu-id="c5090-106">Utilizzare un <xref:System.Drawing.StringFormat> con l'appropriato <xref:System.Drawing.Graphics.DrawString%2A> per specificare il testo centrato.</span><span class="sxs-lookup"><span data-stu-id="c5090-106">Use a <xref:System.Drawing.StringFormat> with the appropriate <xref:System.Drawing.Graphics.DrawString%2A> method to specify centered text.</span></span>  
  
     [!code-csharp[System.Drawing.AlignDrawnText#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#10)]
     [!code-vb[System.Drawing.AlignDrawnText#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#10)]  
  
### <a name="to-draw-centered-text-with-gdi-drawtext"></a><span data-ttu-id="c5090-107">Per disegnare il testo centrato con GDI (DrawText)</span><span class="sxs-lookup"><span data-stu-id="c5090-107">To draw centered text with GDI (DrawText)</span></span>  
  
1.  <span data-ttu-id="c5090-108">Utilizzare il <xref:System.Windows.Forms.TextFormatFlags> enumerazione per il wrapping di centratura verticalmente e orizzontalmente testo con l'appropriato <xref:System.Windows.Forms.TextRenderer.DrawText%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="c5090-108">Use the <xref:System.Windows.Forms.TextFormatFlags> enumeration for wrapping as well as vertically and horizontally centering text with the appropriate <xref:System.Windows.Forms.TextRenderer.DrawText%2A> method.</span></span>  
  
     [!code-csharp[System.Drawing.AlignDrawnText#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#20)]
     [!code-vb[System.Drawing.AlignDrawnText#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#20)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="c5090-109">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="c5090-109">Compiling the Code</span></span>  
 <span data-ttu-id="c5090-110">Gli esempi di codice precedente sono progettati per l'uso con Windows Form e richiedono <xref:System.Windows.Forms.PaintEventArgs> `e`, ovvero un parametro di <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="c5090-110">The preceding code examples are designed for use with Windows Forms, and they require <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5090-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c5090-111">See Also</span></span>  
 [<span data-ttu-id="c5090-112">Procedura: Creare testo con GDI</span><span class="sxs-lookup"><span data-stu-id="c5090-112">How to: Draw Text with GDI</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md)  
 [<span data-ttu-id="c5090-113">Uso di tipi di carattere e testo</span><span class="sxs-lookup"><span data-stu-id="c5090-113">Using Fonts and Text</span></span>](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)  
 [<span data-ttu-id="c5090-114">Procedura: Creare caratteri e gruppi di caratteri</span><span class="sxs-lookup"><span data-stu-id="c5090-114">How to: Construct Font Families and Fonts</span></span>](../../../../docs/framework/winforms/advanced/how-to-construct-font-families-and-fonts.md)
