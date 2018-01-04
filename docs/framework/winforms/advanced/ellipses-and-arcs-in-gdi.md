---
title: Ellissi e archi in GDI+
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
- arcs
- GDI+, arcs
- drawing [Windows Forms], ellipses
- GDI+, ellipses
- ellipses
- drawing [Windows Forms], arcs
ms.assetid: 34f35133-a835-4ca4-81f6-0dfedee8b683
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 71126942f4cde37cc5d26bfba029c5f50f1065a3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ellipses-and-arcs-in-gdi"></a><span data-ttu-id="da501-102">Ellissi e archi in GDI+</span><span class="sxs-lookup"><span data-stu-id="da501-102">Ellipses and Arcs in GDI+</span></span>
<span data-ttu-id="da501-103">È possibile tracciare ellissi e archi utilizzando il <xref:System.Drawing.Graphics.DrawEllipse%2A> e <xref:System.Drawing.Graphics.DrawArc%2A> metodi di <xref:System.Drawing.Graphics> classe.</span><span class="sxs-lookup"><span data-stu-id="da501-103">You can easily draw ellipses and arcs using the <xref:System.Drawing.Graphics.DrawEllipse%2A> and <xref:System.Drawing.Graphics.DrawArc%2A> methods of the <xref:System.Drawing.Graphics> class.</span></span>  
  
