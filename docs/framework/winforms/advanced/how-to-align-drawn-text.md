---
title: 'Procedura: Allineare il testo disegnato'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [Windows Forms], aligning
- Windows Forms, aligning drawn text
ms.assetid: 83c10a81-1a90-4b5c-98aa-2c6c4b280079
ms.openlocfilehash: 0e77e4d8eeb9d7a07115b89525ac80074afeb6e8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59323268"
---
# <a name="how-to-align-drawn-text"></a><span data-ttu-id="73578-102">Procedura: Allineare il testo disegnato</span><span class="sxs-lookup"><span data-stu-id="73578-102">How to: Align Drawn Text</span></span>
<span data-ttu-id="73578-103">Quando si esegue il disegno personalizzato, è spesso possibile centrare testo disegnato su un form o controllo.</span><span class="sxs-lookup"><span data-stu-id="73578-103">When you perform custom drawing, you may often want to center drawn text on a form or control.</span></span> <span data-ttu-id="73578-104">Per facilitare l'allineamento del testo disegnato con la <xref:System.Drawing.Graphics.DrawString%2A> o <xref:System.Windows.Forms.TextRenderer.DrawText%2A> metodi creando l'oggetto di formattazione corretta e impostare i flag di formato appropriato.</span><span class="sxs-lookup"><span data-stu-id="73578-104">You can easily align text drawn with the <xref:System.Drawing.Graphics.DrawString%2A> or <xref:System.Windows.Forms.TextRenderer.DrawText%2A> methods by creating the correct formatting object and setting the appropriate format flags.</span></span>  
  
### <a name="to-draw-centered-text-with-gdi-drawstring"></a><span data-ttu-id="73578-105">Per disegnare il testo con GDI + (DrawString) centrato</span><span class="sxs-lookup"><span data-stu-id="73578-105">To draw centered text with GDI+ (DrawString)</span></span>  
  
1. <span data-ttu-id="73578-106">Usare un <xref:System.Drawing.StringFormat> con l'appropriato <xref:System.Drawing.Graphics.DrawString%2A> metodo per specificare il testo centrato.</span><span class="sxs-lookup"><span data-stu-id="73578-106">Use a <xref:System.Drawing.StringFormat> with the appropriate <xref:System.Drawing.Graphics.DrawString%2A> method to specify centered text.</span></span>  
  
     [!code-csharp[System.Drawing.AlignDrawnText#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#10)]
     [!code-vb[System.Drawing.AlignDrawnText#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#10)]  
  
### <a name="to-draw-centered-text-with-gdi-drawtext"></a><span data-ttu-id="73578-107">Per disegnare il testo con GDI (DrawText) centrato</span><span class="sxs-lookup"><span data-stu-id="73578-107">To draw centered text with GDI (DrawText)</span></span>  
  
1. <span data-ttu-id="73578-108">Usare la <xref:System.Windows.Forms.TextFormatFlags> enumerazione per il wrapping, nonché verticalmente e orizzontalmente ruotava testo con l'appropriato <xref:System.Windows.Forms.TextRenderer.DrawText%2A> (metodo).</span><span class="sxs-lookup"><span data-stu-id="73578-108">Use the <xref:System.Windows.Forms.TextFormatFlags> enumeration for wrapping as well as vertically and horizontally centering text with the appropriate <xref:System.Windows.Forms.TextRenderer.DrawText%2A> method.</span></span>  
  
     [!code-csharp[System.Drawing.AlignDrawnText#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#20)]
     [!code-vb[System.Drawing.AlignDrawnText#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#20)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="73578-109">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="73578-109">Compiling the Code</span></span>  
 <span data-ttu-id="73578-110">Gli esempi di codice precedenti sono progettati per l'uso con Windows Form, e richiedono <xref:System.Windows.Forms.PaintEventArgs> `e`, ovvero un parametro di <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="73578-110">The preceding code examples are designed for use with Windows Forms, and they require <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73578-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="73578-111">See also</span></span>

- [<span data-ttu-id="73578-112">Procedura: Creare testo con GDI</span><span class="sxs-lookup"><span data-stu-id="73578-112">How to: Draw Text with GDI</span></span>](how-to-draw-text-with-gdi.md)
- [<span data-ttu-id="73578-113">Uso di tipi di carattere e testo</span><span class="sxs-lookup"><span data-stu-id="73578-113">Using Fonts and Text</span></span>](using-fonts-and-text.md)
- [<span data-ttu-id="73578-114">Procedura: Costruire i tipi di carattere e famiglie di caratteri</span><span class="sxs-lookup"><span data-stu-id="73578-114">How to: Construct Font Families and Fonts</span></span>](how-to-construct-font-families-and-fonts.md)
