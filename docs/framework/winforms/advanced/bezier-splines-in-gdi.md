---
title: B&#233;Bézier Bézier in GDI+
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Bezier splines
- splines [Windows Forms], Bezier
- GDI+, Bezier splines
ms.assetid: 5774ce1e-87d4-4bc7-88c4-4862052781b8
ms.openlocfilehash: 2e247ec2bcd57c2fb2f5c32f61d38a2e7a267ff1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33517573"
---
# <a name="b233zier-splines-in-gdi"></a><span data-ttu-id="fb702-102">B&#233;Bézier Bézier in GDI+</span><span class="sxs-lookup"><span data-stu-id="fb702-102">B&#233;zier Splines in GDI+</span></span>
<span data-ttu-id="fb702-103">Una spline di Bézier è una curva specificata da quattro punti: due punti finali (p1 e p2) e due punti di controllo (c1 e c2).</span><span class="sxs-lookup"><span data-stu-id="fb702-103">A Bézier spline is a curve specified by four points: two end points (p1 and p2) and two control points (c1 and c2).</span></span> <span data-ttu-id="fb702-104">La curva inizia p1 e p2 termina.</span><span class="sxs-lookup"><span data-stu-id="fb702-104">The curve begins at p1 and ends at p2.</span></span> <span data-ttu-id="fb702-105">La curva non passano attraverso i punti di controllo, ma i punti di controllo di agire come grado attirare l'attenzione, estrarre la curva in determinate direzioni e che influenzano il modo di che curvatura.</span><span class="sxs-lookup"><span data-stu-id="fb702-105">The curve does not pass through the control points, but the control points act as magnets, pulling the curve in certain directions and influencing the way the curve bends.</span></span> <span data-ttu-id="fb702-106">Nella figura seguente mostra una curva di Bézier insieme ai relativi punti di controllo e di endpoint.</span><span class="sxs-lookup"><span data-stu-id="fb702-106">The following illustration shows a Bézier curve along with its endpoints and control points.</span></span>  
  
 <span data-ttu-id="fb702-107">![Spline di Bézier](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art11a.gif "Aboutgdip02_art11a")</span><span class="sxs-lookup"><span data-stu-id="fb702-107">![Bezier Splines](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art11a.gif "Aboutgdip02_art11a")</span></span>  
  
 <span data-ttu-id="fb702-108">La curva inizia in p1 e si sposta verso il punto di controllo c1.</span><span class="sxs-lookup"><span data-stu-id="fb702-108">The curve starts at p1 and moves toward the control point c1.</span></span> <span data-ttu-id="fb702-109">La tangente della curva in p1 è la riga disegnata da p1 a c1.</span><span class="sxs-lookup"><span data-stu-id="fb702-109">The tangent line to the curve at p1 is the line drawn from p1 to c1.</span></span> <span data-ttu-id="fb702-110">La tangente al punto finale p2 è la riga che unisce c2 e p2.</span><span class="sxs-lookup"><span data-stu-id="fb702-110">The tangent line at the endpoint p2 is the line drawn from c2 to p2.</span></span>  
  
