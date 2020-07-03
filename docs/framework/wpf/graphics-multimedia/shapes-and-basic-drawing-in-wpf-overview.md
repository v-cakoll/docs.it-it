---
title: Cenni preliminari sulla progettazione di forme e di base
description: Migliorare l'interfaccia utente con forme pronte per l'uso e diversi livelli di servizi di rendering in Windows Presentation Foundation (WPF).
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- shapes [WPF], about shapes
- basic drawing [WPF]
- vector drawing [WPF], overview
- vectors [WPF], drawing
- Shape objects [WPF]
ms.assetid: 66d7a6d6-e3b6-47bc-8dfe-8a1b26f7d901
ms.openlocfilehash: 41d8f2b87232740c8945bd6a6099aa86dbe77bc6
ms.sourcegitcommit: b6a1869f97a37f11a68c90afde1a520a6887dcbc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/02/2020
ms.locfileid: "85853689"
---
# <a name="shapes-and-basic-drawing-in-wpf-overview"></a><span data-ttu-id="0e8a6-103">Cenni preliminari sugli oggetti Shape e sulle funzionalità di disegno di base di WPF</span><span class="sxs-lookup"><span data-stu-id="0e8a6-103">Shapes and Basic Drawing in WPF Overview</span></span>
<span data-ttu-id="0e8a6-104">Questo argomento fornisce una panoramica di come creare <xref:System.Windows.Shapes.Shape> oggetti.</span><span class="sxs-lookup"><span data-stu-id="0e8a6-104">This topic gives an overview of how to draw with <xref:System.Windows.Shapes.Shape> objects.</span></span> <span data-ttu-id="0e8a6-105">Un <xref:System.Windows.Shapes.Shape> è un tipo di <xref:System.Windows.UIElement> che consente di disegnare una forma sullo schermo.</span><span class="sxs-lookup"><span data-stu-id="0e8a6-105">A <xref:System.Windows.Shapes.Shape> is a type of <xref:System.Windows.UIElement> that enables you to draw a shape to the screen.</span></span> <span data-ttu-id="0e8a6-106">Poiché si tratta di elementi dell'interfaccia utente, <xref:System.Windows.Shapes.Shape> gli oggetti possono essere utilizzati all'interno <xref:System.Windows.Controls.Panel> di elementi e la maggior parte dei controlli</span><span class="sxs-lookup"><span data-stu-id="0e8a6-106">Because they are UI elements, <xref:System.Windows.Shapes.Shape> objects can be used inside <xref:System.Windows.Controls.Panel> elements and most controls.</span></span>  
  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <span data-ttu-id="0e8a6-107">offre diversi livelli di accesso alla grafica e ai servizi di rendering.</span><span class="sxs-lookup"><span data-stu-id="0e8a6-107">offers several layers of access to graphics and rendering services.</span></span> <span data-ttu-id="0e8a6-108">Al livello superiore, <xref:System.Windows.Shapes.Shape> gli oggetti sono facili da usare e offrono numerose funzionalità utili, ad esempio il layout e la partecipazione al [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] sistema di eventi.</span><span class="sxs-lookup"><span data-stu-id="0e8a6-108">At the top layer, <xref:System.Windows.Shapes.Shape> objects are easy to use and provide many useful features, such as layout and participation in the [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] event system.</span></span>  

<a name="shapes"></a>
## <a name="shape-objects"></a><span data-ttu-id="0e8a6-109">Oggetti Shape</span><span class="sxs-lookup"><span data-stu-id="0e8a6-109">Shape Objects</span></span>  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<span data-ttu-id="0e8a6-110">fornisce una serie di oggetti pronti per l'utilizzo <xref:System.Windows.Shapes.Shape> .</span><span class="sxs-lookup"><span data-stu-id="0e8a6-110">provides a number of ready-to-use <xref:System.Windows.Shapes.Shape> objects.</span></span>  <span data-ttu-id="0e8a6-111">Tutti gli oggetti Shape ereditano dalla <xref:System.Windows.Shapes.Shape> classe.</span><span class="sxs-lookup"><span data-stu-id="0e8a6-111">All shape objects inherit from the <xref:System.Windows.Shapes.Shape> class.</span></span> <span data-ttu-id="0e8a6-112">Gli oggetti Shape disponibili includono <xref:System.Windows.Shapes.Ellipse> ,, <xref:System.Windows.Shapes.Line> <xref:System.Windows.Shapes.Path> , <xref:System.Windows.Shapes.Polygon> , <xref:System.Windows.Shapes.Polyline> e <xref:System.Windows.Shapes.Rectangle> .</span><span class="sxs-lookup"><span data-stu-id="0e8a6-112">Available shape objects include <xref:System.Windows.Shapes.Ellipse>, <xref:System.Windows.Shapes.Line>, <xref:System.Windows.Shapes.Path>, <xref:System.Windows.Shapes.Polygon>, <xref:System.Windows.Shapes.Polyline>, and <xref:System.Windows.Shapes.Rectangle>.</span></span> <span data-ttu-id="0e8a6-113"><xref:System.Windows.Shapes.Shape>gli oggetti condividono le seguenti proprietà comuni.</span><span class="sxs-lookup"><span data-stu-id="0e8a6-113"><xref:System.Windows.Shapes.Shape> objects share the following common properties.</span></span>  
  
- <span data-ttu-id="0e8a6-114"><xref:System.Windows.Shapes.Shape.Stroke%2A>: Descrive il modo in cui viene disegnato il contorno della forma.</span><span class="sxs-lookup"><span data-stu-id="0e8a6-114"><xref:System.Windows.Shapes.Shape.Stroke%2A>: Describes how the shape's outline is painted.</span></span>  
  
