---
title: 'Procedura: utilizzare un oggetto Pen per disegnare rettangoli'
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
- rectangles [Windows Forms], drawing
- pens [Windows Forms], drawing rectangles
ms.assetid: 54a7fa14-3ad8-4d64-b424-2a12005b250c
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 032f53ffe3bccd329b3e2eea4fbf13949f35c3cd
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-use-a-pen-to-draw-rectangles"></a><span data-ttu-id="d493e-102">Procedura: utilizzare un oggetto Pen per disegnare rettangoli</span><span class="sxs-lookup"><span data-stu-id="d493e-102">How to: Use a Pen to Draw Rectangles</span></span>
<span data-ttu-id="d493e-103">Per disegnare rettangoli, è necessario un <xref:System.Drawing.Graphics> oggetto e un <xref:System.Drawing.Pen> oggetto.</span><span class="sxs-lookup"><span data-stu-id="d493e-103">To draw rectangles, you need a <xref:System.Drawing.Graphics> object and a <xref:System.Drawing.Pen> object.</span></span> <span data-ttu-id="d493e-104">Il <xref:System.Drawing.Graphics> oggetto fornisce il <xref:System.Drawing.Graphics.DrawRectangle%2A> (metodo) e <xref:System.Drawing.Pen> oggetto archivia le funzionalità della riga, ad esempio colore e spessore.</span><span class="sxs-lookup"><span data-stu-id="d493e-104">The <xref:System.Drawing.Graphics> object provides the <xref:System.Drawing.Graphics.DrawRectangle%2A> method, and the <xref:System.Drawing.Pen> object stores features of the line, such as color and width.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d493e-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="d493e-105">Example</span></span>  
 <span data-ttu-id="d493e-106">Nell'esempio seguente disegna un rettangolo con il relativo angolo superiore sinistro a (10, 10).</span><span class="sxs-lookup"><span data-stu-id="d493e-106">The following example draws a rectangle with its upper-left corner at (10, 10).</span></span> <span data-ttu-id="d493e-107">Il rettangolo ha una larghezza pari a 100 e un'altezza pari a 50.</span><span class="sxs-lookup"><span data-stu-id="d493e-107">The rectangle has a width of 100 and a height of 50.</span></span> <span data-ttu-id="d493e-108">Il secondo argomento passato al <xref:System.Drawing.Pen.%23ctor%2A> costruttore indica che la larghezza della penna è 5 pixel.</span><span class="sxs-lookup"><span data-stu-id="d493e-108">The second argument passed to the <xref:System.Drawing.Pen.%23ctor%2A> constructor indicates that the pen width is 5 pixels.</span></span>  
  
 <span data-ttu-id="d493e-109">Quando viene disegnato il rettangolo, la penna è centrata sul bordo del rettangolo.</span><span class="sxs-lookup"><span data-stu-id="d493e-109">When the rectangle is drawn, the pen is centered on the rectangle's boundary.</span></span> <span data-ttu-id="d493e-110">Poiché la larghezza della penna è 5, i lati del rettangolo vengono disegnati 5 pixel ampia, ad esempio che 1 pixel viene disegnato sul limite, 2 pixel sono disegnate all'interno e 2 pixel sono disegnate all'esterno.</span><span class="sxs-lookup"><span data-stu-id="d493e-110">Because the pen width is 5, the sides of the rectangle are drawn 5 pixels wide, such that 1 pixel is drawn on the boundary itself, 2 pixels are drawn on the inside, and 2 pixels are drawn on the outside.</span></span> <span data-ttu-id="d493e-111">Per ulteriori informazioni sull'allineamento della penna, vedere [procedura: impostare larghezza e l'allineamento](../../../../docs/framework/winforms/advanced/how-to-set-pen-width-and-alignment.md).</span><span class="sxs-lookup"><span data-stu-id="d493e-111">For more details on pen alignment, see [How to: Set Pen Width and Alignment](../../../../docs/framework/winforms/advanced/how-to-set-pen-width-and-alignment.md).</span></span>  
  
 <span data-ttu-id="d493e-112">Nella figura seguente viene illustrato il rettangolo risulta.</span><span class="sxs-lookup"><span data-stu-id="d493e-112">The following illustration shows the resulting rectangle.</span></span> <span data-ttu-id="d493e-113">Le linee tratteggiate indicano in cui il rettangolo sarebbe stato tracciato se la larghezza della penna fosse un pixel.</span><span class="sxs-lookup"><span data-stu-id="d493e-113">The dotted lines show where the rectangle would have been drawn if the pen width had been one pixel.</span></span> <span data-ttu-id="d493e-114">La visualizzazione estesa dell'angolo superiore sinistro del rettangolo mostra che le linee nere spessore sono centrate sul linee tratteggiate.</span><span class="sxs-lookup"><span data-stu-id="d493e-114">The enlarged view of the upper-left corner of the rectangle shows that the thick black lines are centered on those dotted lines.</span></span>  
  
 <span data-ttu-id="d493e-115">![Penne](../../../../docs/framework/winforms/advanced/media/pens1.gif "pens1")</span><span class="sxs-lookup"><span data-stu-id="d493e-115">![Pens](../../../../docs/framework/winforms/advanced/media/pens1.gif "pens1")</span></span>  
  
 [!code-csharp[System.Drawing.UsingAPen#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.UsingAPen#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d493e-116">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="d493e-116">Compiling the Code</span></span>  
 <span data-ttu-id="d493e-117">L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs>`e`, un parametro del gestore eventi <xref:System.Windows.Forms.Control.Paint>.</span><span class="sxs-lookup"><span data-stu-id="d493e-117">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d493e-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d493e-118">See Also</span></span>  
 [<span data-ttu-id="d493e-119">Uso di un oggetto Pen per creare linee e forme</span><span class="sxs-lookup"><span data-stu-id="d493e-119">Using a Pen to Draw Lines and Shapes</span></span>](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)
