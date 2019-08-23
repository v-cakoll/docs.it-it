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
ms.openlocfilehash: 45ef0b5920e43300e047d363149ea10a7833477b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69912225"
---
# <a name="brushes-and-filled-shapes-in-gdi"></a><span data-ttu-id="bf3cd-102">Pennelli e forme con riempimento in GDI+</span><span class="sxs-lookup"><span data-stu-id="bf3cd-102">Brushes and Filled Shapes in GDI+</span></span>
<span data-ttu-id="bf3cd-103">Una forma chiusa, ad esempio un rettangolo o un'ellisse, è costituita da un contorno e da una parte interna.</span><span class="sxs-lookup"><span data-stu-id="bf3cd-103">A closed shape, such as a rectangle or an ellipse, consists of an outline and an interior.</span></span> <span data-ttu-id="bf3cd-104">Il contorno viene disegnato con una penna e l'interno è riempito da un pennello.</span><span class="sxs-lookup"><span data-stu-id="bf3cd-104">The outline is drawn with a pen and the interior is filled with a brush.</span></span> <span data-ttu-id="bf3cd-105">In GDI+ sono disponibili diverse classi di pennelli per riempire le parti <xref:System.Drawing.SolidBrush>interne <xref:System.Drawing.Drawing2D.HatchBrush>delle <xref:System.Drawing.TextureBrush>forme <xref:System.Drawing.Drawing2D.LinearGradientBrush>chiuse, <xref:System.Drawing.Drawing2D.PathGradientBrush>ovvero,,, e.</span><span class="sxs-lookup"><span data-stu-id="bf3cd-105">GDI+ provides several brush classes for filling the interiors of closed shapes: <xref:System.Drawing.SolidBrush>, <xref:System.Drawing.Drawing2D.HatchBrush>, <xref:System.Drawing.TextureBrush>, <xref:System.Drawing.Drawing2D.LinearGradientBrush>, and <xref:System.Drawing.Drawing2D.PathGradientBrush>.</span></span> <span data-ttu-id="bf3cd-106">Tutte le classi ereditano dalla <xref:System.Drawing.Brush> classe.</span><span class="sxs-lookup"><span data-stu-id="bf3cd-106">All of these classes inherit from the <xref:System.Drawing.Brush> class.</span></span> <span data-ttu-id="bf3cd-107">Nella figura seguente viene illustrato un rettangolo riempito con un pennello a tinta unita e un'ellisse riempita con un pennello di tratteggio.</span><span class="sxs-lookup"><span data-stu-id="bf3cd-107">The following illustration shows a rectangle filled with a solid brush and an ellipse filled with a hatch brush.</span></span>  
  
 <span data-ttu-id="bf3cd-108">![Forme piene](./media/aboutgdip02-art17.gif "Aboutgdip02_art17")</span><span class="sxs-lookup"><span data-stu-id="bf3cd-108">![Filled Shapes](./media/aboutgdip02-art17.gif "Aboutgdip02_art17")</span></span>  
  
