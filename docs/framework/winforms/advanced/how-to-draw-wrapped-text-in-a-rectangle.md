---
title: 'Procedura: Disegnare testo sottoposto a wrapping in un rettangolo'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, drawing text in a rectangle
- text [Windows Forms], drawing in a rectangle
- strings [Windows Forms], drawing in a rectangle
ms.assetid: e1fb432a-dc90-48b5-9b6b-acc14507133d
ms.openlocfilehash: 5c4e76cda37527d0167b21c0d206749ba6dab4a9
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57708860"
---
# <a name="how-to-draw-wrapped-text-in-a-rectangle"></a><span data-ttu-id="2ec85-102">Procedura: Disegnare testo sottoposto a wrapping in un rettangolo</span><span class="sxs-lookup"><span data-stu-id="2ec85-102">How to: Draw Wrapped Text in a Rectangle</span></span>
<span data-ttu-id="2ec85-103">È possibile disegnare testo sottoposto a wrapping in un rettangolo utilizzando il <xref:System.Drawing.Graphics.DrawString%2A> metodo di overload di <xref:System.Drawing.Graphics> classe che accetta un <xref:System.Drawing.Rectangle> o <xref:System.Drawing.RectangleF> parametro.</span><span class="sxs-lookup"><span data-stu-id="2ec85-103">You can draw wrapped text in a rectangle by using the <xref:System.Drawing.Graphics.DrawString%2A> overloaded method of the <xref:System.Drawing.Graphics> class that takes a <xref:System.Drawing.Rectangle> or <xref:System.Drawing.RectangleF> parameter.</span></span> <span data-ttu-id="2ec85-104">Si utilizzerà inoltre un <xref:System.Drawing.Brush> e un <xref:System.Drawing.Font>.</span><span class="sxs-lookup"><span data-stu-id="2ec85-104">You will also use a <xref:System.Drawing.Brush> and a <xref:System.Drawing.Font>.</span></span>  
  
 <span data-ttu-id="2ec85-105">È anche possibile disegnare testo sottoposto a wrapping in un rettangolo utilizzando il <xref:System.Windows.Forms.TextRenderer.DrawText%2A> metodo di overload di <xref:System.Windows.Forms.TextRenderer> che accetta un <xref:System.Drawing.Rectangle> e un <xref:System.Windows.Forms.TextFormatFlags> parametro.</span><span class="sxs-lookup"><span data-stu-id="2ec85-105">You can also draw wrapped text in a rectangle by using the <xref:System.Windows.Forms.TextRenderer.DrawText%2A> overloaded method of the <xref:System.Windows.Forms.TextRenderer> that takes a <xref:System.Drawing.Rectangle> and a <xref:System.Windows.Forms.TextFormatFlags> parameter.</span></span> <span data-ttu-id="2ec85-106">Si utilizzerà inoltre un <xref:System.Drawing.Color> e un <xref:System.Drawing.Font>.</span><span class="sxs-lookup"><span data-stu-id="2ec85-106">You will also use a <xref:System.Drawing.Color> and a <xref:System.Drawing.Font>.</span></span>  
  
 <span data-ttu-id="2ec85-107">La figura seguente mostra l'output del testo disegnato nel rettangolo, quando si usa il <xref:System.Drawing.Graphics.DrawString%2A> (metodo).</span><span class="sxs-lookup"><span data-stu-id="2ec85-107">The following illustration shows the output of text drawn in the rectangle when you use the <xref:System.Drawing.Graphics.DrawString%2A> method.</span></span>  
  
 <span data-ttu-id="2ec85-108">![I tipi di carattere testo](./media/csfontstext2.png "csfontstext2")</span><span class="sxs-lookup"><span data-stu-id="2ec85-108">![Fonts Text](./media/csfontstext2.png "csfontstext2")</span></span>  
  