- <span data-ttu-id="0e8a6-115"><xref:System.Windows.Shapes.Shape.StrokeThickness%2A>: Descrive lo spessore del contorno della forma.</span><span class="sxs-lookup"><span data-stu-id="0e8a6-115"><xref:System.Windows.Shapes.Shape.StrokeThickness%2A>: Describes the thickness of the shape's outline.</span></span>  
  
- <span data-ttu-id="0e8a6-116"><xref:System.Windows.Shapes.Shape.Fill%2A>: Descrive il modo in cui viene disegnata l'area interna della forma.</span><span class="sxs-lookup"><span data-stu-id="0e8a6-116"><xref:System.Windows.Shapes.Shape.Fill%2A>: Describes how the interior of the shape is painted.</span></span>  
  
- <span data-ttu-id="0e8a6-117">Proprietà dei dati per specificare coordinate e vertici, misurati in pixel indipendenti dal dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0e8a6-117">Data properties to specify coordinates and vertices, measured in device-independent pixels.</span></span>  
  
 <span data-ttu-id="0e8a6-118">Poiché derivano da <xref:System.Windows.UIElement> , gli oggetti Shape possono essere utilizzati all'interno di pannelli e la maggior parte dei controlli.</span><span class="sxs-lookup"><span data-stu-id="0e8a6-118">Because they derive from <xref:System.Windows.UIElement>, shape objects can be used inside panels and most controls.</span></span> <span data-ttu-id="0e8a6-119">Il <xref:System.Windows.Controls.Canvas> pannello è una scelta particolarmente utile per la creazione di disegni complessi, perché supporta il posizionamento assoluto dei relativi oggetti figlio.</span><span class="sxs-lookup"><span data-stu-id="0e8a6-119">The <xref:System.Windows.Controls.Canvas> panel is a particularly good choice for creating complex drawings because it supports absolute positioning of its child objects.</span></span>  
  
 <span data-ttu-id="0e8a6-120">La <xref:System.Windows.Shapes.Line> classe consente di creare una linea tra due punti.</span><span class="sxs-lookup"><span data-stu-id="0e8a6-120">The <xref:System.Windows.Shapes.Line> class enables you to draw a line between two points.</span></span> <span data-ttu-id="0e8a6-121">L'esempio seguente illustra molti modi per specificare le coordinate della riga e le proprietà del tratto.</span><span class="sxs-lookup"><span data-stu-id="0e8a6-121">The following example shows several ways to specify line coordinates and stroke properties.</span></span>  
  
 [!code-xaml[drawingwithshapeelements#LineExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/lineexample.xaml#lineexample1)]  
  
 [!code-cpp[shapesprocedural#ShapesProceduralLine](~/samples/snippets/cpp/VS_Snippets_Wpf/ShapesProcedural/CPP/ShapesProcedural.cpp#shapesproceduralline)]
 [!code-csharp[shapesprocedural#ShapesProceduralLine](~/samples/snippets/csharp/VS_Snippets_Wpf/ShapesProcedural/Csharp/ShapesProcedural.cs#shapesproceduralline)]
 [!code-vb[shapesprocedural#ShapesProceduralLine](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ShapesProcedural/VisualBasic/ShapesProceduralVB.vb#shapesproceduralline)]  
  
 <span data-ttu-id="0e8a6-122">Nell'immagine seguente viene illustrato il rendering <xref:System.Windows.Shapes.Line> .</span><span class="sxs-lookup"><span data-stu-id="0e8a6-122">The following image shows the rendered <xref:System.Windows.Shapes.Line>.</span></span>  
  
 <span data-ttu-id="0e8a6-123">![Illustrazione di Line](./media/shape-ovw-line2.gif "shape_ovw_line2")</span><span class="sxs-lookup"><span data-stu-id="0e8a6-123">![Line illustration](./media/shape-ovw-line2.gif "shape_ovw_line2")</span></span>  
  
 <span data-ttu-id="0e8a6-124">Sebbene la <xref:System.Windows.Shapes.Line> classe fornisca una <xref:System.Windows.Shapes.Shape.Fill%2A> proprietà, l'impostazione non ha alcun effetto perché un oggetto <xref:System.Windows.Shapes.Line> non dispone di un'area.</span><span class="sxs-lookup"><span data-stu-id="0e8a6-124">Although the <xref:System.Windows.Shapes.Line> class does provide a <xref:System.Windows.Shapes.Shape.Fill%2A> property, setting it has no effect because a <xref:System.Windows.Shapes.Line> has no area.</span></span>  
  
 <span data-ttu-id="0e8a6-125">Un'altra forma comune è <xref:System.Windows.Shapes.Ellipse> .</span><span class="sxs-lookup"><span data-stu-id="0e8a6-125">Another common shape is the <xref:System.Windows.Shapes.Ellipse>.</span></span>  <span data-ttu-id="0e8a6-126">Creare un oggetto <xref:System.Windows.Shapes.Ellipse> definendo le <xref:System.Windows.FrameworkElement.Width%2A> proprietà e della forma <xref:System.Windows.FrameworkElement.Height%2A> .</span><span class="sxs-lookup"><span data-stu-id="0e8a6-126">Create an <xref:System.Windows.Shapes.Ellipse> by defining the shape's <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties.</span></span> <span data-ttu-id="0e8a6-127">Per creare un cerchio, specificare <xref:System.Windows.Shapes.Ellipse> i cui <xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.FrameworkElement.Height%2A> valori e sono uguali.</span><span class="sxs-lookup"><span data-stu-id="0e8a6-127">To draw a circle, specify an <xref:System.Windows.Shapes.Ellipse> whose <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> values are equal.</span></span>  
  
 [!code-xaml[ShapeOverviews#ShapesOVW1](~/samples/snippets/csharp/VS_Snippets_Wpf/ShapeOverviews/CS/Window1.xaml#shapesovw1)]  
  
 [!code-csharp[brushesmiscsnippets_procedural_snip#SetBackgroundColorOfShapeCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesMiscSnippets_procedural_snip/CSharp/SetBackgroundColorOfShapeExample.cs#setbackgroundcolorofshapecodeexamplewholepage)]
 [!code-vb[brushesmiscsnippets_procedural_snip#SetBackgroundColorOfShapeCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesMiscSnippets_procedural_snip/visualbasic/setbackgroundcolorofshapeexample.vb#setbackgroundcolorofshapecodeexamplewholepage)]  
  
 <span data-ttu-id="0e8a6-128">La figura seguente mostra un esempio di un oggetto di cui è stato eseguito il rendering <xref:System.Windows.Shapes.Ellipse> .</span><span class="sxs-lookup"><span data-stu-id="0e8a6-128">The following image shows an example of a rendered <xref:System.Windows.Shapes.Ellipse>.</span></span>  
  
 <span data-ttu-id="0e8a6-129">![Illustrazione di Ellipse](./media/shape-ovw-ellipse2.png "shape_ovw_ellipse2")</span><span class="sxs-lookup"><span data-stu-id="0e8a6-129">![Ellipse illustration](./media/shape-ovw-ellipse2.png "shape_ovw_ellipse2")</span></span>  
  
<a name="paths"></a>
## <a name="using-paths-and-geometries"></a><span data-ttu-id="0e8a6-130">Utilizzo di tracciati e geometrie</span><span class="sxs-lookup"><span data-stu-id="0e8a6-130">Using Paths and Geometries</span></span>  
 <span data-ttu-id="0e8a6-131">La <xref:System.Windows.Shapes.Path> classe consente di creare curve e forme complesse.</span><span class="sxs-lookup"><span data-stu-id="0e8a6-131">The <xref:System.Windows.Shapes.Path> class enables you to draw curves and complex shapes.</span></span> <span data-ttu-id="0e8a6-132">Queste curve e forme vengono descritte utilizzando <xref:System.Windows.Media.Geometry> gli oggetti.</span><span class="sxs-lookup"><span data-stu-id="0e8a6-132">These curves and shapes are described using <xref:System.Windows.Media.Geometry> objects.</span></span> <span data-ttu-id="0e8a6-133">Per utilizzare un <xref:System.Windows.Shapes.Path> oggetto, è necessario creare un <xref:System.Windows.Media.Geometry> oggetto e utilizzarlo per impostare la <xref:System.Windows.Shapes.Path> proprietà dell'oggetto <xref:System.Windows.Shapes.Path.Data%2A> .</span><span class="sxs-lookup"><span data-stu-id="0e8a6-133">To use a <xref:System.Windows.Shapes.Path>, you create a <xref:System.Windows.Media.Geometry> and use it to set the <xref:System.Windows.Shapes.Path> object's <xref:System.Windows.Shapes.Path.Data%2A> property.</span></span>  
  
 <span data-ttu-id="0e8a6-134">È possibile <xref:System.Windows.Media.Geometry> scegliere tra diversi oggetti.</span><span class="sxs-lookup"><span data-stu-id="0e8a6-134">There are a variety of <xref:System.Windows.Media.Geometry> objects to choose from.</span></span> <span data-ttu-id="0e8a6-135">Le <xref:System.Windows.Media.LineGeometry> <xref:System.Windows.Media.RectangleGeometry> classi, e <xref:System.Windows.Media.EllipseGeometry> descrivono forme relativamente semplici.</span><span class="sxs-lookup"><span data-stu-id="0e8a6-135">The <xref:System.Windows.Media.LineGeometry>, <xref:System.Windows.Media.RectangleGeometry>, and <xref:System.Windows.Media.EllipseGeometry> classes describe relatively simple shapes.</span></span> <span data-ttu-id="0e8a6-136">Per creare forme più complesse o creare curve, usare un oggetto <xref:System.Windows.Media.PathGeometry> .</span><span class="sxs-lookup"><span data-stu-id="0e8a6-136">To create more complex shapes or create curves, use a <xref:System.Windows.Media.PathGeometry>.</span></span>  
  
<a name="pathgeometry"></a>
### <a name="pathgeometry-and-pathsegments"></a><span data-ttu-id="0e8a6-137">PathGeometry e PathSegments</span><span class="sxs-lookup"><span data-stu-id="0e8a6-137">PathGeometry and PathSegments</span></span>  
 <span data-ttu-id="0e8a6-138"><xref:System.Windows.Media.PathGeometry>gli oggetti sono costituiti da uno o più <xref:System.Windows.Media.PathFigure> oggetti, ognuno dei quali <xref:System.Windows.Media.PathFigure> rappresenta una "figura" o una forma diversa.</span><span class="sxs-lookup"><span data-stu-id="0e8a6-138"><xref:System.Windows.Media.PathGeometry> objects are comprised of one or more <xref:System.Windows.Media.PathFigure> objects; each <xref:System.Windows.Media.PathFigure> represents a different "figure" or shape.</span></span> <span data-ttu-id="0e8a6-139">Ognuno <xref:System.Windows.Media.PathFigure> è costituito da uno o più <xref:System.Windows.Media.PathSegment> oggetti, ognuno dei quali rappresenta una parte connessa della figura o della forma.</span><span class="sxs-lookup"><span data-stu-id="0e8a6-139">Each <xref:System.Windows.Media.PathFigure> is itself comprised of one or more <xref:System.Windows.Media.PathSegment> objects, each representing a connected portion of the figure or shape.</span></span> <span data-ttu-id="0e8a6-140">I tipi di segmenti includono i seguenti: <xref:System.Windows.Media.LineSegment> , <xref:System.Windows.Media.BezierSegment> e <xref:System.Windows.Media.ArcSegment> .</span><span class="sxs-lookup"><span data-stu-id="0e8a6-140">Segment types include the following: <xref:System.Windows.Media.LineSegment>, <xref:System.Windows.Media.BezierSegment>, and <xref:System.Windows.Media.ArcSegment>.</span></span>  
  
 <span data-ttu-id="0e8a6-141">Nell'esempio seguente <xref:System.Windows.Shapes.Path> viene usato un oggetto per creare una curva di Bézier quadratica.</span><span class="sxs-lookup"><span data-stu-id="0e8a6-141">In the following example, a <xref:System.Windows.Shapes.Path> is used to draw a quadratic Bezier curve.</span></span>  
  
 [!code-xaml[geometrysample#34](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#34)]  
  
 <span data-ttu-id="0e8a6-142">L'immagine seguente illustra la forma sottoposta a rendering.</span><span class="sxs-lookup"><span data-stu-id="0e8a6-142">The following image shows the rendered shape.</span></span>  
  
 <span data-ttu-id="0e8a6-143">![Illustrazione di Path](./media/shape-ovw-path2.gif "shape_ovw_path2")</span><span class="sxs-lookup"><span data-stu-id="0e8a6-143">![Path illustration](./media/shape-ovw-path2.gif "shape_ovw_path2")</span></span>  
  
 <span data-ttu-id="0e8a6-144">Per ulteriori informazioni su <xref:System.Windows.Media.PathGeometry> e sulle altre <xref:System.Windows.Media.Geometry> classi, vedere [Cenni preliminari sulla geometria](geometry-overview.md).</span><span class="sxs-lookup"><span data-stu-id="0e8a6-144">For more information about <xref:System.Windows.Media.PathGeometry> and the other <xref:System.Windows.Media.Geometry> classes, see the [Geometry Overview](geometry-overview.md).</span></span>  
  
<a name="pathdatastring"></a>
### <a name="xaml-abbreviated-syntax"></a><span data-ttu-id="0e8a6-145">Sintassi abbreviata XAML</span><span class="sxs-lookup"><span data-stu-id="0e8a6-145">XAML Abbreviated Syntax</span></span>  
 <span data-ttu-id="0e8a6-146">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] è anche possibile usare una speciale sintassi abbreviata per descrivere un <xref:System.Windows.Shapes.Path> .</span><span class="sxs-lookup"><span data-stu-id="0e8a6-146">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], you may also use a special abbreviated syntax to describe a <xref:System.Windows.Shapes.Path>.</span></span> <span data-ttu-id="0e8a6-147">Nell'esempio seguente viene usata la sintassi abbreviata per disegnare una forma complessa.</span><span class="sxs-lookup"><span data-stu-id="0e8a6-147">In the following example, abbreviated syntax is used to draw a complex shape.</span></span>  
  
```xaml  
      <Path Stroke="DarkGoldenRod" StrokeThickness="3"
Data="M 100,200 C 100,25 400,350 400,175 H 280" />  
```  
  
 <span data-ttu-id="0e8a6-148">Nell'immagine seguente viene illustrato un oggetto sottoposto a rendering <xref:System.Windows.Shapes.Path> .</span><span class="sxs-lookup"><span data-stu-id="0e8a6-148">The following image shows a rendered <xref:System.Windows.Shapes.Path>.</span></span>  
  
 <span data-ttu-id="0e8a6-149">![Illustrazione di Path](./media/shape-ovw-path.PNG "shape_ovw_path")</span><span class="sxs-lookup"><span data-stu-id="0e8a6-149">![Path illustration](./media/shape-ovw-path.PNG "shape_ovw_path")</span></span>  
  
 <span data-ttu-id="0e8a6-150">La <xref:System.Windows.Shapes.Path.Data%2A> stringa dell'attributo inizia con il comando "MoveTo", indicato da M, che stabilisce un punto iniziale per il percorso nel sistema di coordinate di <xref:System.Windows.Controls.Canvas> .</span><span class="sxs-lookup"><span data-stu-id="0e8a6-150">The <xref:System.Windows.Shapes.Path.Data%2A> attribute string begins with the "moveto" command, indicated by M, which establishes a start point for the path in the coordinate system of the <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="0e8a6-151"><xref:System.Windows.Shapes.Path>i parametri dati fanno distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="0e8a6-151"><xref:System.Windows.Shapes.Path> data parameters are case-sensitive.</span></span> <span data-ttu-id="0e8a6-152">Il valore letterale M indica una posizione assoluta per il nuovo punto corrente.</span><span class="sxs-lookup"><span data-stu-id="0e8a6-152">The capital M indicates an absolute location for the new current point.</span></span> <span data-ttu-id="0e8a6-153">Una lettera m minuscola indica le coordinate relative.</span><span class="sxs-lookup"><span data-stu-id="0e8a6-153">A lowercase m would indicate relative coordinates.</span></span> <span data-ttu-id="0e8a6-154">Il primo segmento è una curva di Bézier cubica che inizia in corrispondenza del punto (100,200) e termina in corrispondenza del punto (400,175) e viene disegnata usando i due punti di controllo (100,25) e (400,350).</span><span class="sxs-lookup"><span data-stu-id="0e8a6-154">The first segment is a cubic Bezier curve beginning at (100,200) and ending at (400,175), drawn using the two control points (100,25) and (400,350).</span></span> <span data-ttu-id="0e8a6-155">Questo segmento è indicato dal comando C nella stringa dell' <xref:System.Windows.Shapes.Path.Data%2A> attributo.</span><span class="sxs-lookup"><span data-stu-id="0e8a6-155">This segment is indicated by the C command in the <xref:System.Windows.Shapes.Path.Data%2A> attribute string.</span></span> <span data-ttu-id="0e8a6-156">Anche in questo caso la lettera C maiuscola indica un percorso assoluto, mentre la lettera c minuscola indica un percorso relativo.</span><span class="sxs-lookup"><span data-stu-id="0e8a6-156">Again, the capital C indicates an absolute path; the lowercase c would indicate a relative path.</span></span>  
  
 <span data-ttu-id="0e8a6-157">Il secondo segmento inizia con un comando orizzontale assoluto "lineto" H, che specifica una riga disegnata dal punto finale del sottopercorso precedente (400,175) a un nuovo punto finale (280,175).</span><span class="sxs-lookup"><span data-stu-id="0e8a6-157">The second segment begins with an absolute horizontal "lineto" command H, which specifies a line drawn from the preceding subpath's endpoint (400,175) to a new endpoint (280,175).</span></span> <span data-ttu-id="0e8a6-158">Poiché si tratta di un comando "lineto" orizzontale, il valore specificato è una coordinata *x*.</span><span class="sxs-lookup"><span data-stu-id="0e8a6-158">Because it is a horizontal "lineto" command, the value specified is an *x*-coordinate.</span></span>  
  
 <span data-ttu-id="0e8a6-159">Per la sintassi del percorso completo, vedere il <xref:System.Windows.Shapes.Path.Data%2A> riferimento e [creare una forma usando un oggetto PathGeometry](how-to-create-a-shape-by-using-a-pathgeometry.md).</span><span class="sxs-lookup"><span data-stu-id="0e8a6-159">For the complete path syntax, see the <xref:System.Windows.Shapes.Path.Data%2A> reference and [Create a Shape by Using a PathGeometry](how-to-create-a-shape-by-using-a-pathgeometry.md).</span></span>  
  
<a name="fillpaint"></a>
## <a name="painting-shapes"></a><span data-ttu-id="0e8a6-160">Disegno di oggetti Shape</span><span class="sxs-lookup"><span data-stu-id="0e8a6-160">Painting Shapes</span></span>  
 <span data-ttu-id="0e8a6-161"><xref:System.Windows.Media.Brush>gli oggetti vengono utilizzati per disegnare le forme <xref:System.Windows.Shapes.Shape.Stroke%2A> e <xref:System.Windows.Shapes.Shape.Fill%2A> .</span><span class="sxs-lookup"><span data-stu-id="0e8a6-161"><xref:System.Windows.Media.Brush> objects are used to paint a shape's <xref:System.Windows.Shapes.Shape.Stroke%2A> and <xref:System.Windows.Shapes.Shape.Fill%2A>.</span></span> <span data-ttu-id="0e8a6-162">Nell'esempio seguente vengono specificati il tratto e il riempimento di un oggetto <xref:System.Windows.Shapes.Ellipse> .</span><span class="sxs-lookup"><span data-stu-id="0e8a6-162">In the following example, the stroke and fill of an <xref:System.Windows.Shapes.Ellipse> are specified.</span></span> <span data-ttu-id="0e8a6-163">Si noti che un input valido per le proprietà del pennello può essere rappresentato da una parola chiave o da un valore di colore esadecimale.</span><span class="sxs-lookup"><span data-stu-id="0e8a6-163">Note that valid input for brush properties can be either a keyword or hexadecimal color value.</span></span> <span data-ttu-id="0e8a6-164">Per ulteriori informazioni sulle parole chiave dei colori disponibili, vedere Proprietà della <xref:System.Windows.Media.Colors> classe nello <xref:System.Windows.Media> spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="0e8a6-164">For more information about available color keywords, see properties of the <xref:System.Windows.Media.Colors> class in the <xref:System.Windows.Media> namespace.</span></span>  
  
```xaml
<Canvas Background="LightGray">
   <Ellipse  
      Canvas.Top="50"  
      Canvas.Left="50"  
      Fill="#FFFFFF00"  
      Height="75"  
      Width="75"  
      StrokeThickness="5"  
      Stroke="#FF0000FF"/>  
</Canvas>  
```  
  
 <span data-ttu-id="0e8a6-165">Nell'immagine seguente viene illustrato il rendering <xref:System.Windows.Shapes.Ellipse> .</span><span class="sxs-lookup"><span data-stu-id="0e8a6-165">The following image shows the rendered <xref:System.Windows.Shapes.Ellipse>.</span></span>  
  
 <span data-ttu-id="0e8a6-166">![Ellisse](./media/shape-ovw-ellipsefill.PNG "shape_ovw_ellipsefill")</span><span class="sxs-lookup"><span data-stu-id="0e8a6-166">![An ellipse](./media/shape-ovw-ellipsefill.PNG "shape_ovw_ellipsefill")</span></span>  
  
 <span data-ttu-id="0e8a6-167">In alternativa, è possibile utilizzare la sintassi dell'elemento proprietà per creare in modo esplicito un <xref:System.Windows.Media.SolidColorBrush> oggetto per disegnare la forma con un colore a tinta unita.</span><span class="sxs-lookup"><span data-stu-id="0e8a6-167">Alternatively, you can use property element syntax to explicitly create a <xref:System.Windows.Media.SolidColorBrush> object to paint the shape with a solid color.</span></span>  
  
```xaml
<!-- This polygon shape uses pre-defined color values for its Stroke and  
     Fill properties.   
     The SolidColorBrush's Opacity property affects the fill color in   
     this case by making it slightly transparent (opacity of 0.4) so   
     that it blends with any underlying color. -->  
  
<Polygon  
    Points="300,200 400,125 400,275 300,200"  
    Stroke="Purple"
    StrokeThickness="2">  
    <Polygon.Fill>  
       <SolidColorBrush Color="Blue" Opacity="0.4"/>  
    </Polygon.Fill>  
</Polygon>  
```  
  
 <span data-ttu-id="0e8a6-168">La figura seguente mostra la forma sottoposta a rendering.</span><span class="sxs-lookup"><span data-stu-id="0e8a6-168">The following illustration shows the rendered shape.</span></span>  
  
 <span data-ttu-id="0e8a6-169">![Illustrazione di SolidColorBrush](./media/shape-ovw-solidcolorbrush.PNG "shape_ovw_solidcolorbrush")</span><span class="sxs-lookup"><span data-stu-id="0e8a6-169">![SolidColorBrush illustration](./media/shape-ovw-solidcolorbrush.PNG "shape_ovw_solidcolorbrush")</span></span>  
  
 <span data-ttu-id="0e8a6-170">È anche possibile disegnare il tratto o il riempimento di una forma con sfumature, immagini, motivi e così via.</span><span class="sxs-lookup"><span data-stu-id="0e8a6-170">You can also paint a shape's stroke or fill with gradients, images, patterns, and more.</span></span> <span data-ttu-id="0e8a6-171">Per ulteriori informazioni, vedere [Cenni preliminari sul disegno con colori a tinta unita e sfumature](painting-with-solid-colors-and-gradients-overview.md).</span><span class="sxs-lookup"><span data-stu-id="0e8a6-171">For more information, see the [Painting with Solid Colors and Gradients Overview](painting-with-solid-colors-and-gradients-overview.md).</span></span>  
  
<a name="stretchableshapessection"></a>
## <a name="stretchable-shapes"></a><span data-ttu-id="0e8a6-172">Oggetti Shape allungabili</span><span class="sxs-lookup"><span data-stu-id="0e8a6-172">Stretchable Shapes</span></span>  
 <span data-ttu-id="0e8a6-173"><xref:System.Windows.Shapes.Line>Tutte le <xref:System.Windows.Shapes.Path> classi,, <xref:System.Windows.Shapes.Polygon> , <xref:System.Windows.Shapes.Polyline> e <xref:System.Windows.Shapes.Rectangle> dispongono di una <xref:System.Windows.Shapes.Shape.Stretch%2A> Proprietà.</span><span class="sxs-lookup"><span data-stu-id="0e8a6-173">The <xref:System.Windows.Shapes.Line>, <xref:System.Windows.Shapes.Path>, <xref:System.Windows.Shapes.Polygon>, <xref:System.Windows.Shapes.Polyline>, and <xref:System.Windows.Shapes.Rectangle> classes all have a <xref:System.Windows.Shapes.Shape.Stretch%2A> property.</span></span> <span data-ttu-id="0e8a6-174">Questa proprietà determina il modo in cui il contenuto di un <xref:System.Windows.Shapes.Shape> oggetto (la forma da disegnare) viene allungato per riempire lo <xref:System.Windows.Shapes.Shape> spazio del layout dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="0e8a6-174">This property determines how a <xref:System.Windows.Shapes.Shape> object's contents (the shape to be drawn) is stretched to fill the <xref:System.Windows.Shapes.Shape> object's layout space.</span></span> <span data-ttu-id="0e8a6-175">Lo <xref:System.Windows.Shapes.Shape> spazio del layout di un oggetto corrisponde alla quantità di spazio <xref:System.Windows.Shapes.Shape> allocata dal sistema di layout, a causa di un' <xref:System.Windows.FrameworkElement.Width%2A> impostazione esplicita e o a <xref:System.Windows.FrameworkElement.Height%2A> causa delle <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> Impostazioni e.</span><span class="sxs-lookup"><span data-stu-id="0e8a6-175">A <xref:System.Windows.Shapes.Shape> object's layout space is the amount of space the <xref:System.Windows.Shapes.Shape> is allocated by the layout system, because of either an explicit <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> setting or because of its <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> and <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> settings.</span></span> <span data-ttu-id="0e8a6-176">Per altre informazioni sul layout in Windows Presentation Foundation, vedere Cenni preliminari sul [layout](../advanced/layout.md) .</span><span class="sxs-lookup"><span data-stu-id="0e8a6-176">For additional information on layout in Windows Presentation Foundation, see [Layout](../advanced/layout.md) overview.</span></span>  
  
 <span data-ttu-id="0e8a6-177">La proprietà Stretch accetta uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="0e8a6-177">The Stretch property takes one of the following values:</span></span>  
  
- <span data-ttu-id="0e8a6-178"><xref:System.Windows.Media.Stretch.None>: Il <xref:System.Windows.Shapes.Shape> contenuto dell'oggetto non viene allungato.</span><span class="sxs-lookup"><span data-stu-id="0e8a6-178"><xref:System.Windows.Media.Stretch.None>: The <xref:System.Windows.Shapes.Shape> object's contents are not stretched.</span></span>  
  
- <span data-ttu-id="0e8a6-179"><xref:System.Windows.Media.Stretch.Fill>: Il <xref:System.Windows.Shapes.Shape> contenuto dell'oggetto viene allungato per riempire lo spazio del layout.</span><span class="sxs-lookup"><span data-stu-id="0e8a6-179"><xref:System.Windows.Media.Stretch.Fill>: The <xref:System.Windows.Shapes.Shape> object's contents are stretched to fill its layout space.</span></span>  <span data-ttu-id="0e8a6-180">Le proporzioni non vengono mantenute.</span><span class="sxs-lookup"><span data-stu-id="0e8a6-180">Aspect ratio is not preserved.</span></span>  
  
- <span data-ttu-id="0e8a6-181"><xref:System.Windows.Media.Stretch.Uniform>: Il <xref:System.Windows.Shapes.Shape> contenuto dell'oggetto viene allungato il più possibile per riempire lo spazio del layout mantenendo le proporzioni originali.</span><span class="sxs-lookup"><span data-stu-id="0e8a6-181"><xref:System.Windows.Media.Stretch.Uniform>: The <xref:System.Windows.Shapes.Shape> object's contents are stretched as much as possible to fill its layout space while preserving its original aspect ratio.</span></span>  
  
- <span data-ttu-id="0e8a6-182"><xref:System.Windows.Media.Stretch.UniformToFill>: Il <xref:System.Windows.Shapes.Shape> contenuto dell'oggetto viene allungato per riempire completamente lo spazio del layout mantenendo le proporzioni originali.</span><span class="sxs-lookup"><span data-stu-id="0e8a6-182"><xref:System.Windows.Media.Stretch.UniformToFill>: The <xref:System.Windows.Shapes.Shape> object's contents are stretched to completely fill its layout space while preserving its original aspect ratio.</span></span>  
  
 <span data-ttu-id="0e8a6-183">Si noti che, quando il <xref:System.Windows.Shapes.Shape> contenuto di un oggetto viene allungato, il <xref:System.Windows.Shapes.Shape> contorno dell'oggetto viene disegnato dopo l'estensione.</span><span class="sxs-lookup"><span data-stu-id="0e8a6-183">Note that, when a <xref:System.Windows.Shapes.Shape> object's contents are stretched, the <xref:System.Windows.Shapes.Shape> object's outline is painted after the stretching.</span></span>  
  
 <span data-ttu-id="0e8a6-184">Nell'esempio seguente <xref:System.Windows.Shapes.Polygon> viene usato un oggetto per creare un triangolo molto piccolo da (0, 0) a (0, 1) a (1,1).</span><span class="sxs-lookup"><span data-stu-id="0e8a6-184">In the following example, a <xref:System.Windows.Shapes.Polygon> is used to draw a very small triangle from (0,0) to (0,1) to (1,1).</span></span> <span data-ttu-id="0e8a6-185"><xref:System.Windows.Shapes.Polygon>Gli oggetti <xref:System.Windows.FrameworkElement.Width%2A> e <xref:System.Windows.FrameworkElement.Height%2A> sono impostati su 100 e la relativa proprietà Stretch è impostata su Fill.</span><span class="sxs-lookup"><span data-stu-id="0e8a6-185">The <xref:System.Windows.Shapes.Polygon> object's <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> are set to 100, and its stretch property is set to Fill.</span></span> <span data-ttu-id="0e8a6-186">Di conseguenza, il <xref:System.Windows.Shapes.Polygon> contenuto dell'oggetto (il triangolo) viene allungato per riempire lo spazio più grande.</span><span class="sxs-lookup"><span data-stu-id="0e8a6-186">As a result, the <xref:System.Windows.Shapes.Polygon> object's contents (the triangle) are stretched to fill the larger space.</span></span>  
  
```xaml
<Polygon  
  Points="0,0 0,1 1,1"  
  Fill="Blue"  
  Width="100"  
  Height="100"  
  Stretch="Fill"  
  Stroke="Black"  
  StrokeThickness="2" />  
```

```csharp
PointCollection myPointCollection = new PointCollection();  
myPointCollection.Add(new Point(0,0));  
myPointCollection.Add(new Point(0,1));  
myPointCollection.Add(new Point(1,1));  
  
Polygon myPolygon = new Polygon();  
myPolygon.Points = myPointCollection;  
myPolygon.Fill = Brushes.Blue;  
myPolygon.Width = 100;  
myPolygon.Height = 100;  
myPolygon.Stretch = Stretch.Fill;  
myPolygon.Stroke = Brushes.Black;  
myPolygon.StrokeThickness = 2;  
```

<a name="transforms"></a>
## <a name="transforming-shapes"></a><span data-ttu-id="0e8a6-187">Trasformazione degli oggetti Shape</span><span class="sxs-lookup"><span data-stu-id="0e8a6-187">Transforming Shapes</span></span>  
 <span data-ttu-id="0e8a6-188">La <xref:System.Windows.Media.Transform> classe fornisce i mezzi per trasformare le forme in un piano bidimensionale.</span><span class="sxs-lookup"><span data-stu-id="0e8a6-188">The <xref:System.Windows.Media.Transform> class provides the means to transform shapes in a two-dimensional plane.</span></span>  <span data-ttu-id="0e8a6-189">I diversi tipi di trasformazione includono rotazione ( <xref:System.Windows.Media.RotateTransform> ), scala ( <xref:System.Windows.Media.ScaleTransform> ), inclinazione ( <xref:System.Windows.Media.SkewTransform> ) e conversione ( <xref:System.Windows.Media.TranslateTransform> ).</span><span class="sxs-lookup"><span data-stu-id="0e8a6-189">The different types of transformation include rotation (<xref:System.Windows.Media.RotateTransform>), scale (<xref:System.Windows.Media.ScaleTransform>), skew (<xref:System.Windows.Media.SkewTransform>), and translation (<xref:System.Windows.Media.TranslateTransform>).</span></span>  
  
 <span data-ttu-id="0e8a6-190">Una trasformazione comune da applicare a una forma è una rotazione.</span><span class="sxs-lookup"><span data-stu-id="0e8a6-190">A common transform to apply to a shape is a rotation.</span></span>  <span data-ttu-id="0e8a6-191">Per ruotare una forma, creare un oggetto <xref:System.Windows.Media.RotateTransform> e specificarne il <xref:System.Windows.Media.RotateTransform.Angle%2A> .</span><span class="sxs-lookup"><span data-stu-id="0e8a6-191">To rotate a shape, create a <xref:System.Windows.Media.RotateTransform> and specify its <xref:System.Windows.Media.RotateTransform.Angle%2A>.</span></span> <span data-ttu-id="0e8a6-192">Un <xref:System.Windows.Media.RotateTransform.Angle%2A> di 45 ruota l'elemento 45 gradi in senso orario; un angolo di 90 ruota l'elemento 90 gradi in senso orario e così via.</span><span class="sxs-lookup"><span data-stu-id="0e8a6-192">An <xref:System.Windows.Media.RotateTransform.Angle%2A> of 45 rotates the element 45 degrees clockwise; an angle of 90 rotates the element 90 degrees clockwise; and so on.</span></span> <span data-ttu-id="0e8a6-193">Impostare le <xref:System.Windows.Media.RotateTransform.CenterX%2A> <xref:System.Windows.Media.RotateTransform.CenterY%2A> proprietà e se si desidera controllare il punto in cui viene ruotato l'elemento.</span><span class="sxs-lookup"><span data-stu-id="0e8a6-193">Set the <xref:System.Windows.Media.RotateTransform.CenterX%2A> and <xref:System.Windows.Media.RotateTransform.CenterY%2A> properties if you want to control the point about which the element is rotated.</span></span> <span data-ttu-id="0e8a6-194">Questi valori di proprietà sono espressi nello spazio delle coordinate dell'elemento trasformato.</span><span class="sxs-lookup"><span data-stu-id="0e8a6-194">These property values are expressed in the coordinate space of the element being transformed.</span></span> <span data-ttu-id="0e8a6-195"><xref:System.Windows.Media.RotateTransform.CenterX%2A>e <xref:System.Windows.Media.RotateTransform.CenterY%2A> hanno valori predefiniti pari a zero.</span><span class="sxs-lookup"><span data-stu-id="0e8a6-195"><xref:System.Windows.Media.RotateTransform.CenterX%2A> and <xref:System.Windows.Media.RotateTransform.CenterY%2A> have default values of zero.</span></span> <span data-ttu-id="0e8a6-196">Infine, applicare all' <xref:System.Windows.Media.RotateTransform> elemento.</span><span class="sxs-lookup"><span data-stu-id="0e8a6-196">Finally, apply the <xref:System.Windows.Media.RotateTransform> to the element.</span></span> <span data-ttu-id="0e8a6-197">Se non si desidera che la trasformazione influisca sul layout, impostare la <xref:System.Windows.UIElement.RenderTransform%2A> proprietà della forma.</span><span class="sxs-lookup"><span data-stu-id="0e8a6-197">If you don't want the transform to affect layout, set the shape's <xref:System.Windows.UIElement.RenderTransform%2A> property.</span></span>  
  
 <span data-ttu-id="0e8a6-198">Nell'esempio seguente <xref:System.Windows.Media.RotateTransform> viene usato un oggetto per ruotare una forma 45 gradi sull'angolo superiore sinistro della forma (0,0).</span><span class="sxs-lookup"><span data-stu-id="0e8a6-198">In the following example, a <xref:System.Windows.Media.RotateTransform> is used to rotate a shape 45 degrees about the shape's top left corner (0,0).</span></span>  
  
 [!code-xaml[transformssample#14](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/RotateTransformExample.xaml#14)]  
  
 <span data-ttu-id="0e8a6-199">Nell'esempio successivo un'altra forma viene ruotata di 45 gradi, ma in questo caso rispetto al punto (25,50).</span><span class="sxs-lookup"><span data-stu-id="0e8a6-199">In the next example, another shape is rotated 45 degrees, but this time it's rotated about the point (25,50).</span></span>  
  
 [!code-xaml[transformssample#15](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/RotateTransformExample.xaml#15)]  
  
 <span data-ttu-id="0e8a6-200">L'immagine seguente illustra i risultati dell'applicazione delle due trasformazioni.</span><span class="sxs-lookup"><span data-stu-id="0e8a6-200">The following illustration shows the results of applying the two transforms.</span></span>  
  
 <span data-ttu-id="0e8a6-201">![Rotazioni di 45 gradi con punti centrali diversi](./media/wcpsdk-graphicsmm-rotatetransform45degrees.gif "wcpsdk_graphicsmm_rotatetransform45degrees")</span><span class="sxs-lookup"><span data-stu-id="0e8a6-201">![45 degree rotations with different center points](./media/wcpsdk-graphicsmm-rotatetransform45degrees.gif "wcpsdk_graphicsmm_rotatetransform45degrees")</span></span>  
  
 <span data-ttu-id="0e8a6-202">Negli esempi precedenti è stata applicata una sola trasformazione a ogni oggetto Shape.</span><span class="sxs-lookup"><span data-stu-id="0e8a6-202">In the previous examples, a single transform was applied to each shape object.</span></span> <span data-ttu-id="0e8a6-203">Per applicare più trasformazioni a una forma (o a qualsiasi altro elemento dell'interfaccia utente), usare un oggetto <xref:System.Windows.Media.TransformGroup> .</span><span class="sxs-lookup"><span data-stu-id="0e8a6-203">To apply multiple transforms to a shape (or any other UI element), use a <xref:System.Windows.Media.TransformGroup>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e8a6-204">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0e8a6-204">See also</span></span>

- [<span data-ttu-id="0e8a6-205">Grafica 2D e creazione di immagini</span><span class="sxs-lookup"><span data-stu-id="0e8a6-205">2D Graphics and Imaging</span></span>](../advanced/optimizing-performance-2d-graphics-and-imaging.md)
- [<span data-ttu-id="0e8a6-206">Cenni sul disegno con colori a tinta unita e sfumature</span><span class="sxs-lookup"><span data-stu-id="0e8a6-206">Painting with Solid Colors and Gradients Overview</span></span>](painting-with-solid-colors-and-gradients-overview.md)
- [<span data-ttu-id="0e8a6-207">Cenni preliminari sulle classi Geometry</span><span class="sxs-lookup"><span data-stu-id="0e8a6-207">Geometry Overview</span></span>](geometry-overview.md)
- [<span data-ttu-id="0e8a6-208">Procedura dettagliata: Prima applicazione desktop WPF</span><span class="sxs-lookup"><span data-stu-id="0e8a6-208">Walkthrough: My first WPF desktop application</span></span>](../getting-started/walkthrough-my-first-wpf-desktop-application.md)
- [<span data-ttu-id="0e8a6-209">Cenni preliminari sull'animazione</span><span class="sxs-lookup"><span data-stu-id="0e8a6-209">Animation Overview</span></span>](animation-overview.md)
