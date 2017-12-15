---
title: 'Procedura: creare testo in una posizione specificata'
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
- text [Windows Forms], drawing at specified locations [Windows Forms]
- drawing text
- drawing text [Windows Forms], specified locations [Windows Forms]
- Windows Forms, drawing text at a specified location
ms.assetid: 60816423-1c38-465e-980d-2c2b64d74086
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: fe6e8563b19ef18b89ad970f3ca35bf5f0782a32
ms.sourcegitcommit: 8ed4ebc15b5ef89d06a7507dc9d5e306e30accf7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/14/2017
---
# <a name="how-to-draw-text-at-a-specified-location"></a><span data-ttu-id="efa1e-102">Procedura: creare testo in una posizione specificata</span><span class="sxs-lookup"><span data-stu-id="efa1e-102">How to: Draw Text at a Specified Location</span></span>
<span data-ttu-id="efa1e-103">Quando si esegue il disegno personalizzato, è possibile disegnare testo in una singola riga orizzontale, a partire da un punto specificato.</span><span class="sxs-lookup"><span data-stu-id="efa1e-103">When you perform custom drawing, you can draw text in a single horizontal line starting at a specified point.</span></span> <span data-ttu-id="efa1e-104">In questo modo è possibile creare testo utilizzando il <xref:System.Drawing.Graphics.DrawString%2A> metodo di overload di <xref:System.Drawing.Graphics> classe che accetta un <xref:System.Drawing.Point> o <xref:System.Drawing.PointF> parametro.</span><span class="sxs-lookup"><span data-stu-id="efa1e-104">You can draw text in this manner by using the <xref:System.Drawing.Graphics.DrawString%2A> overloaded method of the <xref:System.Drawing.Graphics> class that takes a <xref:System.Drawing.Point> or <xref:System.Drawing.PointF> parameter.</span></span> <span data-ttu-id="efa1e-105">Il <xref:System.Drawing.Graphics.DrawString%2A> metodo richiede inoltre un <xref:System.Drawing.Brush> e<xref:System.Drawing.Font></span><span class="sxs-lookup"><span data-stu-id="efa1e-105">The <xref:System.Drawing.Graphics.DrawString%2A> method also requires a <xref:System.Drawing.Brush> and <xref:System.Drawing.Font></span></span>  
  
 <span data-ttu-id="efa1e-106">È inoltre possibile utilizzare il <xref:System.Windows.Forms.TextRenderer.DrawText%2A> metodo di overload di <xref:System.Windows.Forms.TextRenderer> che accetta un <xref:System.Drawing.Point>.</span><span class="sxs-lookup"><span data-stu-id="efa1e-106">You can also use the <xref:System.Windows.Forms.TextRenderer.DrawText%2A> overloaded method of the <xref:System.Windows.Forms.TextRenderer> that takes a <xref:System.Drawing.Point>.</span></span> <span data-ttu-id="efa1e-107"><xref:System.Windows.Forms.TextRenderer.DrawText%2A>richiede inoltre un <xref:System.Drawing.Color> e <xref:System.Drawing.Font>.</span><span class="sxs-lookup"><span data-stu-id="efa1e-107"><xref:System.Windows.Forms.TextRenderer.DrawText%2A> also requires a <xref:System.Drawing.Color> and a <xref:System.Drawing.Font>.</span></span>  
  
 <span data-ttu-id="efa1e-108">Nella figura seguente mostra l'output di testo creato in un punto specificato quando si utilizza il <xref:System.Drawing.Graphics.DrawString%2A> il metodo di overload.</span><span class="sxs-lookup"><span data-stu-id="efa1e-108">The following illustration shows the output of text drawn at a specified point when you use the <xref:System.Drawing.Graphics.DrawString%2A> overloaded method.</span></span>  
  
 <span data-ttu-id="efa1e-109">![Tipi di carattere testo](../../../../docs/framework/winforms/advanced/media/csfontstext1.png "csfontstext1")</span><span class="sxs-lookup"><span data-stu-id="efa1e-109">![Fonts Text](../../../../docs/framework/winforms/advanced/media/csfontstext1.png "csfontstext1")</span></span>  
  
