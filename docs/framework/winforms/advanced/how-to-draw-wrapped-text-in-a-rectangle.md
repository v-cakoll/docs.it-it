---
title: 'Procedura: creare testo disposto su più righe in un rettangolo'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, drawing text in a rectangle
- text [Windows Forms], drawing in a rectangle
- strings [Windows Forms], drawing in a rectangle
ms.assetid: e1fb432a-dc90-48b5-9b6b-acc14507133d
ms.openlocfilehash: c753be6a200f166e59e1330c7dbcf1fadc7588a6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33524973"
---
# <a name="how-to-draw-wrapped-text-in-a-rectangle"></a><span data-ttu-id="d1aee-102">Procedura: creare testo disposto su più righe in un rettangolo</span><span class="sxs-lookup"><span data-stu-id="d1aee-102">How to: Draw Wrapped Text in a Rectangle</span></span>
<span data-ttu-id="d1aee-103">È possibile disegnare il testo a capo in un rettangolo con il <xref:System.Drawing.Graphics.DrawString%2A> metodo di overload di <xref:System.Drawing.Graphics> classe che accetta un <xref:System.Drawing.Rectangle> o <xref:System.Drawing.RectangleF> parametro.</span><span class="sxs-lookup"><span data-stu-id="d1aee-103">You can draw wrapped text in a rectangle by using the <xref:System.Drawing.Graphics.DrawString%2A> overloaded method of the <xref:System.Drawing.Graphics> class that takes a <xref:System.Drawing.Rectangle> or <xref:System.Drawing.RectangleF> parameter.</span></span> <span data-ttu-id="d1aee-104">Si utilizzerà inoltre un <xref:System.Drawing.Brush> e <xref:System.Drawing.Font>.</span><span class="sxs-lookup"><span data-stu-id="d1aee-104">You will also use a <xref:System.Drawing.Brush> and a <xref:System.Drawing.Font>.</span></span>  
  
 <span data-ttu-id="d1aee-105">È possibile creare testo sottoposta a wrapping in un rettangolo con il <xref:System.Windows.Forms.TextRenderer.DrawText%2A> metodo di overload di <xref:System.Windows.Forms.TextRenderer> che accetta un <xref:System.Drawing.Rectangle> e un <xref:System.Windows.Forms.TextFormatFlags> parametro.</span><span class="sxs-lookup"><span data-stu-id="d1aee-105">You can also draw wrapped text in a rectangle by using the <xref:System.Windows.Forms.TextRenderer.DrawText%2A> overloaded method of the <xref:System.Windows.Forms.TextRenderer> that takes a <xref:System.Drawing.Rectangle> and a <xref:System.Windows.Forms.TextFormatFlags> parameter.</span></span> <span data-ttu-id="d1aee-106">Si utilizzerà inoltre un <xref:System.Drawing.Color> e <xref:System.Drawing.Font>.</span><span class="sxs-lookup"><span data-stu-id="d1aee-106">You will also use a <xref:System.Drawing.Color> and a <xref:System.Drawing.Font>.</span></span>  
  
 <span data-ttu-id="d1aee-107">Nella figura seguente viene illustrato l'output di testo nel rettangolo quando si utilizza il <xref:System.Drawing.Graphics.DrawString%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="d1aee-107">The following illustration shows the output of text drawn in the rectangle when you use the <xref:System.Drawing.Graphics.DrawString%2A> method.</span></span>  
  
 <span data-ttu-id="d1aee-108">![Testo caratteri](../../../../docs/framework/winforms/advanced/media/csfontstext2.png "csfontstext2")</span><span class="sxs-lookup"><span data-stu-id="d1aee-108">![Fonts Text](../../../../docs/framework/winforms/advanced/media/csfontstext2.png "csfontstext2")</span></span>  
  
