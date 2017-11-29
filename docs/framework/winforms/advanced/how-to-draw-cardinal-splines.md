---
title: 'Procedura: disegnare spline di tipo Cardinal'
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
- cardinal splines [Windows Forms], drawing
- drawing [Windows Forms], cardinal splines
- graphics [Windows Forms], cardinal splines
ms.assetid: a4a41e80-4461-4b47-b6bd-2c5e68881994
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c47ff269cb1c367abee0be197fdc80485fb37b97
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-draw-cardinal-splines"></a><span data-ttu-id="53494-102">Procedura: disegnare spline di tipo Cardinal</span><span class="sxs-lookup"><span data-stu-id="53494-102">How to: Draw Cardinal Splines</span></span>
<span data-ttu-id="53494-103">Spline di tipo cardinal è una curva che passa attraverso un determinato set di punti.</span><span class="sxs-lookup"><span data-stu-id="53494-103">A cardinal spline is a curve that passes smoothly through a given set of points.</span></span> <span data-ttu-id="53494-104">Per disegnare spline di tipo cardinal, creare un <xref:System.Drawing.Graphics> dell'oggetto e passare l'indirizzo di una matrice di punti per il <xref:System.Drawing.Graphics.DrawCurve%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="53494-104">To draw a cardinal spline, create a <xref:System.Drawing.Graphics> object and pass the address of an array of points to the <xref:System.Drawing.Graphics.DrawCurve%2A> method.</span></span>  
  
### <a name="drawing-a-bell-shaped-cardinal-spline"></a><span data-ttu-id="53494-105">Creazione di una Spline di tipo Cardinal a campana</span><span class="sxs-lookup"><span data-stu-id="53494-105">Drawing a Bell-Shaped Cardinal Spline</span></span>  
  
-   <span data-ttu-id="53494-106">Nell'esempio seguente disegna una spline di tipo cardinal a campana che passa attraverso cinque punti designati.</span><span class="sxs-lookup"><span data-stu-id="53494-106">The following example draws a bell-shaped cardinal spline that passes through five designated points.</span></span> <span data-ttu-id="53494-107">Nella figura seguente mostra la curva e cinque punti.</span><span class="sxs-lookup"><span data-stu-id="53494-107">The following illustration shows the curve and five points.</span></span>  
  
     <span data-ttu-id="53494-108">![Spline di tipo Cardinal](../../../../docs/framework/winforms/advanced/media/cardinalspline1.png "CardinalSpline1")</span><span class="sxs-lookup"><span data-stu-id="53494-108">![Cardinal Spline](../../../../docs/framework/winforms/advanced/media/cardinalspline1.png "CardinalSpline1")</span></span>  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#21)]  
  
### <a name="drawing-a-closed-cardinal-spline"></a><span data-ttu-id="53494-109">Disegno di una spline di tipo Cardinal chiusa</span><span class="sxs-lookup"><span data-stu-id="53494-109">Drawing a Closed Cardinal Spline</span></span>  
  
-   <span data-ttu-id="53494-110">Utilizzare il <xref:System.Drawing.Graphics.DrawClosedCurve%2A> metodo la <xref:System.Drawing.Graphics> classe per disegnare una spline di tipo cardinal chiusa.</span><span class="sxs-lookup"><span data-stu-id="53494-110">Use the <xref:System.Drawing.Graphics.DrawClosedCurve%2A> method of the <xref:System.Drawing.Graphics> class to draw a closed cardinal spline.</span></span> <span data-ttu-id="53494-111">In una spline di tipo cardinal chiusa, la curva continua fino all'ultimo punto della matrice e si connette con il primo punto nella matrice.</span><span class="sxs-lookup"><span data-stu-id="53494-111">In a closed cardinal spline, the curve continues through the last point in the array and connects with the first point in the array.</span></span> <span data-ttu-id="53494-112">Nell'esempio seguente disegna una spline di tipo cardinal chiusa che passa attraverso sei punti designati.</span><span class="sxs-lookup"><span data-stu-id="53494-112">The following example draws a closed cardinal spline that passes through six designated points.</span></span> <span data-ttu-id="53494-113">Nella figura seguente mostra la spline chiusa e sei punti.</span><span class="sxs-lookup"><span data-stu-id="53494-113">The following illustration shows the closed spline along with the six points.</span></span>  
  
 <span data-ttu-id="53494-114">![Spline di tipo Cardinal](../../../../docs/framework/winforms/advanced/media/cardinalspline1a.png "CardinalSpline1A")</span><span class="sxs-lookup"><span data-stu-id="53494-114">![Cardinal Spline](../../../../docs/framework/winforms/advanced/media/cardinalspline1a.png "CardinalSpline1A")</span></span>  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#22](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#22)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#22](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#22)]  
  
### <a name="changing-the-bend-of-a-cardinal-spline"></a><span data-ttu-id="53494-115">Modifica della curvatura di una spline di tipo Cardinal</span><span class="sxs-lookup"><span data-stu-id="53494-115">Changing the Bend of a Cardinal Spline</span></span>  
  
-   <span data-ttu-id="53494-116">Possibile modificare la spline di tipo cardinal passando un argomento di tensione per la <xref:System.Drawing.Graphics.DrawCurve%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="53494-116">Change the way a cardinal spline bends by passing a tension argument to the <xref:System.Drawing.Graphics.DrawCurve%2A> method.</span></span> <span data-ttu-id="53494-117">L'esempio seguente disegna una spline di tipo cardinal tre che passano attraverso lo stesso set di punti.</span><span class="sxs-lookup"><span data-stu-id="53494-117">The following example draws three cardinal splines that pass through the same set of points.</span></span> <span data-ttu-id="53494-118">Nella figura seguente mostra le tre curve insieme ai relativi valori di tensione.</span><span class="sxs-lookup"><span data-stu-id="53494-118">The following illustration shows the three splines along with their tension values.</span></span> <span data-ttu-id="53494-119">Si noti che quando la tensione è 0, i punti vengono collegati da linee rette.</span><span class="sxs-lookup"><span data-stu-id="53494-119">Note that when the tension is 0, the points are connected by straight lines.</span></span>  
  
 <span data-ttu-id="53494-120">![Spline di tipo Cardinal](../../../../docs/framework/winforms/advanced/media/cardinalspline2.png "CardinalSpline2")</span><span class="sxs-lookup"><span data-stu-id="53494-120">![Cardinal Spline](../../../../docs/framework/winforms/advanced/media/cardinalspline2.png "CardinalSpline2")</span></span>  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#23](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#23)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#23](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#23)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="53494-121">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="53494-121">Compiling the Code</span></span>  
 <span data-ttu-id="53494-122">Negli esempi precedenti sono progettati per l'uso con Windows Form e richiedono <xref:System.Windows.Forms.PaintEventArgs> `e`, ovvero un parametro del <xref:System.Windows.Forms.Control.Paint> gestore dell'evento.</span><span class="sxs-lookup"><span data-stu-id="53494-122">The preceding examples are designed for use with Windows Forms, and they require <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53494-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="53494-123">See Also</span></span>  
 [<span data-ttu-id="53494-124">Linee, curve e forme</span><span class="sxs-lookup"><span data-stu-id="53494-124">Lines, Curves, and Shapes</span></span>](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [<span data-ttu-id="53494-125">Costruzione e creazione di curve</span><span class="sxs-lookup"><span data-stu-id="53494-125">Constructing and Drawing Curves</span></span>](../../../../docs/framework/winforms/advanced/constructing-and-drawing-curves.md)
