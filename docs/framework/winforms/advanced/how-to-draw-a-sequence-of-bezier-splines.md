---
title: 'Procedura: Disegnare una sequenza di B&#233;spline di Bézier'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- splines [Windows Forms], drawing Bezier
- Bezier splines [Windows Forms], drawing sequence of
ms.assetid: 37a0bedb-20c2-4cf0-91fa-a5509e826b30
ms.openlocfilehash: 976787f5830282a581d05a9c24d1f83dceca4b25
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62004265"
---
# <a name="how-to-draw-a-sequence-of-b233zier-splines"></a><span data-ttu-id="41174-102">Procedura: Disegnare una sequenza di B&#233;spline di Bézier</span><span class="sxs-lookup"><span data-stu-id="41174-102">How to: Draw a Sequence of B&#233;zier Splines</span></span>
<span data-ttu-id="41174-103">È possibile usare il <xref:System.Drawing.Graphics.DrawBeziers%2A> metodo di <xref:System.Drawing.Graphics> connesso di classe per creare una sequenza di spline di Bézier.</span><span class="sxs-lookup"><span data-stu-id="41174-103">You can use the <xref:System.Drawing.Graphics.DrawBeziers%2A> method of the <xref:System.Drawing.Graphics> class to draw a sequence of connected Bézier splines.</span></span>  
  
## <a name="example"></a><span data-ttu-id="41174-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="41174-104">Example</span></span>  
 <span data-ttu-id="41174-105">L'esempio seguente disegna una curva che è costituito da due spline di Bézier collegate.</span><span class="sxs-lookup"><span data-stu-id="41174-105">The following example draws a curve that consists of two connected Bézier splines.</span></span> <span data-ttu-id="41174-106">L'endpoint di spline di Bézier il primo è il punto di inizio della seconda spline di Bézier.</span><span class="sxs-lookup"><span data-stu-id="41174-106">The endpoint of the first Bézier spline is the start point of the second Bézier spline.</span></span>  
  
 <span data-ttu-id="41174-107">La figura seguente mostra la spline collegate insieme a sette punti:</span><span class="sxs-lookup"><span data-stu-id="41174-107">The following illustration shows the connected splines along with the seven points:</span></span>  
  
 ![Figura che illustra la spline collegate insieme a sette punti.](./media/how-to-draw-a-sequence-of-bezier-splines/bezier-spline-seven-points.png)  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="41174-109">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="41174-109">Compiling the Code</span></span>  
 <span data-ttu-id="41174-110">L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs> `e`, ovvero un parametro del <xref:System.Windows.Forms.Control.Paint> gestore dell'evento.</span><span class="sxs-lookup"><span data-stu-id="41174-110">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41174-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="41174-111">See also</span></span>

- [<span data-ttu-id="41174-112">Grafica e disegno in Windows Form</span><span class="sxs-lookup"><span data-stu-id="41174-112">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="41174-113">Spline di Bézier in GDI+</span><span class="sxs-lookup"><span data-stu-id="41174-113">Bézier Splines in GDI+</span></span>](bezier-splines-in-gdi.md)
- [<span data-ttu-id="41174-114">Costruzione e creazione di curve</span><span class="sxs-lookup"><span data-stu-id="41174-114">Constructing and Drawing Curves</span></span>](constructing-and-drawing-curves.md)
