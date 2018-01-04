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
ms.workload: dotnet
ms.openlocfilehash: 6d2eaf570190f85ca084e5a5ab5d1bee1be56871
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-draw-a-single-b233zier-spline"></a><span data-ttu-id="11969-102">Procedura: disegno di un singolo B &#233; Spline di Bézier</span><span class="sxs-lookup"><span data-stu-id="11969-102">How to: Draw a Single B&#233;zier Spline</span></span>
<span data-ttu-id="11969-103">Una spline di Bézier è definita da quattro punti: un punto di inizio, due punti di controllo e un endpoint.</span><span class="sxs-lookup"><span data-stu-id="11969-103">A Bézier spline is defined by four points: a start point, two control points, and an endpoint.</span></span>  
  
## <a name="example"></a><span data-ttu-id="11969-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="11969-104">Example</span></span>  
 <span data-ttu-id="11969-105">Nell'esempio seguente disegna una spline di Bézier con endpoint (200, 100) e il punto di inizio (10, 100).</span><span class="sxs-lookup"><span data-stu-id="11969-105">The following example draws a Bézier spline with start point (10, 100) and endpoint (200, 100).</span></span> <span data-ttu-id="11969-106">I punti di controllo sono (100, 10) e (150, 150).</span><span class="sxs-lookup"><span data-stu-id="11969-106">The control points are (100, 10) and (150, 150).</span></span>  
  
 <span data-ttu-id="11969-107">Nella figura seguente mostra la spline di Bézier risulta con il punto iniziale, punti di controllo e l'endpoint.</span><span class="sxs-lookup"><span data-stu-id="11969-107">The following illustration shows the resulting Bézier spline along with its start point, control points, and endpoint.</span></span> <span data-ttu-id="11969-108">L'illustrazione mostra anche convessa della spline, un poligono formato collegando i quattro punti con linee rette.</span><span class="sxs-lookup"><span data-stu-id="11969-108">The illustration also shows the spline's convex hull, which is a polygon formed by connecting the four points with straight lines.</span></span>  
  
 <span data-ttu-id="11969-109">![Spline di Bézier](../../../../docs/framework/winforms/advanced/media/bezierspline1.png "BezierSpline1")</span><span class="sxs-lookup"><span data-stu-id="11969-109">![Bezier Spline](../../../../docs/framework/winforms/advanced/media/bezierspline1.png "BezierSpline1")</span></span>  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="11969-110">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="11969-110">Compiling the Code</span></span>  
 <span data-ttu-id="11969-111">L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs> `e`, un parametro del gestore eventi <xref:System.Windows.Forms.Control.Paint>.</span><span class="sxs-lookup"><span data-stu-id="11969-111">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11969-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="11969-112">See Also</span></span>  
 <xref:System.Drawing.Graphics.DrawBezier%2A>  
 [<span data-ttu-id="11969-113">Spline di Bézier in GDI+</span><span class="sxs-lookup"><span data-stu-id="11969-113">Bézier Splines in GDI+</span></span>](../../../../docs/framework/winforms/advanced/bezier-splines-in-gdi.md)  
 [<span data-ttu-id="11969-114">Procedura: Disegnare una sequenza di spline di Bézier</span><span class="sxs-lookup"><span data-stu-id="11969-114">How to: Draw a Sequence of Bézier Splines</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-a-sequence-of-bezier-splines.md)
