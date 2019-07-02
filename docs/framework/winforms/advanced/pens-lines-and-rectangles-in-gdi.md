---
title: Penne, linee e rettangoli in GDI+
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- lines
- GDI+, lines
- drawing [Windows Forms], rectangles
- rectangles
- drawing [Windows Forms], lines
- GDI+, pens
- examples [Windows Forms], drawing lines and shapes
- examples [Windows Forms], pens
- GDI+, rectangles
- examples [Windows Forms], GDI+
- lines [Windows Forms], dashed
ms.assetid: 30b25aae-e3eb-4479-bdb8-187cf651fc84
ms.openlocfilehash: 06d2351ffa7d7f009d7b049f4689df7038b4d202
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/02/2019
ms.locfileid: "67505346"
---
# <a name="pens-lines-and-rectangles-in-gdi"></a><span data-ttu-id="07c43-102">Penne, linee e rettangoli in GDI+</span><span class="sxs-lookup"><span data-stu-id="07c43-102">Pens, Lines, and Rectangles in GDI+</span></span>
<span data-ttu-id="07c43-103">Per disegnare linee con GDI+ è necessario creare un <xref:System.Drawing.Graphics> oggetto e un <xref:System.Drawing.Pen> oggetto.</span><span class="sxs-lookup"><span data-stu-id="07c43-103">To draw lines with GDI+ you need to create a <xref:System.Drawing.Graphics> object and a <xref:System.Drawing.Pen> object.</span></span> <span data-ttu-id="07c43-104">Il <xref:System.Drawing.Graphics> oggetto fornisce i metodi che eseguono effettivamente il disegno, e il <xref:System.Drawing.Pen> oggetto archivia gli attributi, ad esempio colore, larghezza e stile.</span><span class="sxs-lookup"><span data-stu-id="07c43-104">The <xref:System.Drawing.Graphics> object provides the methods that actually do the drawing, and the <xref:System.Drawing.Pen> object stores attributes, such as line color, width, and style.</span></span>  
  
