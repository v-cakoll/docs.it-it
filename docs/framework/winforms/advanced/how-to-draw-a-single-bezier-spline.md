---
title: "Procedura: disegno di un singolo B &#233; Spline di Bézier"
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
- Bezier splines [Windows Forms], drawing
- drawing [Windows Forms], Bezier splines
ms.assetid: f4f3fe30-f0a6-4743-ac91-11310cebea9f
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0ebdba9e01824cc764a6ab759da049add180ba83
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-draw-a-single-b233zier-spline"></a><span data-ttu-id="9ab35-102">Procedura: disegno di un singolo B &#233; Spline di Bézier</span><span class="sxs-lookup"><span data-stu-id="9ab35-102">How to: Draw a Single B&#233;zier Spline</span></span>
<span data-ttu-id="9ab35-103">Una spline di Bézier è definita da quattro punti: un punto di inizio, due punti di controllo e un endpoint.</span><span class="sxs-lookup"><span data-stu-id="9ab35-103">A Bézier spline is defined by four points: a start point, two control points, and an endpoint.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9ab35-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="9ab35-104">Example</span></span>  
 <span data-ttu-id="9ab35-105">Nell'esempio seguente disegna una spline di Bézier con endpoint (200, 100) e il punto di inizio (10, 100).</span><span class="sxs-lookup"><span data-stu-id="9ab35-105">The following example draws a Bézier spline with start point (10, 100) and endpoint (200, 100).</span></span> <span data-ttu-id="9ab35-106">I punti di controllo sono (100, 10) e (150, 150).</span><span class="sxs-lookup"><span data-stu-id="9ab35-106">The control points are (100, 10) and (150, 150).</span></span>  
  
 <span data-ttu-id="9ab35-107">Nella figura seguente mostra la spline di Bézier risulta con il punto iniziale, punti di controllo e l'endpoint.</span><span class="sxs-lookup"><span data-stu-id="9ab35-107">The following illustration shows the resulting Bézier spline along with its start point, control points, and endpoint.</span></span> <span data-ttu-id="9ab35-108">L'illustrazione mostra anche convessa della spline, un poligono formato collegando i quattro punti con linee rette.</span><span class="sxs-lookup"><span data-stu-id="9ab35-108">The illustration also shows the spline's convex hull, which is a polygon formed by connecting the four points with straight lines.</span></span>  
  
 <span data-ttu-id="9ab35-109">![Spline di Bézier](../../../../docs/framework/winforms/advanced/media/bezierspline1.png "BezierSpline1")</span><span class="sxs-lookup"><span data-stu-id="9ab35-109">![Bezier Spline](../../../../docs/framework/winforms/advanced/media/bezierspline1.png "BezierSpline1")</span></span>  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="9ab35-110">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="9ab35-110">Compiling the Code</span></span>  
 <span data-ttu-id="9ab35-111">L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs> `e`, un parametro del gestore eventi <xref:System.Windows.Forms.Control.Paint>.</span><span class="sxs-lookup"><span data-stu-id="9ab35-111">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ab35-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9ab35-112">See Also</span></span>  
 <xref:System.Drawing.Graphics.DrawBezier%2A>  
 [<span data-ttu-id="9ab35-113">Spline di Bézier in GDI+</span><span class="sxs-lookup"><span data-stu-id="9ab35-113">Bézier Splines in GDI+</span></span>](../../../../docs/framework/winforms/advanced/bezier-splines-in-gdi.md)  
 [<span data-ttu-id="9ab35-114">Procedura: Disegnare una sequenza di spline di Bézier</span><span class="sxs-lookup"><span data-stu-id="9ab35-114">How to: Draw a Sequence of Bézier Splines</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-a-sequence-of-bezier-splines.md)