## <a name="drawing-an-ellipse"></a><span data-ttu-id="da501-104">Disegnare un'ellisse</span><span class="sxs-lookup"><span data-stu-id="da501-104">Drawing an Ellipse</span></span>  
 <span data-ttu-id="da501-105">Per disegnare un'ellisse, è necessario un <xref:System.Drawing.Graphics> oggetto e un <xref:System.Drawing.Pen> oggetto.</span><span class="sxs-lookup"><span data-stu-id="da501-105">To draw an ellipse, you need a <xref:System.Drawing.Graphics> object and a <xref:System.Drawing.Pen> object.</span></span> <span data-ttu-id="da501-106">Il <xref:System.Drawing.Graphics> oggetto fornisce il <xref:System.Drawing.Graphics.DrawEllipse%2A> (metodo) e <xref:System.Drawing.Pen> oggetto archivia gli attributi, ad esempio spessore e colore della linea utilizzata per eseguire il rendering dell'ellisse.</span><span class="sxs-lookup"><span data-stu-id="da501-106">The <xref:System.Drawing.Graphics> object provides the <xref:System.Drawing.Graphics.DrawEllipse%2A> method, and the <xref:System.Drawing.Pen> object stores attributes, such as width and color, of the line used to render the ellipse.</span></span> <span data-ttu-id="da501-107">Il <xref:System.Drawing.Pen> oggetto viene passato come uno degli argomenti per il <xref:System.Drawing.Graphics.DrawEllipse%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="da501-107">The <xref:System.Drawing.Pen> object is passed as one of the arguments to the <xref:System.Drawing.Graphics.DrawEllipse%2A> method.</span></span> <span data-ttu-id="da501-108">Gli argomenti rimanenti passati il <xref:System.Drawing.Graphics.DrawEllipse%2A> metodo specificare il rettangolo di delimitazione dell'ellisse.</span><span class="sxs-lookup"><span data-stu-id="da501-108">The remaining arguments passed to the <xref:System.Drawing.Graphics.DrawEllipse%2A> method specify the bounding rectangle for the ellipse.</span></span> <span data-ttu-id="da501-109">Nella figura seguente mostra un'ellisse con rettangolo di delimitazione.</span><span class="sxs-lookup"><span data-stu-id="da501-109">The following illustration shows an ellipse along with its bounding rectangle.</span></span>  
  
 <span data-ttu-id="da501-110">![Ellissi e archi](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art05.gif "Aboutgdip02_art05")</span><span class="sxs-lookup"><span data-stu-id="da501-110">![Ellipses and arcs](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art05.gif "Aboutgdip02_art05")</span></span>  
  
 <span data-ttu-id="da501-111">Nell'esempio seguente disegna un'ellisse. il rettangolo di delimitazione ha una larghezza pari a 80, un'altezza pari a 40 e un angolo superiore sinistro di (100, 50):</span><span class="sxs-lookup"><span data-stu-id="da501-111">The following example draws an ellipse; the bounding rectangle has a width of 80, a height of 40, and an upper-left corner of (100, 50):</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#51](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#51)]
 [!code-vb[LinesCurvesAndShapes#51](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#51)]  
  
 <span data-ttu-id="da501-112"><xref:System.Drawing.Graphics.DrawEllipse%2A>un metodo di overload di <xref:System.Drawing.Graphics> classe, pertanto vi sono diversi modi, è possibile fornire argomenti.</span><span class="sxs-lookup"><span data-stu-id="da501-112"><xref:System.Drawing.Graphics.DrawEllipse%2A> is an overloaded method of the <xref:System.Drawing.Graphics> class, so there are several ways you can supply it with arguments.</span></span> <span data-ttu-id="da501-113">Ad esempio, è possibile costruire un <xref:System.Drawing.Rectangle> e passare il <xref:System.Drawing.Rectangle> per il <xref:System.Drawing.Graphics.DrawEllipse%2A> metodo come argomento:</span><span class="sxs-lookup"><span data-stu-id="da501-113">For example, you can construct a <xref:System.Drawing.Rectangle> and pass the <xref:System.Drawing.Rectangle> to the <xref:System.Drawing.Graphics.DrawEllipse%2A> method as an argument:</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#52](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#52)]
 [!code-vb[LinesCurvesAndShapes#52](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#52)]  
  
## <a name="drawing-an-arc"></a><span data-ttu-id="da501-114">Disegno di un arco</span><span class="sxs-lookup"><span data-stu-id="da501-114">Drawing an Arc</span></span>  
 <span data-ttu-id="da501-115">Un arco è una parte di un'ellisse.</span><span class="sxs-lookup"><span data-stu-id="da501-115">An arc is a portion of an ellipse.</span></span> <span data-ttu-id="da501-116">Per disegnare l'arco, si chiama il <xref:System.Drawing.Graphics.DrawArc%2A> metodo la <xref:System.Drawing.Graphics> classe.</span><span class="sxs-lookup"><span data-stu-id="da501-116">To draw an arc, you call the <xref:System.Drawing.Graphics.DrawArc%2A> method of the <xref:System.Drawing.Graphics> class.</span></span> <span data-ttu-id="da501-117">I parametri del <xref:System.Drawing.Graphics.DrawArc%2A> metodo sono gli stessi parametri del <xref:System.Drawing.Graphics.DrawEllipse%2A> (metodo), con la differenza che <xref:System.Drawing.Graphics.DrawArc%2A> richiede un angolo iniziale e angolo di apertura.</span><span class="sxs-lookup"><span data-stu-id="da501-117">The parameters of the <xref:System.Drawing.Graphics.DrawArc%2A> method are the same as the parameters of the <xref:System.Drawing.Graphics.DrawEllipse%2A> method, except that <xref:System.Drawing.Graphics.DrawArc%2A> requires a starting angle and sweep angle.</span></span> <span data-ttu-id="da501-118">Nell'esempio seguente disegna un arco con un angolo iniziale di 30 gradi e un angolo di apertura di 180 gradi:</span><span class="sxs-lookup"><span data-stu-id="da501-118">The following example draws an arc with a starting angle of 30 degrees and a sweep angle of 180 degrees:</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#53](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#53)]
 [!code-vb[LinesCurvesAndShapes#53](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#53)]  
  
 <span data-ttu-id="da501-119">Nella figura seguente mostra l'arco, i puntini di sospensione e il rettangolo di delimitazione.</span><span class="sxs-lookup"><span data-stu-id="da501-119">The following illustration shows the arc, the ellipse, and the bounding rectangle.</span></span>  
  
 <span data-ttu-id="da501-120">![Ellissi e archi](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art06.gif "Aboutgdip02_art06")</span><span class="sxs-lookup"><span data-stu-id="da501-120">![Ellipses and arcs](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art06.gif "Aboutgdip02_art06")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da501-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="da501-121">See Also</span></span>  
 <xref:System.Drawing.Graphics?displayProperty=nameWithType>  
 <xref:System.Drawing.Pen?displayProperty=nameWithType>  
 [<span data-ttu-id="da501-122">Linee, curve e forme</span><span class="sxs-lookup"><span data-stu-id="da501-122">Lines, Curves, and Shapes</span></span>](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [<span data-ttu-id="da501-123">Procedura: Creare oggetti Graphics per disegnare</span><span class="sxs-lookup"><span data-stu-id="da501-123">How to: Create Graphics Objects for Drawing</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)  
 [<span data-ttu-id="da501-124">Procedura: Creare un oggetto Pen</span><span class="sxs-lookup"><span data-stu-id="da501-124">How to: Create a Pen</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-a-pen.md)  
 [<span data-ttu-id="da501-125">Procedura: Creare una forma con contorno</span><span class="sxs-lookup"><span data-stu-id="da501-125">How to: Draw an Outlined Shape</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-an-outlined-shape.md)