## <a name="drawing-a-line"></a><span data-ttu-id="07c43-105">Creazione di una linea</span><span class="sxs-lookup"><span data-stu-id="07c43-105">Drawing a Line</span></span>  
 <span data-ttu-id="07c43-106">Per disegnare una linea, chiamare il <xref:System.Drawing.Graphics.DrawLine%2A> metodo di <xref:System.Drawing.Graphics> oggetto.</span><span class="sxs-lookup"><span data-stu-id="07c43-106">To draw a line, call the <xref:System.Drawing.Graphics.DrawLine%2A> method of the <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="07c43-107">Il <xref:System.Drawing.Pen> oggetto viene passato come uno degli argomenti per il <xref:System.Drawing.Graphics.DrawLine%2A> (metodo).</span><span class="sxs-lookup"><span data-stu-id="07c43-107">The <xref:System.Drawing.Pen> object is passed as one of the arguments to the <xref:System.Drawing.Graphics.DrawLine%2A> method.</span></span> <span data-ttu-id="07c43-108">Nell'esempio seguente disegna una linea dal punto (4, 2) nel punto (12, 6):</span><span class="sxs-lookup"><span data-stu-id="07c43-108">The following example draws a line from the point (4, 2) to the point (12, 6):</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#41](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#41)]
 [!code-vb[LinesCurvesAndShapes#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#41)]  
  
 <span data-ttu-id="07c43-109"><xref:System.Drawing.Graphics.DrawLine%2A> un metodo di overload di <xref:System.Drawing.Graphics> classe, quindi esistono diversi modi, è possibile fornire argomenti.</span><span class="sxs-lookup"><span data-stu-id="07c43-109"><xref:System.Drawing.Graphics.DrawLine%2A> is an overloaded method of the <xref:System.Drawing.Graphics> class, so there are several ways you can supply it with arguments.</span></span> <span data-ttu-id="07c43-110">Ad esempio, è possibile creare due <xref:System.Drawing.Point> gli oggetti e passare il <xref:System.Drawing.Point> oggetti come argomenti il <xref:System.Drawing.Graphics.DrawLine%2A> (metodo):</span><span class="sxs-lookup"><span data-stu-id="07c43-110">For example, you can construct two <xref:System.Drawing.Point> objects and pass the <xref:System.Drawing.Point> objects as arguments to the <xref:System.Drawing.Graphics.DrawLine%2A> method:</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#42](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#42)]
 [!code-vb[LinesCurvesAndShapes#42](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#42)]  
  
## <a name="constructing-a-pen"></a><span data-ttu-id="07c43-111">Costruzione di un oggetto Pen</span><span class="sxs-lookup"><span data-stu-id="07c43-111">Constructing a Pen</span></span>  
 <span data-ttu-id="07c43-112">È possibile specificare determinati attributi quando si costruisce un <xref:System.Drawing.Pen> oggetto.</span><span class="sxs-lookup"><span data-stu-id="07c43-112">You can specify certain attributes when you construct a <xref:System.Drawing.Pen> object.</span></span> <span data-ttu-id="07c43-113">Ad esempio, uno `Pen` costruttore consente di specificare il colore e larghezza.</span><span class="sxs-lookup"><span data-stu-id="07c43-113">For example, one `Pen` constructor allows you to specify color and width.</span></span> <span data-ttu-id="07c43-114">L'esempio seguente disegna una linea blu della larghezza 2 da (0, 0) a (60, 30):</span><span class="sxs-lookup"><span data-stu-id="07c43-114">The following example draws a blue line of width 2 from (0, 0) to (60, 30):</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#43](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#43)]
 [!code-vb[LinesCurvesAndShapes#43](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#43)]  
  
## <a name="dashed-lines-and-line-caps"></a><span data-ttu-id="07c43-115">Le linee tratteggiate e delimitatori di riga</span><span class="sxs-lookup"><span data-stu-id="07c43-115">Dashed Lines and Line Caps</span></span>  
 <span data-ttu-id="07c43-116">Il <xref:System.Drawing.Pen> oggetto espone anche proprietà, ad esempio <xref:System.Drawing.Pen.DashStyle%2A>, che è possibile usare per specificare le funzionalità della linea.</span><span class="sxs-lookup"><span data-stu-id="07c43-116">The <xref:System.Drawing.Pen> object also exposes properties, such as <xref:System.Drawing.Pen.DashStyle%2A>, that you can use to specify features of the line.</span></span> <span data-ttu-id="07c43-117">L'esempio seguente disegna una linea tratteggiata da (100, 50) a (300, 80):</span><span class="sxs-lookup"><span data-stu-id="07c43-117">The following example draws a dashed line from (100, 50) to (300, 80):</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#44](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#44)]
 [!code-vb[LinesCurvesAndShapes#44](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#44)]  
  
 <span data-ttu-id="07c43-118">È possibile usare le proprietà del <xref:System.Drawing.Pen> oggetto da impostare molti più attributi della linea.</span><span class="sxs-lookup"><span data-stu-id="07c43-118">You can use the properties of the <xref:System.Drawing.Pen> object to set many more attributes of the line.</span></span> <span data-ttu-id="07c43-119">Il <xref:System.Drawing.Pen.StartCap%2A> e <xref:System.Drawing.Pen.EndCap%2A> specificano l'aspetto delle entità finali della linea, le entità finali possono anche essere flat, square, angoli arrotondati, triangolare, o una forma personalizzata.</span><span class="sxs-lookup"><span data-stu-id="07c43-119">The <xref:System.Drawing.Pen.StartCap%2A> and <xref:System.Drawing.Pen.EndCap%2A> properties specify the appearance of the ends of the line; the ends can be flat, square, rounded, triangular, or a custom shape.</span></span> <span data-ttu-id="07c43-120">Il <xref:System.Drawing.Pen.LineJoin%2A> proprietà consente di specificare se linee collegate sono siano (unita in join con angoli acuti), in rilievo, arrotondate o troncate.</span><span class="sxs-lookup"><span data-stu-id="07c43-120">The <xref:System.Drawing.Pen.LineJoin%2A> property lets you specify whether connected lines are mitered (joined with sharp corners), beveled, rounded, or clipped.</span></span> <span data-ttu-id="07c43-121">Nella figura seguente mostra le righe con vari stili di estremità e join.</span><span class="sxs-lookup"><span data-stu-id="07c43-121">The following illustration shows lines with various cap and join styles.</span></span>  
  
 <span data-ttu-id="07c43-122">![Lines](./media/aboutgdip02-art04.gif "Aboutgdip02_art04")</span><span class="sxs-lookup"><span data-stu-id="07c43-122">![Lines](./media/aboutgdip02-art04.gif "Aboutgdip02_art04")</span></span>  
  
## <a name="drawing-a-rectangle"></a><span data-ttu-id="07c43-123">Disegna un rettangolo</span><span class="sxs-lookup"><span data-stu-id="07c43-123">Drawing a Rectangle</span></span>  
 <span data-ttu-id="07c43-124">Disegno di rettangoli in GDI+ è simile al disegno di linee.</span><span class="sxs-lookup"><span data-stu-id="07c43-124">Drawing rectangles with GDI+ is similar to drawing lines.</span></span> <span data-ttu-id="07c43-125">Per disegnare un rettangolo, è necessario un <xref:System.Drawing.Graphics> oggetto e un <xref:System.Drawing.Pen> oggetto.</span><span class="sxs-lookup"><span data-stu-id="07c43-125">To draw a rectangle, you need a <xref:System.Drawing.Graphics> object and a <xref:System.Drawing.Pen> object.</span></span> <span data-ttu-id="07c43-126">Il <xref:System.Drawing.Graphics> oggetto fornisce un <xref:System.Drawing.Graphics.DrawRectangle%2A> metodo e il <xref:System.Drawing.Pen> oggetto archivia gli attributi, ad esempio spessore e colore.</span><span class="sxs-lookup"><span data-stu-id="07c43-126">The <xref:System.Drawing.Graphics> object provides a <xref:System.Drawing.Graphics.DrawRectangle%2A> method, and the <xref:System.Drawing.Pen> object stores attributes, such as line width and color.</span></span> <span data-ttu-id="07c43-127">Il <xref:System.Drawing.Pen> oggetto viene passato come uno degli argomenti per il <xref:System.Drawing.Graphics.DrawRectangle%2A> (metodo).</span><span class="sxs-lookup"><span data-stu-id="07c43-127">The <xref:System.Drawing.Pen> object is passed as one of the arguments to the <xref:System.Drawing.Graphics.DrawRectangle%2A> method.</span></span> <span data-ttu-id="07c43-128">Nell'esempio seguente disegna un rettangolo con relativo angolo superiore sinistro a (100, 50), la larghezza è pari a 80 e l'altezza pari a 40:</span><span class="sxs-lookup"><span data-stu-id="07c43-128">The following example draws a rectangle with its upper-left corner at (100, 50), a width of 80, and a height of 40:</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#45](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#45)]
 [!code-vb[LinesCurvesAndShapes#45](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#45)]  
  
 <span data-ttu-id="07c43-129"><xref:System.Drawing.Graphics.DrawRectangle%2A> un metodo di overload di <xref:System.Drawing.Graphics> classe, quindi esistono diversi modi, è possibile fornire argomenti.</span><span class="sxs-lookup"><span data-stu-id="07c43-129"><xref:System.Drawing.Graphics.DrawRectangle%2A> is an overloaded method of the <xref:System.Drawing.Graphics> class, so there are several ways you can supply it with arguments.</span></span> <span data-ttu-id="07c43-130">Ad esempio, è possibile costruire un <xref:System.Drawing.Rectangle> , quindi passare il <xref:System.Drawing.Rectangle> dell'oggetto al <xref:System.Drawing.Graphics.DrawRectangle%2A> metodo come argomento:</span><span class="sxs-lookup"><span data-stu-id="07c43-130">For example, you can construct a <xref:System.Drawing.Rectangle> object and pass the <xref:System.Drawing.Rectangle> object to the <xref:System.Drawing.Graphics.DrawRectangle%2A> method as an argument:</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#46](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#46)]
 [!code-vb[LinesCurvesAndShapes#46](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#46)]  
  
 <span data-ttu-id="07c43-131">Oggetto <xref:System.Drawing.Rectangle> oggetto dispone di metodi e proprietà per la modifica e la raccolta di informazioni relative al rettangolo.</span><span class="sxs-lookup"><span data-stu-id="07c43-131">A <xref:System.Drawing.Rectangle> object has methods and properties for manipulating and gathering information about the rectangle.</span></span> <span data-ttu-id="07c43-132">Ad esempio, il <xref:System.Drawing.Rectangle.Inflate%2A> e <xref:System.Drawing.Rectangle.Offset%2A> metodi modificano le dimensioni e posizione del rettangolo.</span><span class="sxs-lookup"><span data-stu-id="07c43-132">For example, the <xref:System.Drawing.Rectangle.Inflate%2A> and <xref:System.Drawing.Rectangle.Offset%2A> methods change the size and position of the rectangle.</span></span> <span data-ttu-id="07c43-133">Il <xref:System.Drawing.Rectangle.IntersectsWith%2A> metodo indica se il rettangolo interseca un altro rettangolo specificato e il <xref:System.Drawing.Rectangle.Contains%2A> metodo indica se un determinato punto è all'interno del rettangolo.</span><span class="sxs-lookup"><span data-stu-id="07c43-133">The <xref:System.Drawing.Rectangle.IntersectsWith%2A> method tells you whether the rectangle intersects another given rectangle, and the <xref:System.Drawing.Rectangle.Contains%2A> method tells you whether a given point is inside the rectangle.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07c43-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="07c43-134">See also</span></span>

- <xref:System.Drawing.Graphics?displayProperty=nameWithType>
- <xref:System.Drawing.Pen?displayProperty=nameWithType>
- <xref:System.Drawing.Rectangle?displayProperty=nameWithType>
- [<span data-ttu-id="07c43-135">Procedura: Creare un oggetto Pen</span><span class="sxs-lookup"><span data-stu-id="07c43-135">How to: Create a Pen</span></span>](how-to-create-a-pen.md)
- [<span data-ttu-id="07c43-136">Procedura: Disegnare una linea in un Windows Form</span><span class="sxs-lookup"><span data-stu-id="07c43-136">How to: Draw a Line on a Windows Form</span></span>](how-to-draw-a-line-on-a-windows-form.md)
- [<span data-ttu-id="07c43-137">Procedura: Disegnare una forma con contorno</span><span class="sxs-lookup"><span data-stu-id="07c43-137">How to: Draw an Outlined Shape</span></span>](how-to-draw-an-outlined-shape.md)
