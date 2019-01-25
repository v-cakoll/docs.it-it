---
title: 'Procedura: Disegnare una linea con estremità'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- drawing [Windows Forms], lines
- lines [Windows Forms], drawing
- pens [Windows Forms], drawing lines
- drawing lines [Windows Forms], line caps
ms.assetid: eb68c3e1-c400-4886-8a04-76978a429cb6
ms.openlocfilehash: a0d4d92d7201c4ac09eadd11d8f2e38a3c80c287
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54713136"
---
# <a name="how-to-draw-a-line-with-line-caps"></a><span data-ttu-id="38339-102">Procedura: Disegnare una linea con estremità</span><span class="sxs-lookup"><span data-stu-id="38339-102">How to: Draw a Line with Line Caps</span></span>
<span data-ttu-id="38339-103">È possibile disegnare inizio o alla fine di una riga in una delle diverse forme chiamate estremità.</span><span class="sxs-lookup"><span data-stu-id="38339-103">You can draw the start or end of a line in one of several shapes called line caps.</span></span> [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="38339-104">supporta diversi limiti di riga, come round, quadrato, a forma di rombo e punta della freccia.</span><span class="sxs-lookup"><span data-stu-id="38339-104">supports several line caps, such as round, square, diamond, and arrowhead.</span></span>  
  
## <a name="example"></a><span data-ttu-id="38339-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="38339-105">Example</span></span>  
 <span data-ttu-id="38339-106">È possibile specificare limiti massimi di riga per l'inizio di una riga (estremità di apertura), la fine di una riga (estremità) o i trattini di una linea tratteggiata (cap dash).</span><span class="sxs-lookup"><span data-stu-id="38339-106">You can specify line caps for the start of a line (start cap), the end of a line (end cap), or the dashes of a dashed line (dash cap).</span></span>  
  
 <span data-ttu-id="38339-107">Nell'esempio seguente disegna una linea con una freccia a un'estremità e un'estremità a altra estremità arrotondata.</span><span class="sxs-lookup"><span data-stu-id="38339-107">The following example draws a line with an arrowhead at one end and a round cap at the other end.</span></span> <span data-ttu-id="38339-108">La figura mostra la riga risulta:</span><span class="sxs-lookup"><span data-stu-id="38339-108">The illustration shows the resulting line:</span></span>  
  
 <span data-ttu-id="38339-109">![Penne](../../../../docs/framework/winforms/advanced/media/pens4.gif "pens4")</span><span class="sxs-lookup"><span data-stu-id="38339-109">![Pens](../../../../docs/framework/winforms/advanced/media/pens4.gif "pens4")</span></span>  
  
 [!code-csharp[System.Drawing.UsingAPen#71](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#71)]
 [!code-vb[System.Drawing.UsingAPen#71](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#71)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="38339-110">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="38339-110">Compiling the Code</span></span>  
  
-   <span data-ttu-id="38339-111">Creare un modulo di Windows e la gestione del modulo <xref:System.Windows.Forms.Control.Paint> evento.</span><span class="sxs-lookup"><span data-stu-id="38339-111">Create a Windows Form and handle the form's <xref:System.Windows.Forms.Control.Paint> event.</span></span> <span data-ttu-id="38339-112">Incollare il codice di esempio nel <xref:System.Windows.Forms.Control.Paint> gestore dell'evento passando `e` come <xref:System.Windows.Forms.PaintEventArgs>.</span><span class="sxs-lookup"><span data-stu-id="38339-112">Paste the example code into the <xref:System.Windows.Forms.Control.Paint> event handler passing `e` as <xref:System.Windows.Forms.PaintEventArgs>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38339-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="38339-113">See also</span></span>
- <xref:System.Drawing.Pen?displayProperty=nameWithType>
- <xref:System.Drawing.Drawing2D.LineCap?displayProperty=nameWithType>
- [<span data-ttu-id="38339-114">Grafica e disegno in Windows Form</span><span class="sxs-lookup"><span data-stu-id="38339-114">Graphics and Drawing in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="38339-115">Uso di un oggetto Pen per creare linee e forme</span><span class="sxs-lookup"><span data-stu-id="38339-115">Using a Pen to Draw Lines and Shapes</span></span>](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)