## <a name="solid-brushes"></a><span data-ttu-id="bf3cd-109">Pennelli a tinta unita</span><span class="sxs-lookup"><span data-stu-id="bf3cd-109">Solid Brushes</span></span>  
 <span data-ttu-id="bf3cd-110">Per riempire una forma chiusa, è necessario disporre di un'istanza <xref:System.Drawing.Graphics> della classe e <xref:System.Drawing.Brush>di un oggetto.</span><span class="sxs-lookup"><span data-stu-id="bf3cd-110">To fill a closed shape, you need an instance of the <xref:System.Drawing.Graphics> class and a <xref:System.Drawing.Brush>.</span></span> <span data-ttu-id="bf3cd-111">L'istanza della <xref:System.Drawing.Graphics> classe fornisce metodi, <xref:System.Drawing.Graphics.FillRectangle%2A> ad esempio e <xref:System.Drawing.Graphics.FillEllipse%2A>, e archivia gli <xref:System.Drawing.Brush> attributi del riempimento, ad esempio il colore e il motivo.</span><span class="sxs-lookup"><span data-stu-id="bf3cd-111">The instance of the <xref:System.Drawing.Graphics> class provides methods, such as <xref:System.Drawing.Graphics.FillRectangle%2A> and <xref:System.Drawing.Graphics.FillEllipse%2A>, and the <xref:System.Drawing.Brush> stores attributes of the fill, such as color and pattern.</span></span> <span data-ttu-id="bf3cd-112"><xref:System.Drawing.Brush> Viene passato come uno degli argomenti del metodo Fill.</span><span class="sxs-lookup"><span data-stu-id="bf3cd-112">The <xref:System.Drawing.Brush> is passed as one of the arguments to the fill method.</span></span> <span data-ttu-id="bf3cd-113">Nell'esempio di codice seguente viene illustrato come riempire un'ellisse con un colore rosso a tinta unita.</span><span class="sxs-lookup"><span data-stu-id="bf3cd-113">The following code example shows how to fill an ellipse with a solid red color.</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#121](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#121)]
 [!code-vb[LinesCurvesAndShapes#121](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#121)]  
  
> [!NOTE]
> <span data-ttu-id="bf3cd-114">Nell'esempio precedente, il pennello è di tipo <xref:System.Drawing.SolidBrush>, che eredita da. <xref:System.Drawing.Brush></span><span class="sxs-lookup"><span data-stu-id="bf3cd-114">In the preceding example, the brush is of type <xref:System.Drawing.SolidBrush>, which inherits from <xref:System.Drawing.Brush>.</span></span>  
  
## <a name="hatch-brushes"></a><span data-ttu-id="bf3cd-115">Pennelli tratteggiati</span><span class="sxs-lookup"><span data-stu-id="bf3cd-115">Hatch Brushes</span></span>  
 <span data-ttu-id="bf3cd-116">Quando si riempie una forma con un pennello tratteggiato, è necessario specificare un colore di primo piano, un colore di sfondo e uno stile di tratteggio.</span><span class="sxs-lookup"><span data-stu-id="bf3cd-116">When you fill a shape with a hatch brush, you specify a foreground color, a background color, and a hatch style.</span></span> <span data-ttu-id="bf3cd-117">Il colore di primo piano è il colore del tratteggio.</span><span class="sxs-lookup"><span data-stu-id="bf3cd-117">The foreground color is the color of the hatching.</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#122](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#122)]
 [!code-vb[LinesCurvesAndShapes#122](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#122)]  
  
 <span data-ttu-id="bf3cd-118">GDI+ fornisce più di 50 stili di tratteggio; i tre stili illustrati nella figura seguente sono <xref:System.Drawing.Drawing2D.HatchStyle.Horizontal>, <xref:System.Drawing.Drawing2D.HatchStyle.ForwardDiagonal>e <xref:System.Drawing.Drawing2D.HatchStyle.Cross>.</span><span class="sxs-lookup"><span data-stu-id="bf3cd-118">GDI+ provides more than 50 hatch styles; the three styles shown in the following illustration are <xref:System.Drawing.Drawing2D.HatchStyle.Horizontal>, <xref:System.Drawing.Drawing2D.HatchStyle.ForwardDiagonal>, and <xref:System.Drawing.Drawing2D.HatchStyle.Cross>.</span></span>  
  
 <span data-ttu-id="bf3cd-119">![Forme piene](./media/aboutgdip02-art18.gif "Aboutgdip02_art18")</span><span class="sxs-lookup"><span data-stu-id="bf3cd-119">![Filled Shapes](./media/aboutgdip02-art18.gif "Aboutgdip02_art18")</span></span>  
  
## <a name="texture-brushes"></a><span data-ttu-id="bf3cd-120">Pennelli trama</span><span class="sxs-lookup"><span data-stu-id="bf3cd-120">Texture Brushes</span></span>  
 <span data-ttu-id="bf3cd-121">Con un pennello trama è possibile riempire una forma con un modello archiviato in una bitmap.</span><span class="sxs-lookup"><span data-stu-id="bf3cd-121">With a texture brush, you can fill a shape with a pattern stored in a bitmap.</span></span> <span data-ttu-id="bf3cd-122">Si supponga, ad esempio, che l'immagine seguente venga archiviata in `MyTexture.bmp`un file su disco denominato.</span><span class="sxs-lookup"><span data-stu-id="bf3cd-122">For example, suppose the following picture is stored in a disk file named `MyTexture.bmp`.</span></span>  
  
 <span data-ttu-id="bf3cd-123">![Forma riempita](./media/aboutgdip02-art19.gif "Aboutgdip02_Art19")</span><span class="sxs-lookup"><span data-stu-id="bf3cd-123">![Filled Shape](./media/aboutgdip02-art19.gif "Aboutgdip02_Art19")</span></span>  
  
 <span data-ttu-id="bf3cd-124">Nell'esempio di codice seguente viene illustrato come riempire un'ellisse ripetendo l' `MyTexture.bmp`immagine archiviata in.</span><span class="sxs-lookup"><span data-stu-id="bf3cd-124">The following code example shows how to fill an ellipse by repeating the picture stored in `MyTexture.bmp`.</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#123](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#123)]
 [!code-vb[LinesCurvesAndShapes#123](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#123)]  
  
 <span data-ttu-id="bf3cd-125">Nell'illustrazione seguente viene mostrata l'ellisse piena.</span><span class="sxs-lookup"><span data-stu-id="bf3cd-125">The following illustration shows the filled ellipse.</span></span>  
  
 <span data-ttu-id="bf3cd-126">![Forma riempita](./media/aboutgdip02-art20.gif "AboutGdip02_Art20")</span><span class="sxs-lookup"><span data-stu-id="bf3cd-126">![Filled Shape](./media/aboutgdip02-art20.gif "AboutGdip02_Art20")</span></span>  
  
## <a name="gradient-brushes"></a><span data-ttu-id="bf3cd-127">Pennelli sfumatura</span><span class="sxs-lookup"><span data-stu-id="bf3cd-127">Gradient Brushes</span></span>  
 <span data-ttu-id="bf3cd-128">GDI+ fornisce due tipi di pennelli sfumatura: lineare e percorso.</span><span class="sxs-lookup"><span data-stu-id="bf3cd-128">GDI+ provides two kinds of gradient brushes: linear and path.</span></span> <span data-ttu-id="bf3cd-129">È possibile utilizzare un pennello sfumato lineare per riempire una forma con un colore che cambia gradualmente man mano che si sposta la forma orizzontalmente, verticalmente o in diagonale.</span><span class="sxs-lookup"><span data-stu-id="bf3cd-129">You can use a linear gradient brush to fill a shape with color that changes gradually as you move across the shape horizontally, vertically, or diagonally.</span></span> <span data-ttu-id="bf3cd-130">Nell'esempio di codice seguente viene illustrato come riempire un'ellisse con un pennello sfumato orizzontale che passa da blu a verde mentre si sposta dal bordo sinistro dell'ellisse al bordo destro.</span><span class="sxs-lookup"><span data-stu-id="bf3cd-130">The following code example shows how to fill an ellipse with a horizontal gradient brush that changes from blue to green as you move from the left edge of the ellipse to the right edge.</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#124](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#124)]
 [!code-vb[LinesCurvesAndShapes#124](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#124)]  
  
 <span data-ttu-id="bf3cd-131">Nell'illustrazione seguente viene mostrata l'ellisse piena.</span><span class="sxs-lookup"><span data-stu-id="bf3cd-131">The following illustration shows the filled ellipse.</span></span>  
  
 <span data-ttu-id="bf3cd-132">![Forma riempita](./media/aboutgdip02-art21.gif "AboutGdip02_Art21")</span><span class="sxs-lookup"><span data-stu-id="bf3cd-132">![Filled Shape](./media/aboutgdip02-art21.gif "AboutGdip02_Art21")</span></span>  
  
 <span data-ttu-id="bf3cd-133">Un pennello sfumatura percorso può essere configurato per modificare il colore mentre si sposta dal centro di una forma verso il bordo.</span><span class="sxs-lookup"><span data-stu-id="bf3cd-133">A path gradient brush can be configured to change color as you move from the center of a shape toward the edge.</span></span>  
  
 <span data-ttu-id="bf3cd-134">![Forma riempita](./media/aboutgdip02-art22.gif "AboutGdip02_Art22")</span><span class="sxs-lookup"><span data-stu-id="bf3cd-134">![Filled Shape](./media/aboutgdip02-art22.gif "AboutGdip02_Art22")</span></span>  
  
 <span data-ttu-id="bf3cd-135">I pennelli sfumatura del percorso sono piuttosto flessibili.</span><span class="sxs-lookup"><span data-stu-id="bf3cd-135">Path gradient brushes are quite flexible.</span></span> <span data-ttu-id="bf3cd-136">Il pennello sfumatura utilizzato per riempire il triangolo nell'illustrazione seguente passa gradualmente da rosso al centro a ognuno dei tre colori diversi nei vertici.</span><span class="sxs-lookup"><span data-stu-id="bf3cd-136">The gradient brush used to fill the triangle in the following illustration changes gradually from red at the center to each of three different colors at the vertices.</span></span>  
  
 <span data-ttu-id="bf3cd-137">![Forma riempita](./media/aboutgdip02-art23.gif "AboutGdip02_Art23")</span><span class="sxs-lookup"><span data-stu-id="bf3cd-137">![Filled Shape](./media/aboutgdip02-art23.gif "AboutGdip02_Art23")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf3cd-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bf3cd-138">See also</span></span>

- <xref:System.Drawing.SolidBrush?displayProperty=nameWithType>
- <xref:System.Drawing.Drawing2D.HatchBrush?displayProperty=nameWithType>
- <xref:System.Drawing.TextureBrush?displayProperty=nameWithType>
- <xref:System.Drawing.Drawing2D.LinearGradientBrush?displayProperty=nameWithType>
- [<span data-ttu-id="bf3cd-139">Linee, curve e forme</span><span class="sxs-lookup"><span data-stu-id="bf3cd-139">Lines, Curves, and Shapes</span></span>](lines-curves-and-shapes.md)
- [<span data-ttu-id="bf3cd-140">Procedura: Creare un rettangolo pieno in un Windows Form</span><span class="sxs-lookup"><span data-stu-id="bf3cd-140">How to: Draw a Filled Rectangle on a Windows Form</span></span>](how-to-draw-a-filled-rectangle-on-a-windows-form.md)
- [<span data-ttu-id="bf3cd-141">Procedura: Creare un'ellisse piena in un Windows Form</span><span class="sxs-lookup"><span data-stu-id="bf3cd-141">How to: Draw a Filled Ellipse on a Windows Form</span></span>](how-to-draw-a-filled-ellipse-on-a-windows-form.md)
