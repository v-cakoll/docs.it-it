---
title: 'Procedura: Disegnare testo in un Windows Form'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- forms [Windows Forms], drawing text
- text [Windows Forms], drawing
ms.assetid: 5d2447a9-21a1-4adc-b954-5516f2bb9b2c
ms.openlocfilehash: ed7aa89c3bd3751ed93f5bda33a26a8309d39143
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57703504"
---
# <a name="how-to-draw-text-on-a-windows-form"></a><span data-ttu-id="41f7a-102">Procedura: Disegnare testo in un Windows Form</span><span class="sxs-lookup"><span data-stu-id="41f7a-102">How to: Draw Text on a Windows Form</span></span>
<span data-ttu-id="41f7a-103">Esempio di codice seguente viene illustrato come utilizzare il <xref:System.Drawing.Graphics.DrawString%2A> metodo del <xref:System.Drawing.Graphics> disegnare testo in un form.</span><span class="sxs-lookup"><span data-stu-id="41f7a-103">The following code example shows how to use the <xref:System.Drawing.Graphics.DrawString%2A> method of the <xref:System.Drawing.Graphics> to draw text on a form.</span></span> <span data-ttu-id="41f7a-104">In alternativa, è possibile usare <xref:System.Windows.Forms.TextRenderer> per disegnare il testo in un form.</span><span class="sxs-lookup"><span data-stu-id="41f7a-104">Alternatively, you can use <xref:System.Windows.Forms.TextRenderer> for drawing text on a form.</span></span> <span data-ttu-id="41f7a-105">Per altre informazioni, vedere [Procedura: Creare testo con GDI](how-to-draw-text-with-gdi.md).</span><span class="sxs-lookup"><span data-stu-id="41f7a-105">For more information, see [How to: Draw Text with GDI](how-to-draw-text-with-gdi.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="41f7a-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="41f7a-106">Example</span></span>  
 [!code-cpp[System.Drawing.ConceptualHowTos#7](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#7)]
 [!code-csharp[System.Drawing.ConceptualHowTos#7](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#7)]
 [!code-vb[System.Drawing.ConceptualHowTos#7](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#7)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="41f7a-107">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="41f7a-107">Compiling the Code</span></span>  
 <span data-ttu-id="41f7a-108">Non è possibile chiamare il <xref:System.Drawing.Graphics.DrawString%2A> nel metodo il <xref:System.Windows.Forms.Form.Load> gestore dell'evento.</span><span class="sxs-lookup"><span data-stu-id="41f7a-108">You cannot call the <xref:System.Drawing.Graphics.DrawString%2A> method in the <xref:System.Windows.Forms.Form.Load> event handler.</span></span> <span data-ttu-id="41f7a-109">Il contenuto creato non verrà ridisegnato se il form viene ridimensionato o nascosto da un altro form.</span><span class="sxs-lookup"><span data-stu-id="41f7a-109">The drawn content will not be redrawn if the form is resized or obscured by another form.</span></span> <span data-ttu-id="41f7a-110">Per rendere il contenuto viene ridisegnata automaticamente, è necessario eseguire l'override di <xref:System.Windows.Forms.Control.OnPaint%2A> (metodo).</span><span class="sxs-lookup"><span data-stu-id="41f7a-110">To make your content automatically repaint, you should override the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="41f7a-111">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="41f7a-111">Robust Programming</span></span>  
 <span data-ttu-id="41f7a-112">Le seguenti condizioni possono generare un'eccezione:</span><span class="sxs-lookup"><span data-stu-id="41f7a-112">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="41f7a-113">Non è installato il tipo di carattere Arial.</span><span class="sxs-lookup"><span data-stu-id="41f7a-113">The Arial font is not installed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41f7a-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="41f7a-114">See also</span></span>
- <xref:System.Drawing.Graphics.DrawString%2A>
- <xref:System.Windows.Forms.TextRenderer.DrawText%2A>
- <xref:System.Drawing.StringFormat.FormatFlags%2A>
- <xref:System.Drawing.StringFormatFlags>
- <xref:System.Windows.Forms.TextFormatFlags>
- <xref:System.Windows.Forms.Control.OnPaint%2A>
- [<span data-ttu-id="41f7a-115">Introduzione alla programmazione grafica</span><span class="sxs-lookup"><span data-stu-id="41f7a-115">Getting Started with Graphics Programming</span></span>](getting-started-with-graphics-programming.md)
- [<span data-ttu-id="41f7a-116">Procedura: Creare testo con GDI</span><span class="sxs-lookup"><span data-stu-id="41f7a-116">How to: Draw Text with GDI</span></span>](how-to-draw-text-with-gdi.md)