## <a name="drawing-bzier-splines"></a><span data-ttu-id="fb702-111">Disegnare spline di Bézier</span><span class="sxs-lookup"><span data-stu-id="fb702-111">Drawing Bézier Splines</span></span>  
 <span data-ttu-id="fb702-112">Per tracciare una spline di Bézier, sono necessari un'istanza di <xref:System.Drawing.Graphics> classe e un <xref:System.Drawing.Pen>.</span><span class="sxs-lookup"><span data-stu-id="fb702-112">To draw a Bézier spline, you need an instance of the <xref:System.Drawing.Graphics> class and a <xref:System.Drawing.Pen>.</span></span> <span data-ttu-id="fb702-113">L'istanza del <xref:System.Drawing.Graphics> classe fornisce il <xref:System.Drawing.Graphics.DrawBezier%2A> (metodo) e <xref:System.Drawing.Pen> archivia gli attributi, ad esempio spessore e colore della linea utilizzata per eseguire il rendering della curva.</span><span class="sxs-lookup"><span data-stu-id="fb702-113">The instance of the <xref:System.Drawing.Graphics> class provides the <xref:System.Drawing.Graphics.DrawBezier%2A> method, and the <xref:System.Drawing.Pen> stores attributes, such as width and color, of the line used to render the curve.</span></span> <span data-ttu-id="fb702-114">Il <xref:System.Drawing.Pen> viene passato come uno degli argomenti per il <xref:System.Drawing.Graphics.DrawBezier%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="fb702-114">The <xref:System.Drawing.Pen> is passed as one of the arguments to the <xref:System.Drawing.Graphics.DrawBezier%2A> method.</span></span> <span data-ttu-id="fb702-115">Gli argomenti rimanenti passati di <xref:System.Drawing.Graphics.DrawBezier%2A> metodo sono gli endpoint e i punti di controllo.</span><span class="sxs-lookup"><span data-stu-id="fb702-115">The remaining arguments passed to the <xref:System.Drawing.Graphics.DrawBezier%2A> method are the endpoints and the control points.</span></span> <span data-ttu-id="fb702-116">Nell'esempio seguente disegna una spline di Bézier con punto iniziale (0, 0), controllare i punti (40, 20) e (80, 150) e punto finale (100, 10):</span><span class="sxs-lookup"><span data-stu-id="fb702-116">The following example draws a Bézier spline with starting point (0, 0), control points (40, 20) and (80, 150), and ending point (100, 10):</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#71](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#71)]
 [!code-vb[LinesCurvesAndShapes#71](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#71)]  
  
 <span data-ttu-id="fb702-117">Nella figura seguente mostra la curva, i punti di controllo e due tangenti.</span><span class="sxs-lookup"><span data-stu-id="fb702-117">The following illustration shows the curve, the control points, and two tangent lines.</span></span>  
  
 <span data-ttu-id="fb702-118">![Spline di Bézier](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art12.gif "Aboutgdip02_art12")</span><span class="sxs-lookup"><span data-stu-id="fb702-118">![Bezier Splines](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art12.gif "Aboutgdip02_art12")</span></span>  
  
 <span data-ttu-id="fb702-119">Spline di Bézier sono stati originariamente sviluppate da Pierre Bézier per progettazione nel settore automobilistico.</span><span class="sxs-lookup"><span data-stu-id="fb702-119">Bézier splines were originally developed by Pierre Bézier for design in the automotive industry.</span></span> <span data-ttu-id="fb702-120">Essi sono poiché rivelati utili in molti tipi di progettazione assistita da computer e vengono inoltre utilizzate per definire le strutture di tipi di carattere.</span><span class="sxs-lookup"><span data-stu-id="fb702-120">They have since proven to be useful in many types of computer-aided design and are also used to define the outlines of fonts.</span></span> <span data-ttu-id="fb702-121">Spline di Bézier possono cedere l'esecuzione di un'ampia gamma di forme, alcune delle quali sono mostrate nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="fb702-121">Bézier splines can yield a wide variety of shapes, some of which are shown in the following illustration.</span></span>  
  
 <span data-ttu-id="fb702-122">![Percorsi](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art13.gif "Aboutgdip02_art13")</span><span class="sxs-lookup"><span data-stu-id="fb702-122">![Paths](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art13.gif "Aboutgdip02_art13")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb702-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fb702-123">See Also</span></span>  
 <xref:System.Drawing.Graphics?displayProperty=nameWithType>  
 <xref:System.Drawing.Pen?displayProperty=nameWithType>  
 [<span data-ttu-id="fb702-124">Linee, curve e forme</span><span class="sxs-lookup"><span data-stu-id="fb702-124">Lines, Curves, and Shapes</span></span>](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [<span data-ttu-id="fb702-125">Costruzione e creazione di curve</span><span class="sxs-lookup"><span data-stu-id="fb702-125">Constructing and Drawing Curves</span></span>](../../../../docs/framework/winforms/advanced/constructing-and-drawing-curves.md)  
 [<span data-ttu-id="fb702-126">Procedura: Creare oggetti Graphics per disegnare</span><span class="sxs-lookup"><span data-stu-id="fb702-126">How to: Create Graphics Objects for Drawing</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)  
 [<span data-ttu-id="fb702-127">Procedura: Creare un oggetto Pen</span><span class="sxs-lookup"><span data-stu-id="fb702-127">How to: Create a Pen</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-a-pen.md)
