---
title: Percorsi di oggetti Graphics in GDI+
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [Windows Forms], paths
- GDI+, drawing paths
- paths [Windows Forms], drawing
- drawing [Windows Forms], paths
ms.assetid: a5500dec-666c-41fd-9da3-2169dd89c5eb
ms.openlocfilehash: b6f0ebd500aa3503c0c0d473ebe21a61f4438862
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57720423"
---
# <a name="graphics-paths-in-gdi"></a><span data-ttu-id="bbfee-102">Percorsi di oggetti Graphics in GDI+</span><span class="sxs-lookup"><span data-stu-id="bbfee-102">Graphics Paths in GDI+</span></span>
<span data-ttu-id="bbfee-103">I percorsi sono costituiti dalla combinazione di linee, rettangoli e le curve semplice.</span><span class="sxs-lookup"><span data-stu-id="bbfee-103">Paths are formed by combining lines, rectangles, and simple curves.</span></span> <span data-ttu-id="bbfee-104">Si ricorderà dal [Cenni preliminari sulla grafica vettoriale](vector-graphics-overview.md) che i blocchi predefiniti seguenti hanno dimostrato di essere particolarmente utile per il disegno di immagini:</span><span class="sxs-lookup"><span data-stu-id="bbfee-104">Recall from the [Vector Graphics Overview](vector-graphics-overview.md) that the following basic building blocks have proven to be the most useful for drawing pictures:</span></span>  
  
-   <span data-ttu-id="bbfee-105">Linee</span><span class="sxs-lookup"><span data-stu-id="bbfee-105">Lines</span></span>  
  
-   <span data-ttu-id="bbfee-106">Rettangoli</span><span class="sxs-lookup"><span data-stu-id="bbfee-106">Rectangles</span></span>  
  
-   <span data-ttu-id="bbfee-107">Puntini di sospensione</span><span class="sxs-lookup"><span data-stu-id="bbfee-107">Ellipses</span></span>  
  
-   <span data-ttu-id="bbfee-108">Archi</span><span class="sxs-lookup"><span data-stu-id="bbfee-108">Arcs</span></span>  
  
-   <span data-ttu-id="bbfee-109">Poligoni</span><span class="sxs-lookup"><span data-stu-id="bbfee-109">Polygons</span></span>  
  
-   <span data-ttu-id="bbfee-110">Spline cardinali</span><span class="sxs-lookup"><span data-stu-id="bbfee-110">Cardinal splines</span></span>  
  
-   <span data-ttu-id="bbfee-111">Spline di Bézier</span><span class="sxs-lookup"><span data-stu-id="bbfee-111">Bézier splines</span></span>  
  
 <span data-ttu-id="bbfee-112">In GDI+, le <xref:System.Drawing.Drawing2D.GraphicsPath> oggetto consente di raccogliere una sequenza di questi blocchi predefiniti in una singola unità.</span><span class="sxs-lookup"><span data-stu-id="bbfee-112">In GDI+, the <xref:System.Drawing.Drawing2D.GraphicsPath> object allows you to collect a sequence of these building blocks into a single unit.</span></span> <span data-ttu-id="bbfee-113">L'intera sequenza di linee, rettangoli, poligoni e curve possa quindi disegnata con una chiamata ai <xref:System.Drawing.Graphics.DrawPath%2A> metodo del <xref:System.Drawing.Graphics> classe.</span><span class="sxs-lookup"><span data-stu-id="bbfee-113">The entire sequence of lines, rectangles, polygons, and curves can then be drawn with one call to the <xref:System.Drawing.Graphics.DrawPath%2A> method of the <xref:System.Drawing.Graphics> class.</span></span> <span data-ttu-id="bbfee-114">La figura seguente mostra un percorso creato dalla combinazione di una riga, un arco, una spline di Bézier e una spline di tipo cardinal.</span><span class="sxs-lookup"><span data-stu-id="bbfee-114">The following illustration shows a path created by combining a line, an arc, a Bézier spline, and a cardinal spline.</span></span>  
  
 <span data-ttu-id="bbfee-115">![Path](./media/aboutgdip02-art14.gif "Aboutgdip02_art14")</span><span class="sxs-lookup"><span data-stu-id="bbfee-115">![Path](./media/aboutgdip02-art14.gif "Aboutgdip02_art14")</span></span>  
  
