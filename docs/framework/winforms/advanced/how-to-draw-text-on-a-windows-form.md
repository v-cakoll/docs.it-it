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
ms.openlocfilehash: ae7749deedba03f0a63bb74099d071d5da4fe27e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59172978"
---
# <a name="how-to-draw-text-on-a-windows-form"></a><span data-ttu-id="9d1d0-102">Procedura: Disegnare testo in un Windows Form</span><span class="sxs-lookup"><span data-stu-id="9d1d0-102">How to: Draw Text on a Windows Form</span></span>
<span data-ttu-id="9d1d0-103">Esempio di codice seguente viene illustrato come utilizzare il <xref:System.Drawing.Graphics.DrawString%2A> metodo del <xref:System.Drawing.Graphics> disegnare testo in un form.</span><span class="sxs-lookup"><span data-stu-id="9d1d0-103">The following code example shows how to use the <xref:System.Drawing.Graphics.DrawString%2A> method of the <xref:System.Drawing.Graphics> to draw text on a form.</span></span> <span data-ttu-id="9d1d0-104">In alternativa, è possibile usare <xref:System.Windows.Forms.TextRenderer> per disegnare il testo in un form.</span><span class="sxs-lookup"><span data-stu-id="9d1d0-104">Alternatively, you can use <xref:System.Windows.Forms.TextRenderer> for drawing text on a form.</span></span> <span data-ttu-id="9d1d0-105">Per altre informazioni, vedere [Procedura: Creare testo con GDI](how-to-draw-text-with-gdi.md).</span><span class="sxs-lookup"><span data-stu-id="9d1d0-105">For more information, see [How to: Draw Text with GDI](how-to-draw-text-with-gdi.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9d1d0-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="9d1d0-106">Example</span></span>  
 [!code-cpp[System.Drawing.ConceptualHowTos#7](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#7)]
 [!code-csharp[System.Drawing.ConceptualHowTos#7](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#7)]
 [!code-vb[System.Drawing.ConceptualHowTos#7](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#7)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="9d1d0-107">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="9d1d0-107">Compiling the Code</span></span>  
 <span data-ttu-id="9d1d0-108">Non è possibile chiamare il <xref:System.Drawing.Graphics.DrawString%2A> nel metodo il <xref:System.Windows.Forms.Form.Load> gestore dell'evento.</span><span class="sxs-lookup"><span data-stu-id="9d1d0-108">You cannot call the <xref:System.Drawing.Graphics.DrawString%2A> method in the <xref:System.Windows.Forms.Form.Load> event handler.</span></span> <span data-ttu-id="9d1d0-109">Il contenuto creato non verrà ridisegnato se il form viene ridimensionato o nascosto da un altro form.</span><span class="sxs-lookup"><span data-stu-id="9d1d0-109">The drawn content will not be redrawn if the form is resized or obscured by another form.</span></span> <span data-ttu-id="9d1d0-110">Per rendere il contenuto viene ridisegnata automaticamente, è necessario eseguire l'override di <xref:System.Windows.Forms.Control.OnPaint%2A> (metodo).</span><span class="sxs-lookup"><span data-stu-id="9d1d0-110">To make your content automatically repaint, you should override the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="9d1d0-111">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="9d1d0-111">Robust Programming</span></span>  
 <span data-ttu-id="9d1d0-112">Le seguenti condizioni possono generare un'eccezione:</span><span class="sxs-lookup"><span data-stu-id="9d1d0-112">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="9d1d0-113">Non è installato il tipo di carattere Arial.</span><span class="sxs-lookup"><span data-stu-id="9d1d0-113">The Arial font is not installed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d1d0-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9d1d0-114">See also</span></span>

- <xref:System.Drawing.Graphics.DrawString%2A>
- <xref:System.Windows.Forms.TextRenderer.DrawText%2A>
- <xref:System.Drawing.StringFormat.FormatFlags%2A>
- <xref:System.Drawing.StringFormatFlags>
- <xref:System.Windows.Forms.TextFormatFlags>
- <xref:System.Windows.Forms.Control.OnPaint%2A>
- [<span data-ttu-id="9d1d0-115">Introduzione alla programmazione grafica</span><span class="sxs-lookup"><span data-stu-id="9d1d0-115">Getting Started with Graphics Programming</span></span>](getting-started-with-graphics-programming.md)
- [<span data-ttu-id="9d1d0-116">Procedura: Creare testo con GDI</span><span class="sxs-lookup"><span data-stu-id="9d1d0-116">How to: Draw Text with GDI</span></span>](how-to-draw-text-with-gdi.md)
