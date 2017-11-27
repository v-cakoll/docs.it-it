---
title: Curve aperte e chiuse in GDI+
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
- curves [Windows Forms], filling
- GDI+, curves
- curves [Windows Forms], drawing
- curves
ms.assetid: 08d2cc9a-dc9d-4eed-bcbb-2c8e2ca5d3ae
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 14da32848978299a0d0651596bbfbfe17c2e0d53
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="open-and-closed-curves-in-gdi"></a><span data-ttu-id="c0926-102">Curve aperte e chiuse in GDI+</span><span class="sxs-lookup"><span data-stu-id="c0926-102">Open and Closed Curves in GDI+</span></span>
<span data-ttu-id="c0926-103">La figura seguente mostra due curve: una aperta e una chiusa.</span><span class="sxs-lookup"><span data-stu-id="c0926-103">The following illustration shows two curves: one open and one closed.</span></span>  
  
 <span data-ttu-id="c0926-104">![Curve aperte e chiuse](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art24.gif "Aboutgdip02_art24")</span><span class="sxs-lookup"><span data-stu-id="c0926-104">![Open & Closed curves](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art24.gif "Aboutgdip02_art24")</span></span>  
  
## <a name="managed-interface-for-curves"></a><span data-ttu-id="c0926-105">Interfaccia gestita per curve</span><span class="sxs-lookup"><span data-stu-id="c0926-105">Managed Interface for Curves</span></span>  
 <span data-ttu-id="c0926-106">Curve chiuse sono una parte interna e possono pertanto essere riempite con un pennello.</span><span class="sxs-lookup"><span data-stu-id="c0926-106">Closed curves have an interior and therefore can be filled with a brush.</span></span> <span data-ttu-id="c0926-107">Il <xref:System.Drawing.Graphics> classe [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] fornisce i metodi seguenti per il riempimento di forme e curve chiuse: <xref:System.Drawing.Graphics.FillRectangle%2A>, <xref:System.Drawing.Graphics.FillEllipse%2A>, <xref:System.Drawing.Graphics.FillPie%2A>, <xref:System.Drawing.Graphics.FillPolygon%2A>, <xref:System.Drawing.Graphics.FillClosedCurve%2A>, <xref:System.Drawing.Graphics.FillPath%2A>, e <xref:System.Drawing.Graphics.FillRegion%2A>.</span><span class="sxs-lookup"><span data-stu-id="c0926-107">The <xref:System.Drawing.Graphics> class in [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] provides the following methods for filling closed shapes and curves: <xref:System.Drawing.Graphics.FillRectangle%2A>, <xref:System.Drawing.Graphics.FillEllipse%2A>, <xref:System.Drawing.Graphics.FillPie%2A>, <xref:System.Drawing.Graphics.FillPolygon%2A>, <xref:System.Drawing.Graphics.FillClosedCurve%2A>, <xref:System.Drawing.Graphics.FillPath%2A>, and <xref:System.Drawing.Graphics.FillRegion%2A>.</span></span> <span data-ttu-id="c0926-108">Quando si chiama uno di questi metodi, è necessario passare uno dei tipi di pennello specifico (<xref:System.Drawing.SolidBrush>, <xref:System.Drawing.Drawing2D.HatchBrush>, <xref:System.Drawing.TextureBrush>, <xref:System.Drawing.Drawing2D.LinearGradientBrush>, o <xref:System.Drawing.Drawing2D.PathGradientBrush>) come argomento.</span><span class="sxs-lookup"><span data-stu-id="c0926-108">Whenever you call one of these methods, you must pass one of the specific brush types (<xref:System.Drawing.SolidBrush>, <xref:System.Drawing.Drawing2D.HatchBrush>, <xref:System.Drawing.TextureBrush>, <xref:System.Drawing.Drawing2D.LinearGradientBrush>, or <xref:System.Drawing.Drawing2D.PathGradientBrush>) as an argument.</span></span>  
  
 <span data-ttu-id="c0926-109">Il <xref:System.Drawing.Graphics.FillPie%2A> metodo è correlato al <xref:System.Drawing.Graphics.DrawArc%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="c0926-109">The <xref:System.Drawing.Graphics.FillPie%2A> method is a companion to the <xref:System.Drawing.Graphics.DrawArc%2A> method.</span></span> <span data-ttu-id="c0926-110">Come il <xref:System.Drawing.Graphics.DrawArc%2A> metodo disegna una parte della struttura di un'ellisse, il <xref:System.Drawing.Graphics.FillPie%2A> metodo compila una parte all'interno di un'ellisse.</span><span class="sxs-lookup"><span data-stu-id="c0926-110">Just as the <xref:System.Drawing.Graphics.DrawArc%2A> method draws a portion of the outline of an ellipse, the <xref:System.Drawing.Graphics.FillPie%2A> method fills a portion of the interior of an ellipse.</span></span> <span data-ttu-id="c0926-111">Nell'esempio seguente disegna un arco e riempie la parte corrispondente all'interno dell'ellisse:</span><span class="sxs-lookup"><span data-stu-id="c0926-111">The following example draws an arc and fills the corresponding portion of the interior of the ellipse:</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#21)]
 [!code-vb[LinesCurvesAndShapes#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#21)]  
  
 <span data-ttu-id="c0926-112">Nella figura seguente mostra l'arco e torta piena.</span><span class="sxs-lookup"><span data-stu-id="c0926-112">The following illustration shows the arc and the filled pie.</span></span>  
  
 <span data-ttu-id="c0926-113">![Curve aperte e chiuse](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art25.gif "Aboutgdip02_art25")</span><span class="sxs-lookup"><span data-stu-id="c0926-113">![Open & Closed curves](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art25.gif "Aboutgdip02_art25")</span></span>  
  
 <span data-ttu-id="c0926-114">Il <xref:System.Drawing.Graphics.FillClosedCurve%2A> metodo è correlato al <xref:System.Drawing.Graphics.DrawClosedCurve%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="c0926-114">The <xref:System.Drawing.Graphics.FillClosedCurve%2A> method is a companion to the <xref:System.Drawing.Graphics.DrawClosedCurve%2A> method.</span></span> <span data-ttu-id="c0926-115">Entrambi i metodi di chiudono automaticamente la curva tramite la connessione al punto finale al punto di partenza.</span><span class="sxs-lookup"><span data-stu-id="c0926-115">Both methods automatically close the curve by connecting the ending point to the starting point.</span></span> <span data-ttu-id="c0926-116">Nell'esempio seguente viene tracciata una curva passante (0, 0), (60, 20) e (40, 50).</span><span class="sxs-lookup"><span data-stu-id="c0926-116">The following example draws a curve that passes through (0, 0), (60, 20), and (40, 50).</span></span> <span data-ttu-id="c0926-117">Quindi, la curva viene chiuso automaticamente tramite la connessione (40, 50) al punto di partenza (0, 0), e l'interno viene riempito con un colore a tinta unita.</span><span class="sxs-lookup"><span data-stu-id="c0926-117">Then, the curve is automatically closed by connecting (40, 50) to the starting point (0, 0), and the interior is filled with a solid color.</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#22](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#22)]
 [!code-vb[LinesCurvesAndShapes#22](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#22)]  
  
 <span data-ttu-id="c0926-118">Il <xref:System.Drawing.Graphics.FillPath%2A> metodo riempie l'area interna di pezzi di percorso separati.</span><span class="sxs-lookup"><span data-stu-id="c0926-118">The <xref:System.Drawing.Graphics.FillPath%2A> method fills the interiors of the separate pieces of a path.</span></span> <span data-ttu-id="c0926-119">Se una parte di un percorso non costituisce una curva chiusa o una forma, il <xref:System.Drawing.Graphics.FillPath%2A> metodo chiude automaticamente tale parte del percorso prima dell'inserimento.</span><span class="sxs-lookup"><span data-stu-id="c0926-119">If a piece of a path doesn't form a closed curve or shape, the <xref:System.Drawing.Graphics.FillPath%2A> method automatically closes that piece of the path before filling it.</span></span> <span data-ttu-id="c0926-120">Nell'esempio seguente disegna e riempie un percorso costituito da un arco, una spline di tipo cardinal, una stringa e un grafico a torta:</span><span class="sxs-lookup"><span data-stu-id="c0926-120">The following example draws and fills a path that consists of an arc, a cardinal spline, a string, and a pie:</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#23](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#23)]
 [!code-vb[LinesCurvesAndShapes#23](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#23)]  
  
 <span data-ttu-id="c0926-121">Nella figura seguente mostra il percorso con e senza riempimento a tinta unita.</span><span class="sxs-lookup"><span data-stu-id="c0926-121">The following illustration shows the path with and without the solid fill.</span></span> <span data-ttu-id="c0926-122">Nota che il testo nella stringa di è descritta, ma non è compilato, per il <xref:System.Drawing.Graphics.DrawPath%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="c0926-122">Note that the text in the string is outlined, but not filled, by the <xref:System.Drawing.Graphics.DrawPath%2A> method.</span></span> <span data-ttu-id="c0926-123">È il <xref:System.Drawing.Graphics.FillPath%2A> metodo riempire i caratteri nella stringa.</span><span class="sxs-lookup"><span data-stu-id="c0926-123">It is the <xref:System.Drawing.Graphics.FillPath%2A> method that paints the interiors of the characters in the string.</span></span>  
  
 <span data-ttu-id="c0926-124">![Stringa in un percorso](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art26.gif "Aboutgdip02_art26")</span><span class="sxs-lookup"><span data-stu-id="c0926-124">![String in a path](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art26.gif "Aboutgdip02_art26")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0926-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c0926-125">See Also</span></span>  
 <xref:System.Drawing.Drawing2D.GraphicsPath?displayProperty=nameWithType>  
 <xref:System.Drawing.Pen?displayProperty=nameWithType>  
 <xref:System.Drawing.Point?displayProperty=nameWithType>  
 [<span data-ttu-id="c0926-126">Linee, curve e forme</span><span class="sxs-lookup"><span data-stu-id="c0926-126">Lines, Curves, and Shapes</span></span>](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [<span data-ttu-id="c0926-127">Procedura: Creare oggetti Graphics per disegnare</span><span class="sxs-lookup"><span data-stu-id="c0926-127">How to: Create Graphics Objects for Drawing</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)  
 [<span data-ttu-id="c0926-128">Costruzione e creazione di percorsi</span><span class="sxs-lookup"><span data-stu-id="c0926-128">Constructing and Drawing Paths</span></span>](../../../../docs/framework/winforms/advanced/constructing-and-drawing-paths.md)
