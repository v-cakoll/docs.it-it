---
title: 'Procedura: disegnare una linea con riempimento a trama'
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
- drawing [Windows Forms], lines
- lines [Windows Forms], texture
- drawing lines [Windows Forms], texture
ms.assetid: dc9118cc-f3c2-42e5-8173-f46d41d18fd5
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0aaba7981dc68bf7bdfe6dbd45685e61f7b763a5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-draw-a-line-filled-with-a-texture"></a><span data-ttu-id="b1a9f-102">Procedura: disegnare una linea con riempimento a trama</span><span class="sxs-lookup"><span data-stu-id="b1a9f-102">How to: Draw a Line Filled with a Texture</span></span>
<span data-ttu-id="b1a9f-103">Anziché disegnare una riga con un colore a tinta unita, è possibile disegnare una riga con una trama.</span><span class="sxs-lookup"><span data-stu-id="b1a9f-103">Instead of drawing a line with a solid color, you can draw a line with a texture.</span></span> <span data-ttu-id="b1a9f-104">Per disegnare linee e curve con una trama, creare un <xref:System.Drawing.TextureBrush> dell'oggetto e passare tale <xref:System.Drawing.TextureBrush> l'oggetto in un <xref:System.Drawing.Pen.%23ctor%2A> costruttore.</span><span class="sxs-lookup"><span data-stu-id="b1a9f-104">To draw lines and curves with a texture, create a <xref:System.Drawing.TextureBrush> object, and pass that <xref:System.Drawing.TextureBrush> object to a <xref:System.Drawing.Pen.%23ctor%2A> constructor.</span></span> <span data-ttu-id="b1a9f-105">La bitmap associata al pennello trama viene utilizzata per affiancare il piano (in modo invisibile) e quando la penna Disegna una linea o una curva, il tratto di penna vengono evidenziati alcuni pixel della trama affiancata.</span><span class="sxs-lookup"><span data-stu-id="b1a9f-105">The bitmap associated with the texture brush is used to tile the plane (invisibly), and when the pen draws a line or curve, the stroke of the pen uncovers certain pixels of the tiled texture.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b1a9f-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="b1a9f-106">Example</span></span>  
 <span data-ttu-id="b1a9f-107">Nell'esempio seguente viene creato un <xref:System.Drawing.Bitmap> oggetto dal file `Texture1.jpg`.</span><span class="sxs-lookup"><span data-stu-id="b1a9f-107">The following example creates a <xref:System.Drawing.Bitmap> object from the file `Texture1.jpg`.</span></span> <span data-ttu-id="b1a9f-108">La bitmap viene utilizzato per costruire un <xref:System.Drawing.TextureBrush> oggetto e <xref:System.Drawing.TextureBrush> oggetto viene utilizzato per costruire un <xref:System.Drawing.Pen> oggetto.</span><span class="sxs-lookup"><span data-stu-id="b1a9f-108">That bitmap is used to construct a <xref:System.Drawing.TextureBrush> object, and the <xref:System.Drawing.TextureBrush> object is used to construct a <xref:System.Drawing.Pen> object.</span></span> <span data-ttu-id="b1a9f-109">La chiamata a <xref:System.Drawing.Graphics.DrawImage%2A> Disegna la bitmap con il relativo angolo superiore sinistro a (0, 0).</span><span class="sxs-lookup"><span data-stu-id="b1a9f-109">The call to <xref:System.Drawing.Graphics.DrawImage%2A> draws the bitmap with its upper-left corner at (0, 0).</span></span> <span data-ttu-id="b1a9f-110">La chiamata a <xref:System.Drawing.Graphics.DrawEllipse%2A> utilizza il <xref:System.Drawing.Pen> oggetto su cui disegnare un'ellisse a trama.</span><span class="sxs-lookup"><span data-stu-id="b1a9f-110">The call to <xref:System.Drawing.Graphics.DrawEllipse%2A> uses the <xref:System.Drawing.Pen> object to draw a textured ellipse.</span></span>  
  
 <span data-ttu-id="b1a9f-111">Nella figura seguente mostra la bitmap e la trama ellisse.</span><span class="sxs-lookup"><span data-stu-id="b1a9f-111">The following illustration shows the bitmap and the textured ellipse.</span></span>  
  
 <span data-ttu-id="b1a9f-112">![Penne](../../../../docs/framework/winforms/advanced/media/pens7.png "pens7")</span><span class="sxs-lookup"><span data-stu-id="b1a9f-112">![Pens](../../../../docs/framework/winforms/advanced/media/pens7.png "pens7")</span></span>  
  
 [!code-csharp[System.Drawing.UsingAPen#61](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#61)]
 [!code-vb[System.Drawing.UsingAPen#61](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#61)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="b1a9f-113">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="b1a9f-113">Compiling the Code</span></span>  
 <span data-ttu-id="b1a9f-114">Creare un Windows Form e gestire il modulo <xref:System.Windows.Forms.Control.Paint> evento.</span><span class="sxs-lookup"><span data-stu-id="b1a9f-114">Create a Windows Form and handle the form's <xref:System.Windows.Forms.Control.Paint> event.</span></span> <span data-ttu-id="b1a9f-115">Incollare il codice precedente nel <xref:System.Windows.Forms.Control.Paint> gestore dell'evento.</span><span class="sxs-lookup"><span data-stu-id="b1a9f-115">Paste the preceding code into the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="b1a9f-116">Sostituire `Texture.jpg` con un'immagine disponibile nel sistema.</span><span class="sxs-lookup"><span data-stu-id="b1a9f-116">Replace `Texture.jpg` with an image valid on your system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1a9f-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b1a9f-117">See Also</span></span>  
 [<span data-ttu-id="b1a9f-118">Uso di un oggetto Pen per creare linee e forme</span><span class="sxs-lookup"><span data-stu-id="b1a9f-118">Using a Pen to Draw Lines and Shapes</span></span>](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)  
 [<span data-ttu-id="b1a9f-119">Grafica e disegno in Windows Form</span><span class="sxs-lookup"><span data-stu-id="b1a9f-119">Graphics and Drawing in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)
