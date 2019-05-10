---
title: 'Procedura: Disegnare testo in una posizione specificata'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [Windows Forms], drawing at specified locations [Windows Forms]
- drawing text
- drawing text [Windows Forms], specified locations [Windows Forms]
- Windows Forms, drawing text at a specified location
ms.assetid: 60816423-1c38-465e-980d-2c2b64d74086
ms.openlocfilehash: 0c36b00e4f6f71f0ecf8042853bb8e99e57854da
ms.sourcegitcommit: e08b319358a8025cc6aa38737854f7bdb87183d6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/29/2019
ms.locfileid: "64912418"
---
# <a name="how-to-draw-text-at-a-specified-location"></a><span data-ttu-id="8096d-102">Procedura: Disegnare testo in una posizione specificata</span><span class="sxs-lookup"><span data-stu-id="8096d-102">How to: Draw Text at a Specified Location</span></span>
<span data-ttu-id="8096d-103">Quando si esegue il disegno personalizzato, è possibile disegnare testo in una singola riga orizzontale iniziando in corrispondenza di un punto specificato.</span><span class="sxs-lookup"><span data-stu-id="8096d-103">When you perform custom drawing, you can draw text in a single horizontal line starting at a specified point.</span></span> <span data-ttu-id="8096d-104">In questo modo è possibile creare testo utilizzando il <xref:System.Drawing.Graphics.DrawString%2A> metodo di overload di <xref:System.Drawing.Graphics> classe che accetta un <xref:System.Drawing.Point> o <xref:System.Drawing.PointF> parametro.</span><span class="sxs-lookup"><span data-stu-id="8096d-104">You can draw text in this manner by using the <xref:System.Drawing.Graphics.DrawString%2A> overloaded method of the <xref:System.Drawing.Graphics> class that takes a <xref:System.Drawing.Point> or <xref:System.Drawing.PointF> parameter.</span></span> <span data-ttu-id="8096d-105">Il <xref:System.Drawing.Graphics.DrawString%2A> metodo richiede anche un <xref:System.Drawing.Brush> e <xref:System.Drawing.Font></span><span class="sxs-lookup"><span data-stu-id="8096d-105">The <xref:System.Drawing.Graphics.DrawString%2A> method also requires a <xref:System.Drawing.Brush> and <xref:System.Drawing.Font></span></span>  
  
 <span data-ttu-id="8096d-106">È anche possibile usare la <xref:System.Windows.Forms.TextRenderer.DrawText%2A> metodo di overload di <xref:System.Windows.Forms.TextRenderer> che accetta un <xref:System.Drawing.Point>.</span><span class="sxs-lookup"><span data-stu-id="8096d-106">You can also use the <xref:System.Windows.Forms.TextRenderer.DrawText%2A> overloaded method of the <xref:System.Windows.Forms.TextRenderer> that takes a <xref:System.Drawing.Point>.</span></span> <span data-ttu-id="8096d-107"><xref:System.Windows.Forms.TextRenderer.DrawText%2A> richiede anche un <xref:System.Drawing.Color> e un <xref:System.Drawing.Font>.</span><span class="sxs-lookup"><span data-stu-id="8096d-107"><xref:System.Windows.Forms.TextRenderer.DrawText%2A> also requires a <xref:System.Drawing.Color> and a <xref:System.Drawing.Font>.</span></span>  
  
 <span data-ttu-id="8096d-108">La figura seguente mostra l'output del testo disegnato in un momento specificato quando si usa il <xref:System.Drawing.Graphics.DrawString%2A> il metodo di overload.</span><span class="sxs-lookup"><span data-stu-id="8096d-108">The following illustration shows the output of text drawn at a specified point when you use the <xref:System.Drawing.Graphics.DrawString%2A> overloaded method.</span></span>  
  
 ![Screenshot che mostra l'output di testo in un momento specificato.](./media/how-to-draw-text-at-a-specified-location/font-text-specified-point.png)  
  
### <a name="to-draw-a-line-of-text-with-gdi"></a><span data-ttu-id="8096d-110">Per disegnare una riga di testo con GDI+</span><span class="sxs-lookup"><span data-stu-id="8096d-110">To draw a line of text with GDI+</span></span>  
  
1. <span data-ttu-id="8096d-111">Usare la <xref:System.Drawing.Graphics.DrawString%2A> metodo, il testo desiderato, passando <xref:System.Drawing.Point> oppure <xref:System.Drawing.PointF>, <xref:System.Drawing.Font>, e <xref:System.Drawing.Brush>.</span><span class="sxs-lookup"><span data-stu-id="8096d-111">Use the <xref:System.Drawing.Graphics.DrawString%2A> method, passing the text you want, <xref:System.Drawing.Point> or <xref:System.Drawing.PointF>, <xref:System.Drawing.Font>, and <xref:System.Drawing.Brush>.</span></span>  
  
     [!code-csharp[System.Drawing.AlignDrawnText#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#30)]
     [!code-vb[System.Drawing.AlignDrawnText#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#30)]  
  
### <a name="to-draw-a-line-of-text-with-gdi"></a><span data-ttu-id="8096d-112">Per disegnare una riga di testo con GDI</span><span class="sxs-lookup"><span data-stu-id="8096d-112">To draw a line of text with GDI</span></span>  
  
1. <span data-ttu-id="8096d-113">Usare la <xref:System.Windows.Forms.TextRenderer.DrawText%2A> metodo, il testo desiderato, passando <xref:System.Drawing.Point>, <xref:System.Drawing.Font>, e <xref:System.Drawing.Color>.</span><span class="sxs-lookup"><span data-stu-id="8096d-113">Use the <xref:System.Windows.Forms.TextRenderer.DrawText%2A> method, passing the text you want, <xref:System.Drawing.Point>, <xref:System.Drawing.Font>, and <xref:System.Drawing.Color>.</span></span>  
  
     [!code-csharp[System.Drawing.AlignDrawnText#40](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#40)]
     [!code-vb[System.Drawing.AlignDrawnText#40](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#40)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="8096d-114">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="8096d-114">Compiling the Code</span></span>  
 <span data-ttu-id="8096d-115">Gli esempi precedenti è necessario:</span><span class="sxs-lookup"><span data-stu-id="8096d-115">The previous examples require:</span></span>  
  
- <span data-ttu-id="8096d-116"><xref:System.Windows.Forms.PaintEventArgs>  `e`, ovvero un parametro di <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="8096d-116"><xref:System.Windows.Forms.PaintEventArgs>  `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8096d-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8096d-117">See also</span></span>

- [<span data-ttu-id="8096d-118">Procedura: Creare testo con GDI</span><span class="sxs-lookup"><span data-stu-id="8096d-118">How to: Draw Text with GDI</span></span>](how-to-draw-text-with-gdi.md)
- [<span data-ttu-id="8096d-119">Uso di tipi di carattere e testo</span><span class="sxs-lookup"><span data-stu-id="8096d-119">Using Fonts and Text</span></span>](using-fonts-and-text.md)
- [<span data-ttu-id="8096d-120">Procedura: Costruire i tipi di carattere e famiglie di caratteri</span><span class="sxs-lookup"><span data-stu-id="8096d-120">How to: Construct Font Families and Fonts</span></span>](how-to-construct-font-families-and-fonts.md)
- [<span data-ttu-id="8096d-121">Procedura: Disegnare testo sottoposto a wrapping in un rettangolo</span><span class="sxs-lookup"><span data-stu-id="8096d-121">How to: Draw Wrapped Text in a Rectangle</span></span>](how-to-draw-wrapped-text-in-a-rectangle.md)
