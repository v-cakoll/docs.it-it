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
ms.openlocfilehash: 3ed2b5c94e4a38a5873a34e61287c4038cab5cbb
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69956535"
---
# <a name="how-to-draw-text-with-gdi"></a><span data-ttu-id="94e57-102">Procedura: Disegnare testo con GDI</span><span class="sxs-lookup"><span data-stu-id="94e57-102">How to: Draw Text with GDI</span></span>
<span data-ttu-id="94e57-103">Con il <xref:System.Windows.Forms.TextRenderer.DrawText%2A> metodo <xref:System.Windows.Forms.TextRenderer> nella classe, è possibile accedere alla funzionalità GDI per il disegno di testo in un form o un controllo.</span><span class="sxs-lookup"><span data-stu-id="94e57-103">With the <xref:System.Windows.Forms.TextRenderer.DrawText%2A> method in the <xref:System.Windows.Forms.TextRenderer> class, you can access GDI functionality for drawing text on a form or control.</span></span> <span data-ttu-id="94e57-104">Il rendering del testo GDI offre in genere prestazioni migliori e una misurazione più accurata del testo rispetto a GDI+.</span><span class="sxs-lookup"><span data-stu-id="94e57-104">GDI text rendering typically offers better performance and more accurate text measuring than GDI+.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="94e57-105">I <xref:System.Windows.Forms.TextRenderer.DrawText%2A> metodi<xref:System.Windows.Forms.TextRenderer> della classe non sono supportati per la stampa.</span><span class="sxs-lookup"><span data-stu-id="94e57-105">The <xref:System.Windows.Forms.TextRenderer.DrawText%2A> methods of the <xref:System.Windows.Forms.TextRenderer> class are not supported for printing.</span></span> <span data-ttu-id="94e57-106">Quando si esegue la stampa, <xref:System.Drawing.Graphics.DrawString%2A> utilizzare sempre i <xref:System.Drawing.Graphics> metodi della classe.</span><span class="sxs-lookup"><span data-stu-id="94e57-106">When printing, always use the <xref:System.Drawing.Graphics.DrawString%2A> methods of the <xref:System.Drawing.Graphics> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="94e57-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="94e57-107">Example</span></span>  
 <span data-ttu-id="94e57-108">Nell'esempio di codice riportato di seguito viene illustrato come creare testo su più righe all'interno <xref:System.Windows.Forms.TextRenderer.DrawText%2A> di un rettangolo utilizzando il metodo.</span><span class="sxs-lookup"><span data-stu-id="94e57-108">The following code example demonstrates how to draw text on multiple lines within a rectangle using the <xref:System.Windows.Forms.TextRenderer.DrawText%2A> method.</span></span>  
  
 [!code-csharp[System.Windows.Forms.TextRendererExamples#7](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.TextRendererExamples/CS/Form1.cs#7)]
 [!code-vb[System.Windows.Forms.TextRendererExamples#7](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.TextRendererExamples/VB/Form1.vb#7)]  
  
 <span data-ttu-id="94e57-109">Per eseguire il rendering del <xref:System.Windows.Forms.TextRenderer> testo con la classe, <xref:System.Drawing.IDeviceContext>è necessario un oggetto <xref:System.Drawing.Graphics> , ad <xref:System.Drawing.Font>esempio un oggetto e un oggetto, un percorso per disegnare il testo e il colore in cui deve essere disegnato.</span><span class="sxs-lookup"><span data-stu-id="94e57-109">To render text with the <xref:System.Windows.Forms.TextRenderer> class, you need an <xref:System.Drawing.IDeviceContext>, such as a <xref:System.Drawing.Graphics> and a <xref:System.Drawing.Font>, a location to draw the text, and the color in which it should be drawn.</span></span> <span data-ttu-id="94e57-110">Facoltativamente, è possibile specificare la formattazione del testo utilizzando l' <xref:System.Windows.Forms.TextFormatFlags> enumerazione.</span><span class="sxs-lookup"><span data-stu-id="94e57-110">Optionally, you can specify the text formatting by using the <xref:System.Windows.Forms.TextFormatFlags> enumeration.</span></span>  
  
 <span data-ttu-id="94e57-111">Per ulteriori informazioni su come ottenere <xref:System.Drawing.Graphics>un, [vedere Procedura: Creare oggetti grafici per il](how-to-create-graphics-objects-for-drawing.md)disegno.</span><span class="sxs-lookup"><span data-stu-id="94e57-111">For more information about obtaining a <xref:System.Drawing.Graphics>, see [How to: Create Graphics Objects for Drawing](how-to-create-graphics-objects-for-drawing.md).</span></span> <span data-ttu-id="94e57-112">Per ulteriori informazioni sulla costruzione di un <xref:System.Drawing.Font>, vedere [procedura: Costruire famiglie di caratteri e](how-to-construct-font-families-and-fonts.md)tipi di carattere.</span><span class="sxs-lookup"><span data-stu-id="94e57-112">For more information about constructing a <xref:System.Drawing.Font>, see [How to: Construct Font Families and Fonts](how-to-construct-font-families-and-fonts.md).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="94e57-113">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="94e57-113">Compiling the Code</span></span>  
 <span data-ttu-id="94e57-114">L'esempio di codice precedente è progettato per l'uso con Windows Forms e richiede <xref:System.Windows.Forms.PaintEventArgs> `e`, che è un parametro di <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="94e57-114">The preceding code example is designed for use with Windows Forms, and it requires the <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94e57-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="94e57-115">See also</span></span>

- <xref:System.Windows.Forms.TextRenderer>
- <xref:System.Drawing.Font>
- <xref:System.Drawing.Color>
- [<span data-ttu-id="94e57-116">Uso di tipi di carattere e testo</span><span class="sxs-lookup"><span data-stu-id="94e57-116">Using Fonts and Text</span></span>](using-fonts-and-text.md)
