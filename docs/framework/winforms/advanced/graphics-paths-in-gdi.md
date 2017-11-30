---
title: Percorsi di oggetti Graphics in GDI+
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
- graphics [Windows Forms], paths
- GDI+, drawing paths
- paths [Windows Forms], drawing
- drawing [Windows Forms], paths
ms.assetid: a5500dec-666c-41fd-9da3-2169dd89c5eb
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e027228ea1cc047f213c28ac3a4984c2f0227c5a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="graphics-paths-in-gdi"></a><span data-ttu-id="e7261-102">Percorsi di oggetti Graphics in GDI+</span><span class="sxs-lookup"><span data-stu-id="e7261-102">Graphics Paths in GDI+</span></span>
<span data-ttu-id="e7261-103">I percorsi sono costituiti dalla combinazione di linee, rettangoli e curve semplici.</span><span class="sxs-lookup"><span data-stu-id="e7261-103">Paths are formed by combining lines, rectangles, and simple curves.</span></span> <span data-ttu-id="e7261-104">Ricorda di [Cenni preliminari sulla grafica vettoriale](../../../../docs/framework/winforms/advanced/vector-graphics-overview.md) i seguenti blocchi predefiniti si sono rivelati a essere più utili per il disegno di immagini:</span><span class="sxs-lookup"><span data-stu-id="e7261-104">Recall from the [Vector Graphics Overview](../../../../docs/framework/winforms/advanced/vector-graphics-overview.md) that the following basic building blocks have proven to be the most useful for drawing pictures:</span></span>  
  
-   <span data-ttu-id="e7261-105">Linee</span><span class="sxs-lookup"><span data-stu-id="e7261-105">Lines</span></span>  
  
-   <span data-ttu-id="e7261-106">Rettangoli</span><span class="sxs-lookup"><span data-stu-id="e7261-106">Rectangles</span></span>  
  
-   <span data-ttu-id="e7261-107">Puntini di sospensione</span><span class="sxs-lookup"><span data-stu-id="e7261-107">Ellipses</span></span>  
  
-   <span data-ttu-id="e7261-108">Archi</span><span class="sxs-lookup"><span data-stu-id="e7261-108">Arcs</span></span>  
  
-   <span data-ttu-id="e7261-109">Poligoni</span><span class="sxs-lookup"><span data-stu-id="e7261-109">Polygons</span></span>  
  
-   <span data-ttu-id="e7261-110">Spline cardinali</span><span class="sxs-lookup"><span data-stu-id="e7261-110">Cardinal splines</span></span>  
  
-   <span data-ttu-id="e7261-111">Spline di Bézier</span><span class="sxs-lookup"><span data-stu-id="e7261-111">Bézier splines</span></span>  
  
 <span data-ttu-id="e7261-112">In GDI+, i <xref:System.Drawing.Drawing2D.GraphicsPath> oggetto consente di raccogliere una sequenza di tali blocchi predefiniti in una singola unità.</span><span class="sxs-lookup"><span data-stu-id="e7261-112">In GDI+, the <xref:System.Drawing.Drawing2D.GraphicsPath> object allows you to collect a sequence of these building blocks into a single unit.</span></span> <span data-ttu-id="e7261-113">L'intera sequenza di linee, rettangoli, poligoni e curve può quindi essere disegnata con una chiamata al <xref:System.Drawing.Graphics.DrawPath%2A> metodo la <xref:System.Drawing.Graphics> classe.</span><span class="sxs-lookup"><span data-stu-id="e7261-113">The entire sequence of lines, rectangles, polygons, and curves can then be drawn with one call to the <xref:System.Drawing.Graphics.DrawPath%2A> method of the <xref:System.Drawing.Graphics> class.</span></span> <span data-ttu-id="e7261-114">Nella figura seguente viene illustrato un percorso creato dalla combinazione di una riga, un arco, una spline di Bézier e una spline di tipo cardinal.</span><span class="sxs-lookup"><span data-stu-id="e7261-114">The following illustration shows a path created by combining a line, an arc, a Bézier spline, and a cardinal spline.</span></span>  
  
 <span data-ttu-id="e7261-115">![Percorso](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art14.gif "Aboutgdip02_art14")</span><span class="sxs-lookup"><span data-stu-id="e7261-115">![Path](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art14.gif "Aboutgdip02_art14")</span></span>  
  
