---
title: 'Procedura: Disegnare testo con GDI'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- GDI [Windows Forms], drawing text [Windows Forms]
- text [Windows Forms], drawing with TextRenderer
- drawing [Windows Forms], text
- Windows Forms, drawing text with GDI
ms.assetid: 2a19fe5d-2ace-451c-94db-01cb1118ef7b
ms.openlocfilehash: d4bf72998c798040451b814a7f0287bca65f5300
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61781485"
---
# <a name="how-to-draw-text-with-gdi"></a><span data-ttu-id="51e8c-102">Procedura: Disegnare testo con GDI</span><span class="sxs-lookup"><span data-stu-id="51e8c-102">How to: Draw Text with GDI</span></span>
<span data-ttu-id="51e8c-103">Con il <xref:System.Windows.Forms.TextRenderer.DrawText%2A> metodo nella <xref:System.Windows.Forms.TextRenderer> (classe), è possibile accedere [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] funzionalità per il disegno di testo in un form o controllo.</span><span class="sxs-lookup"><span data-stu-id="51e8c-103">With the <xref:System.Windows.Forms.TextRenderer.DrawText%2A> method in the <xref:System.Windows.Forms.TextRenderer> class, you can access [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] functionality for drawing text on a form or control.</span></span> [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] <span data-ttu-id="51e8c-104">il rendering del testo offre in genere prestazioni migliori e misurazione del testo più accurata [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].</span><span class="sxs-lookup"><span data-stu-id="51e8c-104">text rendering typically offers better performance and more accurate text measuring than [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="51e8c-105">Il <xref:System.Windows.Forms.TextRenderer.DrawText%2A> metodi del <xref:System.Windows.Forms.TextRenderer> classe non sono supportati per la stampa.</span><span class="sxs-lookup"><span data-stu-id="51e8c-105">The <xref:System.Windows.Forms.TextRenderer.DrawText%2A> methods of the <xref:System.Windows.Forms.TextRenderer> class are not supported for printing.</span></span> <span data-ttu-id="51e8c-106">Quando si stampa, utilizzare sempre il <xref:System.Drawing.Graphics.DrawString%2A> metodi del <xref:System.Drawing.Graphics> classe.</span><span class="sxs-lookup"><span data-stu-id="51e8c-106">When printing, always use the <xref:System.Drawing.Graphics.DrawString%2A> methods of the <xref:System.Drawing.Graphics> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="51e8c-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="51e8c-107">Example</span></span>  
 <span data-ttu-id="51e8c-108">Esempio di codice seguente viene illustrato come creare testo su più righe all'interno di un rettangolo utilizzando il <xref:System.Windows.Forms.TextRenderer.DrawText%2A> (metodo).</span><span class="sxs-lookup"><span data-stu-id="51e8c-108">The following code example demonstrates how to draw text on multiple lines within a rectangle using the <xref:System.Windows.Forms.TextRenderer.DrawText%2A> method.</span></span>  
  
 [!code-csharp[System.Windows.Forms.TextRendererExamples#7](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.TextRendererExamples/CS/Form1.cs#7)]
 [!code-vb[System.Windows.Forms.TextRendererExamples#7](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.TextRendererExamples/VB/Form1.vb#7)]  
  
 <span data-ttu-id="51e8c-109">Per il rendering del testo con il <xref:System.Windows.Forms.TextRenderer> (classe), è necessario un <xref:System.Drawing.IDeviceContext>, ad esempio un <xref:System.Drawing.Graphics> e un <xref:System.Drawing.Font>, un percorso in cui disegnare il testo e il colore in cui deve essere disegnato.</span><span class="sxs-lookup"><span data-stu-id="51e8c-109">To render text with the <xref:System.Windows.Forms.TextRenderer> class, you need an <xref:System.Drawing.IDeviceContext>, such as a <xref:System.Drawing.Graphics> and a <xref:System.Drawing.Font>, a location to draw the text, and the color in which it should be drawn.</span></span> <span data-ttu-id="51e8c-110">Facoltativamente, è possibile specificare il formattazione del testo utilizzando il <xref:System.Windows.Forms.TextFormatFlags> enumerazione.</span><span class="sxs-lookup"><span data-stu-id="51e8c-110">Optionally, you can specify the text formatting by using the <xref:System.Windows.Forms.TextFormatFlags> enumeration.</span></span>  
  
 <span data-ttu-id="51e8c-111">Per altre informazioni su come ottenere un <xref:System.Drawing.Graphics>, vedere [come: Creare oggetti Graphics per disegnare](how-to-create-graphics-objects-for-drawing.md).</span><span class="sxs-lookup"><span data-stu-id="51e8c-111">For more information about obtaining a <xref:System.Drawing.Graphics>, see [How to: Create Graphics Objects for Drawing](how-to-create-graphics-objects-for-drawing.md).</span></span> <span data-ttu-id="51e8c-112">Per altre informazioni sulla creazione di un <xref:System.Drawing.Font>, vedere [come: Creare le famiglie di caratteri e caratteri](how-to-construct-font-families-and-fonts.md).</span><span class="sxs-lookup"><span data-stu-id="51e8c-112">For more information about constructing a <xref:System.Drawing.Font>, see [How to: Construct Font Families and Fonts](how-to-construct-font-families-and-fonts.md).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="51e8c-113">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="51e8c-113">Compiling the Code</span></span>  
 <span data-ttu-id="51e8c-114">Esempio di codice precedente è progettato per l'uso con Windows Form e richiede la <xref:System.Windows.Forms.PaintEventArgs> `e`, ovvero un parametro di <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="51e8c-114">The preceding code example is designed for use with Windows Forms, and it requires the <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51e8c-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="51e8c-115">See also</span></span>

- <xref:System.Windows.Forms.TextRenderer>
- <xref:System.Drawing.Font>
- <xref:System.Drawing.Color>
- [<span data-ttu-id="51e8c-116">Uso di tipi di carattere e testo</span><span class="sxs-lookup"><span data-stu-id="51e8c-116">Using Fonts and Text</span></span>](using-fonts-and-text.md)