## <a name="using-a-path"></a><span data-ttu-id="bbfee-116">Utilizzando un percorso</span><span class="sxs-lookup"><span data-stu-id="bbfee-116">Using a Path</span></span>  
 <span data-ttu-id="bbfee-117">Il <xref:System.Drawing.Drawing2D.GraphicsPath> classe fornisce i metodi seguenti per la creazione di una sequenza di elementi da disegnare: <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddRectangle%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddEllipse%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddArc%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddPolygon%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A> (per cardinali), e <xref:System.Drawing.Drawing2D.GraphicsPath.AddBezier%2A>.</span><span class="sxs-lookup"><span data-stu-id="bbfee-117">The <xref:System.Drawing.Drawing2D.GraphicsPath> class provides the following methods for creating a sequence of items to be drawn: <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddRectangle%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddEllipse%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddArc%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddPolygon%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A> (for cardinal splines), and <xref:System.Drawing.Drawing2D.GraphicsPath.AddBezier%2A>.</span></span> <span data-ttu-id="bbfee-118">Ognuno di questi metodi è in overload; ogni metodo, ovvero supporta diversi elenchi di parametri diversi.</span><span class="sxs-lookup"><span data-stu-id="bbfee-118">Each of these methods is overloaded; that is, each method supports several different parameter lists.</span></span> <span data-ttu-id="bbfee-119">Ad esempio, una variazione del <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> metodo riceve quattro interi e un'altra variazione del <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> metodo riceve due <xref:System.Drawing.Point> oggetti.</span><span class="sxs-lookup"><span data-stu-id="bbfee-119">For example, one variation of the <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> method receives four integers, and another variation of the <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> method receives two <xref:System.Drawing.Point> objects.</span></span>  
  
 <span data-ttu-id="bbfee-120">I metodi per l'aggiunta di linee, rettangoli e spline di Bézier in un percorso sono associati più metodi che aggiungono diversi elementi nel percorso in una singola chiamata: <xref:System.Drawing.Drawing2D.GraphicsPath.AddLines%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddRectangles%2A>, e <xref:System.Drawing.Drawing2D.GraphicsPath.AddBeziers%2A>.</span><span class="sxs-lookup"><span data-stu-id="bbfee-120">The methods for adding lines, rectangles, and Bézier splines to a path have plural companion methods that add several items to the path in a single call: <xref:System.Drawing.Drawing2D.GraphicsPath.AddLines%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddRectangles%2A>, and <xref:System.Drawing.Drawing2D.GraphicsPath.AddBeziers%2A>.</span></span> <span data-ttu-id="bbfee-121">Inoltre, il <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A> e <xref:System.Drawing.Drawing2D.GraphicsPath.AddArc%2A> metodi includono metodi complementare, <xref:System.Drawing.Drawing2D.GraphicsPath.AddClosedCurve%2A> e <xref:System.Drawing.Drawing2D.GraphicsPath.AddPie%2A>, che consentono di aggiungere una curva chiusa o un grafico a torta al percorso.</span><span class="sxs-lookup"><span data-stu-id="bbfee-121">Also, the <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A> and <xref:System.Drawing.Drawing2D.GraphicsPath.AddArc%2A> methods have companion methods, <xref:System.Drawing.Drawing2D.GraphicsPath.AddClosedCurve%2A> and <xref:System.Drawing.Drawing2D.GraphicsPath.AddPie%2A>, that add a closed curve or pie to the path.</span></span>  
  
 <span data-ttu-id="bbfee-122">Per disegnare un tracciato, è necessario un <xref:System.Drawing.Graphics> oggetti, una <xref:System.Drawing.Pen> oggetti e un <xref:System.Drawing.Drawing2D.GraphicsPath> oggetto.</span><span class="sxs-lookup"><span data-stu-id="bbfee-122">To draw a path, you need a <xref:System.Drawing.Graphics> object, a <xref:System.Drawing.Pen> object, and a <xref:System.Drawing.Drawing2D.GraphicsPath> object.</span></span> <span data-ttu-id="bbfee-123">Il <xref:System.Drawing.Graphics> oggetto fornisce le <xref:System.Drawing.Graphics.DrawPath%2A> metodo e il <xref:System.Drawing.Pen> oggetto archivia gli attributi, ad esempio la larghezza e il colore della linea utilizzata per eseguire il rendering di percorso.</span><span class="sxs-lookup"><span data-stu-id="bbfee-123">The <xref:System.Drawing.Graphics> object provides the <xref:System.Drawing.Graphics.DrawPath%2A> method, and the <xref:System.Drawing.Pen> object stores attributes, such as width and color, of the line used to render the path.</span></span> <span data-ttu-id="bbfee-124">Il <xref:System.Drawing.Drawing2D.GraphicsPath> oggetto archivia la sequenza di linee e curve che costituiscono il percorso.</span><span class="sxs-lookup"><span data-stu-id="bbfee-124">The <xref:System.Drawing.Drawing2D.GraphicsPath> object stores the sequence of lines and curves that make up the path.</span></span> <span data-ttu-id="bbfee-125">Il <xref:System.Drawing.Pen> oggetto e il <xref:System.Drawing.Drawing2D.GraphicsPath> oggetto vengono passati come argomenti per il <xref:System.Drawing.Graphics.DrawPath%2A> (metodo).</span><span class="sxs-lookup"><span data-stu-id="bbfee-125">The <xref:System.Drawing.Pen> object and the <xref:System.Drawing.Drawing2D.GraphicsPath> object are passed as arguments to the <xref:System.Drawing.Graphics.DrawPath%2A> method.</span></span> <span data-ttu-id="bbfee-126">L'esempio seguente disegna un percorso che è costituito da una riga, un'ellisse e una spline di Bézier:</span><span class="sxs-lookup"><span data-stu-id="bbfee-126">The following example draws a path that consists of a line, an ellipse, and a Bézier spline:</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#101](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#101)]
 [!code-vb[LinesCurvesAndShapes#101](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#101)]  
  
 <span data-ttu-id="bbfee-127">La figura seguente mostra il percorso.</span><span class="sxs-lookup"><span data-stu-id="bbfee-127">The following illustration shows the path.</span></span>  
  
 <span data-ttu-id="bbfee-128">![Path](./media/aboutgdip02-art15.gif "Aboutgdip02_art15")</span><span class="sxs-lookup"><span data-stu-id="bbfee-128">![Path](./media/aboutgdip02-art15.gif "Aboutgdip02_art15")</span></span>  
  
 <span data-ttu-id="bbfee-129">Oltre all'aggiunta di rettangoli, linee e curve a un percorso, è possibile aggiungere i percorsi in un percorso.</span><span class="sxs-lookup"><span data-stu-id="bbfee-129">In addition to adding lines, rectangles, and curves to a path, you can add paths to a path.</span></span> <span data-ttu-id="bbfee-130">In questo modo è possibile combinare percorsi esistenti per creare percorsi lunghi e complessi.</span><span class="sxs-lookup"><span data-stu-id="bbfee-130">This allows you to combine existing paths to form large, complex paths.</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#102](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#102)]
 [!code-vb[LinesCurvesAndShapes#102](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#102)]  
  
 <span data-ttu-id="bbfee-131">Esistono due altri elementi di cui è possibile aggiungere a un percorso: stringhe e grafici a torta.</span><span class="sxs-lookup"><span data-stu-id="bbfee-131">There are two other items you can add to a path: strings and pies.</span></span> <span data-ttu-id="bbfee-132">Un grafico a torta è riportata una parte all'interno di un'ellisse.</span><span class="sxs-lookup"><span data-stu-id="bbfee-132">A pie is a portion of the interior of an ellipse.</span></span> <span data-ttu-id="bbfee-133">L'esempio seguente crea un percorso da un arco, una spline di tipo cardinal, una stringa e un grafico a torta:</span><span class="sxs-lookup"><span data-stu-id="bbfee-133">The following example creates a path from an arc, a cardinal spline, a string, and a pie:</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#103](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#103)]
 [!code-vb[LinesCurvesAndShapes#103](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#103)]  
  
 <span data-ttu-id="bbfee-134">La figura seguente mostra il percorso.</span><span class="sxs-lookup"><span data-stu-id="bbfee-134">The following illustration shows the path.</span></span> <span data-ttu-id="bbfee-135">Si noti che un percorso non deve essere connessa; l'arco, di tipo Cardinal, stringa e a torta sono separati.</span><span class="sxs-lookup"><span data-stu-id="bbfee-135">Note that a path does not have to be connected; the arc, cardinal spline, string, and pie are separated.</span></span>  
  
 <span data-ttu-id="bbfee-136">![Paths](./media/aboutgdip02-art16.gif "Aboutgdip02_Art16")</span><span class="sxs-lookup"><span data-stu-id="bbfee-136">![Paths](./media/aboutgdip02-art16.gif "Aboutgdip02_Art16")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bbfee-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bbfee-137">See also</span></span>
- <xref:System.Drawing.Drawing2D.GraphicsPath?displayProperty=nameWithType>
- <xref:System.Drawing.Point?displayProperty=nameWithType>
- [<span data-ttu-id="bbfee-138">Linee, curve e forme</span><span class="sxs-lookup"><span data-stu-id="bbfee-138">Lines, Curves, and Shapes</span></span>](lines-curves-and-shapes.md)
- [<span data-ttu-id="bbfee-139">Procedura: Creare oggetti Graphics per disegnare</span><span class="sxs-lookup"><span data-stu-id="bbfee-139">How to: Create Graphics Objects for Drawing</span></span>](how-to-create-graphics-objects-for-drawing.md)
- [<span data-ttu-id="bbfee-140">Costruzione e creazione di percorsi</span><span class="sxs-lookup"><span data-stu-id="bbfee-140">Constructing and Drawing Paths</span></span>](constructing-and-drawing-paths.md)