## <a name="using-a-path"></a><span data-ttu-id="e7261-116">Utilizzo di un percorso</span><span class="sxs-lookup"><span data-stu-id="e7261-116">Using a Path</span></span>  
 <span data-ttu-id="e7261-117">Il <xref:System.Drawing.Drawing2D.GraphicsPath> classe fornisce i metodi seguenti per la creazione di una sequenza di elementi da tracciare: <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddRectangle%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddEllipse%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddArc%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddPolygon%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A> (per spline cardinali), e <xref:System.Drawing.Drawing2D.GraphicsPath.AddBezier%2A>.</span><span class="sxs-lookup"><span data-stu-id="e7261-117">The <xref:System.Drawing.Drawing2D.GraphicsPath> class provides the following methods for creating a sequence of items to be drawn: <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddRectangle%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddEllipse%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddArc%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddPolygon%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A> (for cardinal splines), and <xref:System.Drawing.Drawing2D.GraphicsPath.AddBezier%2A>.</span></span> <span data-ttu-id="e7261-118">Ognuno di questi metodi è in overload; ovvero, ogni metodo supporta diversi elenchi di parametri diversi.</span><span class="sxs-lookup"><span data-stu-id="e7261-118">Each of these methods is overloaded; that is, each method supports several different parameter lists.</span></span> <span data-ttu-id="e7261-119">Ad esempio, una variazione del <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> metodo riceve quattro valori integer e un'altra variazione del <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> metodo riceve due <xref:System.Drawing.Point> oggetti.</span><span class="sxs-lookup"><span data-stu-id="e7261-119">For example, one variation of the <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> method receives four integers, and another variation of the <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> method receives two <xref:System.Drawing.Point> objects.</span></span>  
  
 <span data-ttu-id="e7261-120">I metodi per l'aggiunta di linee, rettangoli e spline di Bézier da un percorso sono associati più metodi che aggiungono diversi elementi nel percorso in una singola chiamata: <xref:System.Drawing.Drawing2D.GraphicsPath.AddLines%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddRectangles%2A>, e <xref:System.Drawing.Drawing2D.GraphicsPath.AddBeziers%2A>.</span><span class="sxs-lookup"><span data-stu-id="e7261-120">The methods for adding lines, rectangles, and Bézier splines to a path have plural companion methods that add several items to the path in a single call: <xref:System.Drawing.Drawing2D.GraphicsPath.AddLines%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddRectangles%2A>, and <xref:System.Drawing.Drawing2D.GraphicsPath.AddBeziers%2A>.</span></span> <span data-ttu-id="e7261-121">Inoltre, il <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A> e <xref:System.Drawing.Drawing2D.GraphicsPath.AddArc%2A> metodi sono metodi complementare, <xref:System.Drawing.Drawing2D.GraphicsPath.AddClosedCurve%2A> e <xref:System.Drawing.Drawing2D.GraphicsPath.AddPie%2A>, che consentono di aggiungere una curva o chiusa a torta al percorso.</span><span class="sxs-lookup"><span data-stu-id="e7261-121">Also, the <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A> and <xref:System.Drawing.Drawing2D.GraphicsPath.AddArc%2A> methods have companion methods, <xref:System.Drawing.Drawing2D.GraphicsPath.AddClosedCurve%2A> and <xref:System.Drawing.Drawing2D.GraphicsPath.AddPie%2A>, that add a closed curve or pie to the path.</span></span>  
  
 <span data-ttu-id="e7261-122">Per disegnare un tracciato, è necessario un <xref:System.Drawing.Graphics> oggetto, un <xref:System.Drawing.Pen> , oggetto e un <xref:System.Drawing.Drawing2D.GraphicsPath> oggetto.</span><span class="sxs-lookup"><span data-stu-id="e7261-122">To draw a path, you need a <xref:System.Drawing.Graphics> object, a <xref:System.Drawing.Pen> object, and a <xref:System.Drawing.Drawing2D.GraphicsPath> object.</span></span> <span data-ttu-id="e7261-123">Il <xref:System.Drawing.Graphics> oggetto fornisce il <xref:System.Drawing.Graphics.DrawPath%2A> (metodo) e <xref:System.Drawing.Pen> oggetto archivia gli attributi, ad esempio spessore e colore della linea utilizzata per eseguire il rendering di percorso.</span><span class="sxs-lookup"><span data-stu-id="e7261-123">The <xref:System.Drawing.Graphics> object provides the <xref:System.Drawing.Graphics.DrawPath%2A> method, and the <xref:System.Drawing.Pen> object stores attributes, such as width and color, of the line used to render the path.</span></span> <span data-ttu-id="e7261-124">Il <xref:System.Drawing.Drawing2D.GraphicsPath> oggetto archivia la sequenza di linee e curve che costituiscono il percorso.</span><span class="sxs-lookup"><span data-stu-id="e7261-124">The <xref:System.Drawing.Drawing2D.GraphicsPath> object stores the sequence of lines and curves that make up the path.</span></span> <span data-ttu-id="e7261-125">Il <xref:System.Drawing.Pen> oggetto e <xref:System.Drawing.Drawing2D.GraphicsPath> oggetto vengono passati come argomenti per il <xref:System.Drawing.Graphics.DrawPath%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="e7261-125">The <xref:System.Drawing.Pen> object and the <xref:System.Drawing.Drawing2D.GraphicsPath> object are passed as arguments to the <xref:System.Drawing.Graphics.DrawPath%2A> method.</span></span> <span data-ttu-id="e7261-126">Nell'esempio seguente disegna un percorso che include una riga, di un'ellisse e di una spline di Bézier:</span><span class="sxs-lookup"><span data-stu-id="e7261-126">The following example draws a path that consists of a line, an ellipse, and a Bézier spline:</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#101](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#101)]
 [!code-vb[LinesCurvesAndShapes#101](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#101)]  
  
 <span data-ttu-id="e7261-127">Nella figura seguente mostra il percorso.</span><span class="sxs-lookup"><span data-stu-id="e7261-127">The following illustration shows the path.</span></span>  
  
 <span data-ttu-id="e7261-128">![Percorso](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art15.gif "Aboutgdip02_art15")</span><span class="sxs-lookup"><span data-stu-id="e7261-128">![Path](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art15.gif "Aboutgdip02_art15")</span></span>  
  
 <span data-ttu-id="e7261-129">Oltre ad aggiungere righe, rettangoli e curve a un percorso, è possibile aggiungere i percorsi in un percorso.</span><span class="sxs-lookup"><span data-stu-id="e7261-129">In addition to adding lines, rectangles, and curves to a path, you can add paths to a path.</span></span> <span data-ttu-id="e7261-130">Ciò consente di combinare i percorsi esistenti per creare percorsi lunghi e complessi.</span><span class="sxs-lookup"><span data-stu-id="e7261-130">This allows you to combine existing paths to form large, complex paths.</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#102](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#102)]
 [!code-vb[LinesCurvesAndShapes#102](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#102)]  
  
 <span data-ttu-id="e7261-131">Esistono altri due elementi è possibile aggiungere a un percorso: stringhe e i grafici a torta.</span><span class="sxs-lookup"><span data-stu-id="e7261-131">There are two other items you can add to a path: strings and pies.</span></span> <span data-ttu-id="e7261-132">Un grafico a torta è una parte all'interno di un'ellisse.</span><span class="sxs-lookup"><span data-stu-id="e7261-132">A pie is a portion of the interior of an ellipse.</span></span> <span data-ttu-id="e7261-133">L'esempio seguente crea un percorso da un arco, una spline di tipo cardinal, una stringa e un grafico a torta:</span><span class="sxs-lookup"><span data-stu-id="e7261-133">The following example creates a path from an arc, a cardinal spline, a string, and a pie:</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#103](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#103)]
 [!code-vb[LinesCurvesAndShapes#103](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#103)]  
  
 <span data-ttu-id="e7261-134">Nella figura seguente mostra il percorso.</span><span class="sxs-lookup"><span data-stu-id="e7261-134">The following illustration shows the path.</span></span> <span data-ttu-id="e7261-135">Si noti che un percorso non è necessario essere connessi; l'arco, spline di tipo cardinal, stringa e a torta sono separati.</span><span class="sxs-lookup"><span data-stu-id="e7261-135">Note that a path does not have to be connected; the arc, cardinal spline, string, and pie are separated.</span></span>  
  
 <span data-ttu-id="e7261-136">![Percorsi](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art16.gif "Aboutgdip02_Art16")</span><span class="sxs-lookup"><span data-stu-id="e7261-136">![Paths](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art16.gif "Aboutgdip02_Art16")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7261-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e7261-137">See Also</span></span>  
 <xref:System.Drawing.Drawing2D.GraphicsPath?displayProperty=nameWithType>  
 <xref:System.Drawing.Point?displayProperty=nameWithType>  
 [<span data-ttu-id="e7261-138">Linee, curve e forme</span><span class="sxs-lookup"><span data-stu-id="e7261-138">Lines, Curves, and Shapes</span></span>](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [<span data-ttu-id="e7261-139">Procedura: Creare oggetti Graphics per disegnare</span><span class="sxs-lookup"><span data-stu-id="e7261-139">How to: Create Graphics Objects for Drawing</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)  
 [<span data-ttu-id="e7261-140">Costruzione e creazione di percorsi</span><span class="sxs-lookup"><span data-stu-id="e7261-140">Constructing and Drawing Paths</span></span>](../../../../docs/framework/winforms/advanced/constructing-and-drawing-paths.md)