### <a name="to-draw-wrapped-text-in-a-rectangle-with-gdi"></a><span data-ttu-id="2ec85-109">Per disegnare il wrapping di testo in un rettangolo con GDI+</span><span class="sxs-lookup"><span data-stu-id="2ec85-109">To draw wrapped text in a rectangle with GDI+</span></span>  
  
1.  <span data-ttu-id="2ec85-110">Usare la <xref:System.Drawing.Graphics.DrawString%2A> sottoposti a overload di metodo, il testo desiderato, passando <xref:System.Drawing.Rectangle> o <xref:System.Drawing.RectangleF>, <xref:System.Drawing.Font> e <xref:System.Drawing.Brush>.</span><span class="sxs-lookup"><span data-stu-id="2ec85-110">Use the <xref:System.Drawing.Graphics.DrawString%2A> overloaded method, passing the text you want, <xref:System.Drawing.Rectangle> or <xref:System.Drawing.RectangleF>, <xref:System.Drawing.Font> and <xref:System.Drawing.Brush>.</span></span>  
  
     [!code-csharp[System.Drawing.AlignDrawnText#50](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#50)]
     [!code-vb[System.Drawing.AlignDrawnText#50](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#50)]  
  
### <a name="to-draw-wrapped-text-in-a-rectangle-with-gdi"></a><span data-ttu-id="2ec85-111">Per disegnare il wrapping di testo in un rettangolo con GDI</span><span class="sxs-lookup"><span data-stu-id="2ec85-111">To draw wrapped text in a rectangle with GDI</span></span>  
  
1.  <span data-ttu-id="2ec85-112">Usare la <xref:System.Windows.Forms.TextFormatFlags> valore di enumerazione per specificare il testo deve essere racchiuso tra parentesi il <xref:System.Windows.Forms.TextRenderer.DrawText%2A> sottoposto a overload, passando il testo desiderato, <xref:System.Drawing.Rectangle>, <xref:System.Drawing.Font> e <xref:System.Drawing.Color>.</span><span class="sxs-lookup"><span data-stu-id="2ec85-112">Use the <xref:System.Windows.Forms.TextFormatFlags> enumeration value to specify the text should be wrapped with the <xref:System.Windows.Forms.TextRenderer.DrawText%2A> overloaded method, passing the text you want, <xref:System.Drawing.Rectangle>, <xref:System.Drawing.Font> and <xref:System.Drawing.Color>.</span></span>  
  
     [!code-csharp[System.Drawing.AlignDrawnText#60](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#60)]
     [!code-vb[System.Drawing.AlignDrawnText#60](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#60)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="2ec85-113">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="2ec85-113">Compiling the Code</span></span>  
 <span data-ttu-id="2ec85-114">Gli esempi precedenti è necessario:</span><span class="sxs-lookup"><span data-stu-id="2ec85-114">The previous examples require:</span></span>  
  
-   <span data-ttu-id="2ec85-115"><xref:System.Windows.Forms.PaintEventArgs> `e`, ovvero un parametro di <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="2ec85-115"><xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ec85-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2ec85-116">See also</span></span>
- [<span data-ttu-id="2ec85-117">Procedura: Creare testo con GDI</span><span class="sxs-lookup"><span data-stu-id="2ec85-117">How to: Draw Text with GDI</span></span>](how-to-draw-text-with-gdi.md)
- [<span data-ttu-id="2ec85-118">Uso di tipi di carattere e testo</span><span class="sxs-lookup"><span data-stu-id="2ec85-118">Using Fonts and Text</span></span>](using-fonts-and-text.md)
- [<span data-ttu-id="2ec85-119">Procedura: Costruire i tipi di carattere e famiglie di caratteri</span><span class="sxs-lookup"><span data-stu-id="2ec85-119">How to: Construct Font Families and Fonts</span></span>](how-to-construct-font-families-and-fonts.md)
- [<span data-ttu-id="2ec85-120">Procedura: Disegnare testo in una posizione specificata</span><span class="sxs-lookup"><span data-stu-id="2ec85-120">How to: Draw Text at a Specified Location</span></span>](how-to-draw-text-at-a-specified-location.md)
