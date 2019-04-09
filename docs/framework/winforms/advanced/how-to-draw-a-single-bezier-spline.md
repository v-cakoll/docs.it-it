---
title: 'Procedura: Disegnare una singola B&#233;Spline di Bézier'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Bezier splines [Windows Forms], drawing
- drawing [Windows Forms], Bezier splines
ms.assetid: f4f3fe30-f0a6-4743-ac91-11310cebea9f
ms.openlocfilehash: ebb53e7df979a553ed4a44deba34345c9ecac772
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59171678"
---
# <a name="how-to-draw-a-single-b233zier-spline"></a><span data-ttu-id="076f5-102">Procedura: Disegnare una singola B&#233;Spline di Bézier</span><span class="sxs-lookup"><span data-stu-id="076f5-102">How to: Draw a Single B&#233;zier Spline</span></span>
<span data-ttu-id="076f5-103">Viene definita una spline di Bézier da quattro punti: un punto di partenza, due punti di controllo e un endpoint.</span><span class="sxs-lookup"><span data-stu-id="076f5-103">A Bézier spline is defined by four points: a start point, two control points, and an endpoint.</span></span>  
  
## <a name="example"></a><span data-ttu-id="076f5-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="076f5-104">Example</span></span>  
 <span data-ttu-id="076f5-105">L'esempio seguente disegna una spline di Bézier con endpoint (200, 100) e il punto di inizio (10, 100).</span><span class="sxs-lookup"><span data-stu-id="076f5-105">The following example draws a Bézier spline with start point (10, 100) and endpoint (200, 100).</span></span> <span data-ttu-id="076f5-106">I punti di controllo sono (100, 10) e (150, 150).</span><span class="sxs-lookup"><span data-stu-id="076f5-106">The control points are (100, 10) and (150, 150).</span></span>  
  
 <span data-ttu-id="076f5-107">La figura seguente mostra la spline di Bézier risulta con il punto iniziale, i punti di controllo ed endpoint.</span><span class="sxs-lookup"><span data-stu-id="076f5-107">The following illustration shows the resulting Bézier spline along with its start point, control points, and endpoint.</span></span> <span data-ttu-id="076f5-108">L'illustrazione mostra anche struttura convessa della spline, che è un poligono costituito dalla connessione di quattro punti con linee rette.</span><span class="sxs-lookup"><span data-stu-id="076f5-108">The illustration also shows the spline's convex hull, which is a polygon formed by connecting the four points with straight lines.</span></span>  
  
 ![Illustrazione di una Spline di Bézier.](./media/how-to-draw-a-single-bezier-spline/bezier-spline-illustration.png)  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="076f5-110">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="076f5-110">Compiling the Code</span></span>  
 <span data-ttu-id="076f5-111">L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs> `e`, ovvero un parametro del <xref:System.Windows.Forms.Control.Paint> gestore dell'evento.</span><span class="sxs-lookup"><span data-stu-id="076f5-111">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="076f5-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="076f5-112">See also</span></span>

- <xref:System.Drawing.Graphics.DrawBezier%2A>
- [<span data-ttu-id="076f5-113">Spline di Bézier in GDI+</span><span class="sxs-lookup"><span data-stu-id="076f5-113">Bézier Splines in GDI+</span></span>](bezier-splines-in-gdi.md)
- [<span data-ttu-id="076f5-114">Procedura: Disegnare una sequenza di spline di Bézier</span><span class="sxs-lookup"><span data-stu-id="076f5-114">How to: Draw a Sequence of Bézier Splines</span></span>](how-to-draw-a-sequence-of-bezier-splines.md)