### <a name="to-draw-wrapped-text-in-a-rectangle-with-gdi"></a><span data-ttu-id="d1aee-109">Per disegnare il wrapping di testo in un rettangolo con GDI+</span><span class="sxs-lookup"><span data-stu-id="d1aee-109">To draw wrapped text in a rectangle with GDI+</span></span>  
  
1.  <span data-ttu-id="d1aee-110">Utilizzare il <xref:System.Drawing.Graphics.DrawString%2A> metodo di overload, passare il testo desiderato, <xref:System.Drawing.Rectangle> o <xref:System.Drawing.RectangleF>, <xref:System.Drawing.Font> e <xref:System.Drawing.Brush>.</span><span class="sxs-lookup"><span data-stu-id="d1aee-110">Use the <xref:System.Drawing.Graphics.DrawString%2A> overloaded method, passing the text you want, <xref:System.Drawing.Rectangle> or <xref:System.Drawing.RectangleF>, <xref:System.Drawing.Font> and <xref:System.Drawing.Brush>.</span></span>  
  
     [!code-csharp[System.Drawing.AlignDrawnText#50](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#50)]
     [!code-vb[System.Drawing.AlignDrawnText#50](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#50)]  
  
### <a name="to-draw-wrapped-text-in-a-rectangle-with-gdi"></a><span data-ttu-id="d1aee-111">Per disegnare il wrapping di testo in un rettangolo con GDI</span><span class="sxs-lookup"><span data-stu-id="d1aee-111">To draw wrapped text in a rectangle with GDI</span></span>  
  
1.  <span data-ttu-id="d1aee-112">Utilizzare il <xref:System.Windows.Forms.TextFormatFlags> il valore di enumerazione per specificare il testo deve essere racchiuso tra i <xref:System.Windows.Forms.TextRenderer.DrawText%2A> metodo di overload, passare il testo desiderato, <xref:System.Drawing.Rectangle>, <xref:System.Drawing.Font> e <xref:System.Drawing.Color>.</span><span class="sxs-lookup"><span data-stu-id="d1aee-112">Use the <xref:System.Windows.Forms.TextFormatFlags> enumeration value to specify the text should be wrapped with the <xref:System.Windows.Forms.TextRenderer.DrawText%2A> overloaded method, passing the text you want, <xref:System.Drawing.Rectangle>, <xref:System.Drawing.Font> and <xref:System.Drawing.Color>.</span></span>  
  
     [!code-csharp[System.Drawing.AlignDrawnText#60](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#60)]
     [!code-vb[System.Drawing.AlignDrawnText#60](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#60)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d1aee-113">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="d1aee-113">Compiling the Code</span></span>  
 <span data-ttu-id="d1aee-114">Gli esempi precedenti richiedono:</span><span class="sxs-lookup"><span data-stu-id="d1aee-114">The previous examples require:</span></span>  
  
-   <span data-ttu-id="d1aee-115"><xref:System.Windows.Forms.PaintEventArgs> `e`, ovvero un parametro di <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="d1aee-115"><xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1aee-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d1aee-116">See Also</span></span>  
 [<span data-ttu-id="d1aee-117">Procedura: Creare testo con GDI</span><span class="sxs-lookup"><span data-stu-id="d1aee-117">How to: Draw Text with GDI</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md)  
 [<span data-ttu-id="d1aee-118">Uso di tipi di carattere e testo</span><span class="sxs-lookup"><span data-stu-id="d1aee-118">Using Fonts and Text</span></span>](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)  
 [<span data-ttu-id="d1aee-119">Procedura: Creare caratteri e gruppi di caratteri</span><span class="sxs-lookup"><span data-stu-id="d1aee-119">How to: Construct Font Families and Fonts</span></span>](../../../../docs/framework/winforms/advanced/how-to-construct-font-families-and-fonts.md)  
 [<span data-ttu-id="d1aee-120">Procedura: Creare testo in una posizione specificata</span><span class="sxs-lookup"><span data-stu-id="d1aee-120">How to: Draw Text at a Specified Location</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-text-at-a-specified-location.md)