### <a name="to-draw-a-line-of-text-with-gdi"></a><span data-ttu-id="efa1e-110">Per disegnare una riga di testo con GDI+</span><span class="sxs-lookup"><span data-stu-id="efa1e-110">To draw a line of text with GDI+</span></span>  
  
1.  <span data-ttu-id="efa1e-111">Utilizzare il <xref:System.Drawing.Graphics.DrawString%2A> , passando il testo desiderato, <xref:System.Drawing.Point> o <xref:System.Drawing.PointF>, <xref:System.Drawing.Font>, e <xref:System.Drawing.Brush>.</span><span class="sxs-lookup"><span data-stu-id="efa1e-111">Use the <xref:System.Drawing.Graphics.DrawString%2A> method, passing the text you want, <xref:System.Drawing.Point> or <xref:System.Drawing.PointF>, <xref:System.Drawing.Font>, and <xref:System.Drawing.Brush>.</span></span>  
  
     [!code-csharp[System.Drawing.AlignDrawnText#30](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#30)]
     [!code-vb[System.Drawing.AlignDrawnText#30](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#30)]  
  
### <a name="to-draw-a-line-of-text-with-gdi"></a><span data-ttu-id="efa1e-112">Per disegnare una riga di testo con GDI</span><span class="sxs-lookup"><span data-stu-id="efa1e-112">To draw a line of text with GDI</span></span>  
  
1.  <span data-ttu-id="efa1e-113">Utilizzare il <xref:System.Windows.Forms.TextRenderer.DrawText%2A> , passando il testo desiderato, <xref:System.Drawing.Point>, <xref:System.Drawing.Font>, e <xref:System.Drawing.Color>.</span><span class="sxs-lookup"><span data-stu-id="efa1e-113">Use the <xref:System.Windows.Forms.TextRenderer.DrawText%2A> method, passing the text you want, <xref:System.Drawing.Point>, <xref:System.Drawing.Font>, and <xref:System.Drawing.Color>.</span></span>  
  
     [!code-csharp[System.Drawing.AlignDrawnText#40](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#40)]
     [!code-vb[System.Drawing.AlignDrawnText#40](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#40)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="efa1e-114">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="efa1e-114">Compiling the Code</span></span>  
 <span data-ttu-id="efa1e-115">Gli esempi precedenti richiedono:</span><span class="sxs-lookup"><span data-stu-id="efa1e-115">The previous examples require:</span></span>  
  
-   <span data-ttu-id="efa1e-116"><xref:System.Windows.Forms.PaintEventArgs>  `e`, che è un parametro di <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="efa1e-116"><xref:System.Windows.Forms.PaintEventArgs>  `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efa1e-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="efa1e-117">See Also</span></span>  
 [<span data-ttu-id="efa1e-118">Procedura: Creare testo con GDI</span><span class="sxs-lookup"><span data-stu-id="efa1e-118">How to: Draw Text with GDI</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md)  
 [<span data-ttu-id="efa1e-119">Uso di tipi di carattere e testo</span><span class="sxs-lookup"><span data-stu-id="efa1e-119">Using Fonts and Text</span></span>](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)  
 [<span data-ttu-id="efa1e-120">Procedura: Creare caratteri e gruppi di caratteri</span><span class="sxs-lookup"><span data-stu-id="efa1e-120">How to: Construct Font Families and Fonts</span></span>](../../../../docs/framework/winforms/advanced/how-to-construct-font-families-and-fonts.md)  
 [<span data-ttu-id="efa1e-121">Procedura: Creare testo disposto su più righe in un rettangolo</span><span class="sxs-lookup"><span data-stu-id="efa1e-121">How to: Draw Wrapped Text in a Rectangle</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-wrapped-text-in-a-rectangle.md)
