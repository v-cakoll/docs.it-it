---
title: Pennelli e forme con riempimento in GDI+
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- brushes [Windows Forms], GDI+
- filled shapes [Windows Forms], GDI+
- shapes [Windows Forms], GDI+
- GDI+, brushes
- GDI+, filled shapes
- gradient brushes
- brushes [Windows Forms], gradient
ms.assetid: e863e2a7-0294-4130-99b6-f1ea3201e7cd
ms.openlocfilehash: 9475518a5f0422e0eac1ec521088071bb4d1c885
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33518997"
---
# <a name="brushes-and-filled-shapes-in-gdi"></a><span data-ttu-id="3899e-102">Pennelli e forme con riempimento in GDI+</span><span class="sxs-lookup"><span data-stu-id="3899e-102">Brushes and Filled Shapes in GDI+</span></span>
<span data-ttu-id="3899e-103">Una forma chiusa, ad esempio un rettangolo o un'ellisse, è costituito da una struttura e una parte interna.</span><span class="sxs-lookup"><span data-stu-id="3899e-103">A closed shape, such as a rectangle or an ellipse, consists of an outline and an interior.</span></span> <span data-ttu-id="3899e-104">La struttura viene disegnata con una penna e l'interno viene riempito con un pennello.</span><span class="sxs-lookup"><span data-stu-id="3899e-104">The outline is drawn with a pen and the interior is filled with a brush.</span></span> [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="3899e-105"> fornisce diverse classi di pennelli per il riempimento di forme chiuse: <xref:System.Drawing.SolidBrush>, <xref:System.Drawing.Drawing2D.HatchBrush>, <xref:System.Drawing.TextureBrush>, <xref:System.Drawing.Drawing2D.LinearGradientBrush>, e <xref:System.Drawing.Drawing2D.PathGradientBrush>.</span><span class="sxs-lookup"><span data-stu-id="3899e-105"> provides several brush classes for filling the interiors of closed shapes: <xref:System.Drawing.SolidBrush>, <xref:System.Drawing.Drawing2D.HatchBrush>, <xref:System.Drawing.TextureBrush>, <xref:System.Drawing.Drawing2D.LinearGradientBrush>, and <xref:System.Drawing.Drawing2D.PathGradientBrush>.</span></span> <span data-ttu-id="3899e-106">Tutte queste classi di ereditare il <xref:System.Drawing.Brush> classe.</span><span class="sxs-lookup"><span data-stu-id="3899e-106">All of these classes inherit from the <xref:System.Drawing.Brush> class.</span></span> <span data-ttu-id="3899e-107">Nella figura seguente viene illustrato un rettangolo riempito con un pennello tinta unita e un'ellisse riempita con un pennello di tratteggio.</span><span class="sxs-lookup"><span data-stu-id="3899e-107">The following illustration shows a rectangle filled with a solid brush and an ellipse filled with a hatch brush.</span></span>  
  
 <span data-ttu-id="3899e-108">![Forme piene](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art17.gif "Aboutgdip02_art17")</span><span class="sxs-lookup"><span data-stu-id="3899e-108">![Filled Shapes](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art17.gif "Aboutgdip02_art17")</span></span>  
  
## <a name="solid-brushes"></a><span data-ttu-id="3899e-109">Pennelli tinta unite</span><span class="sxs-lookup"><span data-stu-id="3899e-109">Solid Brushes</span></span>  
 <span data-ttu-id="3899e-110">Per riempire una forma chiusa, sono necessari un'istanza di <xref:System.Drawing.Graphics> classe e un <xref:System.Drawing.Brush>.</span><span class="sxs-lookup"><span data-stu-id="3899e-110">To fill a closed shape, you need an instance of the <xref:System.Drawing.Graphics> class and a <xref:System.Drawing.Brush>.</span></span> <span data-ttu-id="3899e-111">L'istanza del <xref:System.Drawing.Graphics> classe fornisce i metodi, ad esempio <xref:System.Drawing.Graphics.FillRectangle%2A> e <xref:System.Drawing.Graphics.FillEllipse%2A>e <xref:System.Drawing.Brush> archivia gli attributi del riempimento, ad esempio colore e il motivo.</span><span class="sxs-lookup"><span data-stu-id="3899e-111">The instance of the <xref:System.Drawing.Graphics> class provides methods, such as <xref:System.Drawing.Graphics.FillRectangle%2A> and <xref:System.Drawing.Graphics.FillEllipse%2A>, and the <xref:System.Drawing.Brush> stores attributes of the fill, such as color and pattern.</span></span> <span data-ttu-id="3899e-112">Il <xref:System.Drawing.Brush> viene passato come uno degli argomenti al metodo di riempimento.</span><span class="sxs-lookup"><span data-stu-id="3899e-112">The <xref:System.Drawing.Brush> is passed as one of the arguments to the fill method.</span></span> <span data-ttu-id="3899e-113">Esempio di codice seguente viene illustrato come compilare un'ellisse con un colore rosso.</span><span class="sxs-lookup"><span data-stu-id="3899e-113">The following code example shows how to fill an ellipse with a solid red color.</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#121](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#121)]
 [!code-vb[LinesCurvesAndShapes#121](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#121)]  
  
> [!NOTE]
>  <span data-ttu-id="3899e-114">Nell'esempio precedente, il pennello è di tipo <xref:System.Drawing.SolidBrush>, che eredita da <xref:System.Drawing.Brush>.</span><span class="sxs-lookup"><span data-stu-id="3899e-114">In the preceding example, the brush is of type <xref:System.Drawing.SolidBrush>, which inherits from <xref:System.Drawing.Brush>.</span></span>  
  
## <a name="hatch-brushes"></a><span data-ttu-id="3899e-115">Pennelli per il tratteggio</span><span class="sxs-lookup"><span data-stu-id="3899e-115">Hatch Brushes</span></span>  
 <span data-ttu-id="3899e-116">Quando si riempie una forma con un pennello tratteggiato, specificare un colore di primo piano, un colore di sfondo e uno stile di tratteggio.</span><span class="sxs-lookup"><span data-stu-id="3899e-116">When you fill a shape with a hatch brush, you specify a foreground color, a background color, and a hatch style.</span></span> <span data-ttu-id="3899e-117">Il colore primo piano è il colore del tratteggio.</span><span class="sxs-lookup"><span data-stu-id="3899e-117">The foreground color is the color of the hatching.</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#122](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#122)]
 [!code-vb[LinesCurvesAndShapes#122](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#122)]  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="3899e-118"> sono disponibili più di 50 stili di tratteggio. i tre stili mostrati nella figura seguente vengono <xref:System.Drawing.Drawing2D.HatchStyle.Horizontal>, <xref:System.Drawing.Drawing2D.HatchStyle.ForwardDiagonal>, e <xref:System.Drawing.Drawing2D.HatchStyle.Cross>.</span><span class="sxs-lookup"><span data-stu-id="3899e-118"> provides more than 50 hatch styles; the three styles shown in the following illustration are <xref:System.Drawing.Drawing2D.HatchStyle.Horizontal>, <xref:System.Drawing.Drawing2D.HatchStyle.ForwardDiagonal>, and <xref:System.Drawing.Drawing2D.HatchStyle.Cross>.</span></span>  
  
 <span data-ttu-id="3899e-119">![Forme piene](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art18.gif "Aboutgdip02_art18")</span><span class="sxs-lookup"><span data-stu-id="3899e-119">![Filled Shapes](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art18.gif "Aboutgdip02_art18")</span></span>  
  
## <a name="texture-brushes"></a><span data-ttu-id="3899e-120">Pennelli della struttura</span><span class="sxs-lookup"><span data-stu-id="3899e-120">Texture Brushes</span></span>  
 <span data-ttu-id="3899e-121">Con un pennello di trama, è possibile riempire una forma con un modello archiviato in una bitmap.</span><span class="sxs-lookup"><span data-stu-id="3899e-121">With a texture brush, you can fill a shape with a pattern stored in a bitmap.</span></span> <span data-ttu-id="3899e-122">Ad esempio, si supponga che l'immagine seguente è memorizzata in un file di disco denominato `MyTexture.bmp`.</span><span class="sxs-lookup"><span data-stu-id="3899e-122">For example, suppose the following picture is stored in a disk file named `MyTexture.bmp`.</span></span>  
  
 <span data-ttu-id="3899e-123">![Riempito forma](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art19.gif "Aboutgdip02_Art19")</span><span class="sxs-lookup"><span data-stu-id="3899e-123">![Filled Shape](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art19.gif "Aboutgdip02_Art19")</span></span>  
  
 <span data-ttu-id="3899e-124">Esempio di codice seguente viene illustrato come compilare un'ellisse ripetendo l'immagine memorizzata in `MyTexture.bmp`.</span><span class="sxs-lookup"><span data-stu-id="3899e-124">The following code example shows how to fill an ellipse by repeating the picture stored in `MyTexture.bmp`.</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#123](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#123)]
 [!code-vb[LinesCurvesAndShapes#123](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#123)]  
  
 <span data-ttu-id="3899e-125">Nella figura seguente mostra l'ellisse piena.</span><span class="sxs-lookup"><span data-stu-id="3899e-125">The following illustration shows the filled ellipse.</span></span>  
  
 <span data-ttu-id="3899e-126">![Riempito forma](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art20.gif "AboutGdip02_Art20")</span><span class="sxs-lookup"><span data-stu-id="3899e-126">![Filled Shape](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art20.gif "AboutGdip02_Art20")</span></span>  
  
## <a name="gradient-brushes"></a><span data-ttu-id="3899e-127">Pennelli per sfumature</span><span class="sxs-lookup"><span data-stu-id="3899e-127">Gradient Brushes</span></span>  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="3899e-128"> sono disponibili due tipi di pennelli per sfumature: lineare e il percorso.</span><span class="sxs-lookup"><span data-stu-id="3899e-128"> provides two kinds of gradient brushes: linear and path.</span></span> <span data-ttu-id="3899e-129">È possibile utilizzare un pennello sfumato lineare per riempire una forma con colore che cambia gradualmente mentre si sposta lungo la forma orizzontalmente, verticalmente o in diagonale.</span><span class="sxs-lookup"><span data-stu-id="3899e-129">You can use a linear gradient brush to fill a shape with color that changes gradually as you move across the shape horizontally, vertically, or diagonally.</span></span> <span data-ttu-id="3899e-130">Esempio di codice seguente viene illustrato come compilare un'ellisse con un pennello sfumato orizzontale che passa da blu a verde si sposta dal bordo sinistro dell'ellisse al bordo destro.</span><span class="sxs-lookup"><span data-stu-id="3899e-130">The following code example shows how to fill an ellipse with a horizontal gradient brush that changes from blue to green as you move from the left edge of the ellipse to the right edge.</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#124](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#124)]
 [!code-vb[LinesCurvesAndShapes#124](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#124)]  
  
 <span data-ttu-id="3899e-131">Nella figura seguente mostra l'ellisse piena.</span><span class="sxs-lookup"><span data-stu-id="3899e-131">The following illustration shows the filled ellipse.</span></span>  
  
 <span data-ttu-id="3899e-132">![Riempito forma](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art21.gif "AboutGdip02_Art21")</span><span class="sxs-lookup"><span data-stu-id="3899e-132">![Filled Shape](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art21.gif "AboutGdip02_Art21")</span></span>  
  
 <span data-ttu-id="3899e-133">Pennello sfumatura percorso può essere configurato per cambiare colore quando si sposta dal centro della forma verso il bordo.</span><span class="sxs-lookup"><span data-stu-id="3899e-133">A path gradient brush can be configured to change color as you move from the center of a shape toward the edge.</span></span>  
  
 <span data-ttu-id="3899e-134">![Riempito forma](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art22.gif "AboutGdip02_Art22")</span><span class="sxs-lookup"><span data-stu-id="3899e-134">![Filled Shape](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art22.gif "AboutGdip02_Art22")</span></span>  
  
 <span data-ttu-id="3899e-135">Pennelli per sfumature di percorso sono molto flessibile.</span><span class="sxs-lookup"><span data-stu-id="3899e-135">Path gradient brushes are quite flexible.</span></span> <span data-ttu-id="3899e-136">Il pennello sfumato usato per riempire il triangolo le seguenti modifiche di illustrazione gradualmente dal colore rosso del centro per ognuno dei tre colori diversi per i vertici.</span><span class="sxs-lookup"><span data-stu-id="3899e-136">The gradient brush used to fill the triangle in the following illustration changes gradually from red at the center to each of three different colors at the vertices.</span></span>  
  
 <span data-ttu-id="3899e-137">![Riempito forma](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art23.gif "AboutGdip02_Art23")</span><span class="sxs-lookup"><span data-stu-id="3899e-137">![Filled Shape](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art23.gif "AboutGdip02_Art23")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3899e-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3899e-138">See Also</span></span>  
 <xref:System.Drawing.SolidBrush?displayProperty=nameWithType>  
 <xref:System.Drawing.Drawing2D.HatchBrush?displayProperty=nameWithType>  
 <xref:System.Drawing.TextureBrush?displayProperty=nameWithType>  
 <xref:System.Drawing.Drawing2D.LinearGradientBrush?displayProperty=nameWithType>  
 [<span data-ttu-id="3899e-139">Linee, curve e forme</span><span class="sxs-lookup"><span data-stu-id="3899e-139">Lines, Curves, and Shapes</span></span>](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [<span data-ttu-id="3899e-140">Procedura: Disegnare un rettangolo con riempimento in un Windows Form</span><span class="sxs-lookup"><span data-stu-id="3899e-140">How to: Draw a Filled Rectangle on a Windows Form</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-a-filled-rectangle-on-a-windows-form.md)  
 [<span data-ttu-id="3899e-141">Procedura: Disegnare un'ellisse con riempimento in un Windows Form</span><span class="sxs-lookup"><span data-stu-id="3899e-141">How to: Draw a Filled Ellipse on a Windows Form</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-a-filled-ellipse-on-a-windows-form.md)
