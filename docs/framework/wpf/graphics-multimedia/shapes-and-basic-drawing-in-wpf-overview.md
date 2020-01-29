---
title: Cenni preliminari sulla progettazione di forme e di base
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
ms.openlocfilehash: dfdbf67d35cbb13e80d0c5184f165b0cc660e2ef
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76731618"
---
# <a name="shapes-and-basic-drawing-in-wpf-overview"></a><span data-ttu-id="7689a-102">Cenni preliminari sugli oggetti Shape e sulle funzionalità di disegno di base di WPF</span><span class="sxs-lookup"><span data-stu-id="7689a-102">Shapes and Basic Drawing in WPF Overview</span></span>
<span data-ttu-id="7689a-103">Questo argomento fornisce una panoramica di come creare oggetti con <xref:System.Windows.Shapes.Shape>.</span><span class="sxs-lookup"><span data-stu-id="7689a-103">This topic gives an overview of how to draw with <xref:System.Windows.Shapes.Shape> objects.</span></span> <span data-ttu-id="7689a-104">Un <xref:System.Windows.Shapes.Shape> è un tipo di <xref:System.Windows.UIElement> che consente di disegnare una forma sullo schermo.</span><span class="sxs-lookup"><span data-stu-id="7689a-104">A <xref:System.Windows.Shapes.Shape> is a type of <xref:System.Windows.UIElement> that enables you to draw a shape to the screen.</span></span> <span data-ttu-id="7689a-105">Poiché si tratta di elementi dell'interfaccia utente, <xref:System.Windows.Shapes.Shape> gli oggetti possono essere utilizzati all'interno di <xref:System.Windows.Controls.Panel> elementi e la maggior parte dei controlli.</span><span class="sxs-lookup"><span data-stu-id="7689a-105">Because they are UI elements, <xref:System.Windows.Shapes.Shape> objects can be used inside <xref:System.Windows.Controls.Panel> elements and most controls.</span></span>  
  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <span data-ttu-id="7689a-106">offre diversi livelli di accesso alla grafica e ai servizi di rendering.</span><span class="sxs-lookup"><span data-stu-id="7689a-106">offers several layers of access to graphics and rendering services.</span></span> <span data-ttu-id="7689a-107">Al livello superiore, gli oggetti <xref:System.Windows.Shapes.Shape> sono facili da usare e offrono numerose funzionalità utili, ad esempio il layout e la partecipazione al sistema di [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] eventi.</span><span class="sxs-lookup"><span data-stu-id="7689a-107">At the top layer, <xref:System.Windows.Shapes.Shape> objects are easy to use and provide many useful features, such as layout and participation in the [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] event system.</span></span>  

<a name="shapes"></a>   
## <a name="shape-objects"></a><span data-ttu-id="7689a-108">Oggetti Shape</span><span class="sxs-lookup"><span data-stu-id="7689a-108">Shape Objects</span></span>  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <span data-ttu-id="7689a-109">fornisce una serie di oggetti <xref:System.Windows.Shapes.Shape> pronti per l'uso.</span><span class="sxs-lookup"><span data-stu-id="7689a-109">provides a number of ready-to-use <xref:System.Windows.Shapes.Shape> objects.</span></span>  <span data-ttu-id="7689a-110">Tutti gli oggetti Shape ereditano dalla classe <xref:System.Windows.Shapes.Shape>.</span><span class="sxs-lookup"><span data-stu-id="7689a-110">All shape objects inherit from the <xref:System.Windows.Shapes.Shape> class.</span></span> <span data-ttu-id="7689a-111">Gli oggetti Shape disponibili includono <xref:System.Windows.Shapes.Ellipse>, <xref:System.Windows.Shapes.Line>, <xref:System.Windows.Shapes.Path>, <xref:System.Windows.Shapes.Polygon>, <xref:System.Windows.Shapes.Polyline>e <xref:System.Windows.Shapes.Rectangle>.</span><span class="sxs-lookup"><span data-stu-id="7689a-111">Available shape objects include <xref:System.Windows.Shapes.Ellipse>, <xref:System.Windows.Shapes.Line>, <xref:System.Windows.Shapes.Path>, <xref:System.Windows.Shapes.Polygon>, <xref:System.Windows.Shapes.Polyline>, and <xref:System.Windows.Shapes.Rectangle>.</span></span> <span data-ttu-id="7689a-112">gli oggetti <xref:System.Windows.Shapes.Shape> condividono le seguenti proprietà comuni.</span><span class="sxs-lookup"><span data-stu-id="7689a-112"><xref:System.Windows.Shapes.Shape> objects share the following common properties.</span></span>  
  
- <span data-ttu-id="7689a-113"><xref:System.Windows.Shapes.Shape.Stroke%2A>: descrive il modo in cui viene disegnato il contorno della forma.</span><span class="sxs-lookup"><span data-stu-id="7689a-113"><xref:System.Windows.Shapes.Shape.Stroke%2A>: Describes how the shape's outline is painted.</span></span>  
  
- <span data-ttu-id="7689a-114"><xref:System.Windows.Shapes.Shape.StrokeThickness%2A>: descrive lo spessore del contorno della forma.</span><span class="sxs-lookup"><span data-stu-id="7689a-114"><xref:System.Windows.Shapes.Shape.StrokeThickness%2A>: Describes the thickness of the shape's outline.</span></span>  
  
- <span data-ttu-id="7689a-115"><xref:System.Windows.Shapes.Shape.Fill%2A>: descrive il modo in cui viene disegnata l'area interna della forma.</span><span class="sxs-lookup"><span data-stu-id="7689a-115"><xref:System.Windows.Shapes.Shape.Fill%2A>: Describes how the interior of the shape is painted.</span></span>  
  
- <span data-ttu-id="7689a-116">Proprietà dei dati per specificare coordinate e vertici, misurati in pixel indipendenti dal dispositivo.</span><span class="sxs-lookup"><span data-stu-id="7689a-116">Data properties to specify coordinates and vertices, measured in device-independent pixels.</span></span>  
  
 <span data-ttu-id="7689a-117">Poiché derivano da <xref:System.Windows.UIElement>, gli oggetti Shape possono essere utilizzati nei pannelli e nella maggior parte dei controlli.</span><span class="sxs-lookup"><span data-stu-id="7689a-117">Because they derive from <xref:System.Windows.UIElement>, shape objects can be used inside panels and most controls.</span></span> <span data-ttu-id="7689a-118">Il pannello <xref:System.Windows.Controls.Canvas> rappresenta una scelta particolarmente utile per la creazione di disegni complessi, perché supporta il posizionamento assoluto dei relativi oggetti figlio.</span><span class="sxs-lookup"><span data-stu-id="7689a-118">The <xref:System.Windows.Controls.Canvas> panel is a particularly good choice for creating complex drawings because it supports absolute positioning of its child objects.</span></span>  
  
 <span data-ttu-id="7689a-119">La classe <xref:System.Windows.Shapes.Line> consente di creare una linea tra due punti.</span><span class="sxs-lookup"><span data-stu-id="7689a-119">The <xref:System.Windows.Shapes.Line> class enables you to draw a line between two points.</span></span> <span data-ttu-id="7689a-120">L'esempio seguente illustra molti modi per specificare le coordinate della riga e le proprietà del tratto.</span><span class="sxs-lookup"><span data-stu-id="7689a-120">The following example shows several ways to specify line coordinates and stroke properties.</span></span>  
  
 [!code-xaml[drawingwithshapeelements#LineExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/lineexample.xaml#lineexample1)]  
  
 [!code-cpp[shapesprocedural#ShapesProceduralLine](~/samples/snippets/cpp/VS_Snippets_Wpf/ShapesProcedural/CPP/ShapesProcedural.cpp#shapesproceduralline)]
 [!code-csharp[shapesprocedural#ShapesProceduralLine](~/samples/snippets/csharp/VS_Snippets_Wpf/ShapesProcedural/Csharp/ShapesProcedural.cs#shapesproceduralline)]
 [!code-vb[shapesprocedural#ShapesProceduralLine](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ShapesProcedural/VisualBasic/ShapesProceduralVB.vb#shapesproceduralline)]  
  
 <span data-ttu-id="7689a-121">Nell'immagine seguente viene illustrata la <xref:System.Windows.Shapes.Line>sottoposta a rendering.</span><span class="sxs-lookup"><span data-stu-id="7689a-121">The following image shows the rendered <xref:System.Windows.Shapes.Line>.</span></span>  
  
 <span data-ttu-id="7689a-122">![Illustrazione linea](./media/shape-ovw-line2.gif "shape_ovw_line2")</span><span class="sxs-lookup"><span data-stu-id="7689a-122">![Line illustration](./media/shape-ovw-line2.gif "shape_ovw_line2")</span></span>  
  
 <span data-ttu-id="7689a-123">Sebbene la classe <xref:System.Windows.Shapes.Line> fornisca una proprietà <xref:System.Windows.Shapes.Shape.Fill%2A>, l'impostazione non produce alcun effetto perché una <xref:System.Windows.Shapes.Line> non ha alcuna area.</span><span class="sxs-lookup"><span data-stu-id="7689a-123">Although the <xref:System.Windows.Shapes.Line> class does provide a <xref:System.Windows.Shapes.Shape.Fill%2A> property, setting it has no effect because a <xref:System.Windows.Shapes.Line> has no area.</span></span>  
  
 <span data-ttu-id="7689a-124">Un'altra forma comune è la <xref:System.Windows.Shapes.Ellipse>.</span><span class="sxs-lookup"><span data-stu-id="7689a-124">Another common shape is the <xref:System.Windows.Shapes.Ellipse>.</span></span>  <span data-ttu-id="7689a-125">Creare una <xref:System.Windows.Shapes.Ellipse> definendo le proprietà <xref:System.Windows.FrameworkElement.Width%2A> e <xref:System.Windows.FrameworkElement.Height%2A> della forma.</span><span class="sxs-lookup"><span data-stu-id="7689a-125">Create an <xref:System.Windows.Shapes.Ellipse> by defining the shape's <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties.</span></span> <span data-ttu-id="7689a-126">Per creare un cerchio, specificare un <xref:System.Windows.Shapes.Ellipse> i cui valori di <xref:System.Windows.FrameworkElement.Width%2A> e <xref:System.Windows.FrameworkElement.Height%2A> siano uguali.</span><span class="sxs-lookup"><span data-stu-id="7689a-126">To draw a circle, specify an <xref:System.Windows.Shapes.Ellipse> whose <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> values are equal.</span></span>  
  
 [!code-xaml[ShapeOverviews#ShapesOVW1](~/samples/snippets/csharp/VS_Snippets_Wpf/ShapeOverviews/CS/Window1.xaml#shapesovw1)]  
  
 [!code-csharp[brushesmiscsnippets_procedural_snip#SetBackgroundColorOfShapeCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesMiscSnippets_procedural_snip/CSharp/SetBackgroundColorOfShapeExample.cs#setbackgroundcolorofshapecodeexamplewholepage)]
 [!code-vb[brushesmiscsnippets_procedural_snip#SetBackgroundColorOfShapeCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesMiscSnippets_procedural_snip/visualbasic/setbackgroundcolorofshapeexample.vb#setbackgroundcolorofshapecodeexamplewholepage)]  
  
 <span data-ttu-id="7689a-127">Nell'immagine seguente viene illustrato un esempio di un <xref:System.Windows.Shapes.Ellipse>sottoposto a rendering.</span><span class="sxs-lookup"><span data-stu-id="7689a-127">The following image shows an example of a rendered <xref:System.Windows.Shapes.Ellipse>.</span></span>  
  
 <span data-ttu-id="7689a-128">![Illustrazione ellisse](./media/shape-ovw-ellipse2.png "shape_ovw_ellipse2")</span><span class="sxs-lookup"><span data-stu-id="7689a-128">![Ellipse illustration](./media/shape-ovw-ellipse2.png "shape_ovw_ellipse2")</span></span>  
  
<a name="paths"></a>   
## <a name="using-paths-and-geometries"></a><span data-ttu-id="7689a-129">Utilizzo di tracciati e geometrie</span><span class="sxs-lookup"><span data-stu-id="7689a-129">Using Paths and Geometries</span></span>  
 <span data-ttu-id="7689a-130">La classe <xref:System.Windows.Shapes.Path> consente di creare curve e forme complesse.</span><span class="sxs-lookup"><span data-stu-id="7689a-130">The <xref:System.Windows.Shapes.Path> class enables you to draw curves and complex shapes.</span></span> <span data-ttu-id="7689a-131">Queste curve e forme vengono descritte utilizzando <xref:System.Windows.Media.Geometry> oggetti.</span><span class="sxs-lookup"><span data-stu-id="7689a-131">These curves and shapes are described using <xref:System.Windows.Media.Geometry> objects.</span></span> <span data-ttu-id="7689a-132">Per utilizzare una <xref:System.Windows.Shapes.Path>, è necessario creare un <xref:System.Windows.Media.Geometry> e utilizzarlo per impostare la proprietà <xref:System.Windows.Shapes.Path.Data%2A> dell'oggetto <xref:System.Windows.Shapes.Path>.</span><span class="sxs-lookup"><span data-stu-id="7689a-132">To use a <xref:System.Windows.Shapes.Path>, you create a <xref:System.Windows.Media.Geometry> and use it to set the <xref:System.Windows.Shapes.Path> object's <xref:System.Windows.Shapes.Path.Data%2A> property.</span></span>  
  
 <span data-ttu-id="7689a-133">È possibile scegliere tra diversi oggetti <xref:System.Windows.Media.Geometry>.</span><span class="sxs-lookup"><span data-stu-id="7689a-133">There are a variety of <xref:System.Windows.Media.Geometry> objects to choose from.</span></span> <span data-ttu-id="7689a-134">Le classi <xref:System.Windows.Media.LineGeometry>, <xref:System.Windows.Media.RectangleGeometry>e <xref:System.Windows.Media.EllipseGeometry> descrivono forme relativamente semplici.</span><span class="sxs-lookup"><span data-stu-id="7689a-134">The <xref:System.Windows.Media.LineGeometry>, <xref:System.Windows.Media.RectangleGeometry>, and <xref:System.Windows.Media.EllipseGeometry> classes describe relatively simple shapes.</span></span> <span data-ttu-id="7689a-135">Per creare forme più complesse o creare curve, usare un <xref:System.Windows.Media.PathGeometry>.</span><span class="sxs-lookup"><span data-stu-id="7689a-135">To create more complex shapes or create curves, use a <xref:System.Windows.Media.PathGeometry>.</span></span>  
  
<a name="pathgeometry"></a>   
### <a name="pathgeometry-and-pathsegments"></a><span data-ttu-id="7689a-136">PathGeometry e PathSegments</span><span class="sxs-lookup"><span data-stu-id="7689a-136">PathGeometry and PathSegments</span></span>  
 <span data-ttu-id="7689a-137"><xref:System.Windows.Media.PathGeometry> oggetti sono costituiti da uno o più oggetti <xref:System.Windows.Media.PathFigure>; ogni <xref:System.Windows.Media.PathFigure> rappresenta una "figura" o una forma diversa.</span><span class="sxs-lookup"><span data-stu-id="7689a-137"><xref:System.Windows.Media.PathGeometry> objects are comprised of one or more <xref:System.Windows.Media.PathFigure> objects; each <xref:System.Windows.Media.PathFigure> represents a different "figure" or shape.</span></span> <span data-ttu-id="7689a-138">Ogni <xref:System.Windows.Media.PathFigure> è costituita da uno o più oggetti <xref:System.Windows.Media.PathSegment>, ciascuno dei quali rappresenta una parte connessa della figura o della forma.</span><span class="sxs-lookup"><span data-stu-id="7689a-138">Each <xref:System.Windows.Media.PathFigure> is itself comprised of one or more <xref:System.Windows.Media.PathSegment> objects, each representing a connected portion of the figure or shape.</span></span> <span data-ttu-id="7689a-139">I tipi di segmento includono i seguenti: <xref:System.Windows.Media.LineSegment>, <xref:System.Windows.Media.BezierSegment>e <xref:System.Windows.Media.ArcSegment>.</span><span class="sxs-lookup"><span data-stu-id="7689a-139">Segment types include the following: <xref:System.Windows.Media.LineSegment>, <xref:System.Windows.Media.BezierSegment>, and <xref:System.Windows.Media.ArcSegment>.</span></span>  
  
 <span data-ttu-id="7689a-140">Nell'esempio seguente viene usato un <xref:System.Windows.Shapes.Path> per creare una curva di Bézier quadratica.</span><span class="sxs-lookup"><span data-stu-id="7689a-140">In the following example, a <xref:System.Windows.Shapes.Path> is used to draw a quadratic Bezier curve.</span></span>  
  
 [!code-xaml[geometrysample#34](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#34)]  
  
 <span data-ttu-id="7689a-141">L'immagine seguente illustra la forma sottoposta a rendering.</span><span class="sxs-lookup"><span data-stu-id="7689a-141">The following image shows the rendered shape.</span></span>  
  
 <span data-ttu-id="7689a-142">![Illustrazione del percorso](./media/shape-ovw-path2.gif "shape_ovw_path2")</span><span class="sxs-lookup"><span data-stu-id="7689a-142">![Path illustration](./media/shape-ovw-path2.gif "shape_ovw_path2")</span></span>  
  
 <span data-ttu-id="7689a-143">Per ulteriori informazioni su <xref:System.Windows.Media.PathGeometry> e sulle altre classi <xref:System.Windows.Media.Geometry>, vedere [Cenni preliminari sulla geometria](geometry-overview.md).</span><span class="sxs-lookup"><span data-stu-id="7689a-143">For more information about <xref:System.Windows.Media.PathGeometry> and the other <xref:System.Windows.Media.Geometry> classes, see the [Geometry Overview](geometry-overview.md).</span></span>  
  
<a name="pathdatastring"></a>   
### <a name="xaml-abbreviated-syntax"></a><span data-ttu-id="7689a-144">Sintassi abbreviata XAML</span><span class="sxs-lookup"><span data-stu-id="7689a-144">XAML Abbreviated Syntax</span></span>  
 <span data-ttu-id="7689a-145">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], è anche possibile usare una speciale sintassi abbreviata per descrivere una <xref:System.Windows.Shapes.Path>.</span><span class="sxs-lookup"><span data-stu-id="7689a-145">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], you may also use a special abbreviated syntax to describe a <xref:System.Windows.Shapes.Path>.</span></span> <span data-ttu-id="7689a-146">Nell'esempio seguente viene usata la sintassi abbreviata per disegnare una forma complessa.</span><span class="sxs-lookup"><span data-stu-id="7689a-146">In the following example, abbreviated syntax is used to draw a complex shape.</span></span>  
  
```xaml  
      <Path Stroke="DarkGoldenRod" StrokeThickness="3"   
Data="M 100,200 C 100,25 400,350 400,175 H 280" />  
```  
  
 <span data-ttu-id="7689a-147">Nell'immagine seguente viene illustrata una <xref:System.Windows.Shapes.Path>sottoposta a rendering.</span><span class="sxs-lookup"><span data-stu-id="7689a-147">The following image shows a rendered <xref:System.Windows.Shapes.Path>.</span></span>  
  
 <span data-ttu-id="7689a-148">![Illustrazione del percorso](./media/shape-ovw-path.PNG "shape_ovw_path")</span><span class="sxs-lookup"><span data-stu-id="7689a-148">![Path illustration](./media/shape-ovw-path.PNG "shape_ovw_path")</span></span>  
  
 <span data-ttu-id="7689a-149">La stringa dell'attributo <xref:System.Windows.Shapes.Path.Data%2A> inizia con il comando "MoveTo", indicato da M, che stabilisce un punto iniziale per il percorso nel sistema di coordinate del <xref:System.Windows.Controls.Canvas>.</span><span class="sxs-lookup"><span data-stu-id="7689a-149">The <xref:System.Windows.Shapes.Path.Data%2A> attribute string begins with the "moveto" command, indicated by M, which establishes a start point for the path in the coordinate system of the <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="7689a-150"><xref:System.Windows.Shapes.Path> i parametri dei dati fanno distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="7689a-150"><xref:System.Windows.Shapes.Path> data parameters are case-sensitive.</span></span> <span data-ttu-id="7689a-151">Il valore letterale M indica una posizione assoluta per il nuovo punto corrente.</span><span class="sxs-lookup"><span data-stu-id="7689a-151">The capital M indicates an absolute location for the new current point.</span></span> <span data-ttu-id="7689a-152">Una lettera m minuscola indica le coordinate relative.</span><span class="sxs-lookup"><span data-stu-id="7689a-152">A lowercase m would indicate relative coordinates.</span></span> <span data-ttu-id="7689a-153">Il primo segmento è una curva di Bézier cubica che inizia in corrispondenza del punto (100,200) e termina in corrispondenza del punto (400,175) e viene disegnata usando i due punti di controllo (100,25) e (400,350).</span><span class="sxs-lookup"><span data-stu-id="7689a-153">The first segment is a cubic Bezier curve beginning at (100,200) and ending at (400,175), drawn using the two control points (100,25) and (400,350).</span></span> <span data-ttu-id="7689a-154">Questo segmento è indicato dal comando C nella stringa dell'attributo <xref:System.Windows.Shapes.Path.Data%2A>.</span><span class="sxs-lookup"><span data-stu-id="7689a-154">This segment is indicated by the C command in the <xref:System.Windows.Shapes.Path.Data%2A> attribute string.</span></span> <span data-ttu-id="7689a-155">Anche in questo caso la lettera C maiuscola indica un percorso assoluto, mentre la lettera c minuscola indica un percorso relativo.</span><span class="sxs-lookup"><span data-stu-id="7689a-155">Again, the capital C indicates an absolute path; the lowercase c would indicate a relative path.</span></span>  
  
 <span data-ttu-id="7689a-156">Il secondo segmento inizia con un comando orizzontale assoluto "lineto" H, che specifica una riga disegnata dal punto finale del sottopercorso precedente (400,175) a un nuovo punto finale (280,175).</span><span class="sxs-lookup"><span data-stu-id="7689a-156">The second segment begins with an absolute horizontal "lineto" command H, which specifies a line drawn from the preceding subpath's endpoint (400,175) to a new endpoint (280,175).</span></span> <span data-ttu-id="7689a-157">Poiché si tratta di un comando "lineto" orizzontale, il valore specificato è una coordinata *x*.</span><span class="sxs-lookup"><span data-stu-id="7689a-157">Because it is a horizontal "lineto" command, the value specified is an *x*-coordinate.</span></span>  
  
 <span data-ttu-id="7689a-158">Per la sintassi del percorso completo, vedere il riferimento <xref:System.Windows.Shapes.Path.Data%2A> e [creare una forma usando un oggetto PathGeometry](how-to-create-a-shape-by-using-a-pathgeometry.md).</span><span class="sxs-lookup"><span data-stu-id="7689a-158">For the complete path syntax, see the <xref:System.Windows.Shapes.Path.Data%2A> reference and [Create a Shape by Using a PathGeometry](how-to-create-a-shape-by-using-a-pathgeometry.md).</span></span>  
  
<a name="fillpaint"></a>   
## <a name="painting-shapes"></a><span data-ttu-id="7689a-159">Disegno di oggetti Shape</span><span class="sxs-lookup"><span data-stu-id="7689a-159">Painting Shapes</span></span>  
 <span data-ttu-id="7689a-160">gli oggetti <xref:System.Windows.Media.Brush> vengono utilizzati per disegnare <xref:System.Windows.Shapes.Shape.Stroke%2A> e <xref:System.Windows.Shapes.Shape.Fill%2A>di una forma.</span><span class="sxs-lookup"><span data-stu-id="7689a-160"><xref:System.Windows.Media.Brush> objects are used to paint a shape's <xref:System.Windows.Shapes.Shape.Stroke%2A> and <xref:System.Windows.Shapes.Shape.Fill%2A>.</span></span> <span data-ttu-id="7689a-161">Nell'esempio seguente vengono specificati il tratto e il riempimento di un <xref:System.Windows.Shapes.Ellipse>.</span><span class="sxs-lookup"><span data-stu-id="7689a-161">In the following example, the stroke and fill of an <xref:System.Windows.Shapes.Ellipse> are specified.</span></span> <span data-ttu-id="7689a-162">Si noti che un input valido per le proprietà del pennello può essere rappresentato da una parola chiave o da un valore di colore esadecimale.</span><span class="sxs-lookup"><span data-stu-id="7689a-162">Note that valid input for brush properties can be either a keyword or hexadecimal color value.</span></span> <span data-ttu-id="7689a-163">Per ulteriori informazioni sulle parole chiave dei colori disponibili, vedere Proprietà della classe <xref:System.Windows.Media.Colors> nello spazio dei nomi <xref:System.Windows.Media>.</span><span class="sxs-lookup"><span data-stu-id="7689a-163">For more information about available color keywords, see properties of the <xref:System.Windows.Media.Colors> class in the <xref:System.Windows.Media> namespace.</span></span>  
  
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
  
 <span data-ttu-id="7689a-164">Nell'immagine seguente viene illustrata la <xref:System.Windows.Shapes.Ellipse>sottoposta a rendering.</span><span class="sxs-lookup"><span data-stu-id="7689a-164">The following image shows the rendered <xref:System.Windows.Shapes.Ellipse>.</span></span>  
  
 <span data-ttu-id="7689a-165">![Ellisse](./media/shape-ovw-ellipsefill.PNG "shape_ovw_ellipsefill")</span><span class="sxs-lookup"><span data-stu-id="7689a-165">![An ellipse](./media/shape-ovw-ellipsefill.PNG "shape_ovw_ellipsefill")</span></span>  
  
 <span data-ttu-id="7689a-166">In alternativa, è possibile utilizzare la sintassi dell'elemento proprietà per creare in modo esplicito un oggetto <xref:System.Windows.Media.SolidColorBrush> per disegnare la forma con un colore a tinta unita.</span><span class="sxs-lookup"><span data-stu-id="7689a-166">Alternatively, you can use property element syntax to explicitly create a <xref:System.Windows.Media.SolidColorBrush> object to paint the shape with a solid color.</span></span>  
  
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
  
 <span data-ttu-id="7689a-167">La figura seguente mostra la forma sottoposta a rendering.</span><span class="sxs-lookup"><span data-stu-id="7689a-167">The following illustration shows the rendered shape.</span></span>  
  
 <span data-ttu-id="7689a-168">![Illustrazione di SolidColorBrush](./media/shape-ovw-solidcolorbrush.PNG "shape_ovw_solidcolorbrush")</span><span class="sxs-lookup"><span data-stu-id="7689a-168">![SolidColorBrush illustration](./media/shape-ovw-solidcolorbrush.PNG "shape_ovw_solidcolorbrush")</span></span>  
  
 <span data-ttu-id="7689a-169">È anche possibile disegnare il tratto o il riempimento di una forma con sfumature, immagini, motivi e così via.</span><span class="sxs-lookup"><span data-stu-id="7689a-169">You can also paint a shape's stroke or fill with gradients, images, patterns, and more.</span></span> <span data-ttu-id="7689a-170">Per ulteriori informazioni, vedere [Cenni preliminari sul disegno con colori a tinta unita e sfumature](painting-with-solid-colors-and-gradients-overview.md).</span><span class="sxs-lookup"><span data-stu-id="7689a-170">For more information, see the [Painting with Solid Colors and Gradients Overview](painting-with-solid-colors-and-gradients-overview.md).</span></span>  
  
<a name="stretchableshapessection"></a>   
## <a name="stretchable-shapes"></a><span data-ttu-id="7689a-171">Oggetti Shape allungabili</span><span class="sxs-lookup"><span data-stu-id="7689a-171">Stretchable Shapes</span></span>  
 <span data-ttu-id="7689a-172">Le classi <xref:System.Windows.Shapes.Line>, <xref:System.Windows.Shapes.Path>, <xref:System.Windows.Shapes.Polygon>, <xref:System.Windows.Shapes.Polyline>e <xref:System.Windows.Shapes.Rectangle> dispongono tutti di una proprietà <xref:System.Windows.Shapes.Shape.Stretch%2A>.</span><span class="sxs-lookup"><span data-stu-id="7689a-172">The <xref:System.Windows.Shapes.Line>, <xref:System.Windows.Shapes.Path>, <xref:System.Windows.Shapes.Polygon>, <xref:System.Windows.Shapes.Polyline>, and <xref:System.Windows.Shapes.Rectangle> classes all have a <xref:System.Windows.Shapes.Shape.Stretch%2A> property.</span></span> <span data-ttu-id="7689a-173">Questa proprietà determina il modo in cui il contenuto di un oggetto <xref:System.Windows.Shapes.Shape> (la forma da disegnare) viene allungato per riempire lo spazio del layout dell'oggetto <xref:System.Windows.Shapes.Shape>.</span><span class="sxs-lookup"><span data-stu-id="7689a-173">This property determines how a <xref:System.Windows.Shapes.Shape> object's contents (the shape to be drawn) is stretched to fill the <xref:System.Windows.Shapes.Shape> object's layout space.</span></span> <span data-ttu-id="7689a-174">Lo spazio di layout di un oggetto <xref:System.Windows.Shapes.Shape> è la quantità di spazio che il <xref:System.Windows.Shapes.Shape> alloca dal sistema di layout, a causa di un'impostazione esplicita di <xref:System.Windows.FrameworkElement.Width%2A> e di <xref:System.Windows.FrameworkElement.Height%2A> oppure a causa delle impostazioni <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> e <xref:System.Windows.FrameworkElement.VerticalAlignment%2A>.</span><span class="sxs-lookup"><span data-stu-id="7689a-174">A <xref:System.Windows.Shapes.Shape> object's layout space is the amount of space the <xref:System.Windows.Shapes.Shape> is allocated by the layout system, because of either an explicit <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> setting or because of its <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> and <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> settings.</span></span> <span data-ttu-id="7689a-175">Per altre informazioni sul layout in Windows Presentation Foundation, vedere Cenni preliminari sul [layout](../advanced/layout.md) .</span><span class="sxs-lookup"><span data-stu-id="7689a-175">For additional information on layout in Windows Presentation Foundation, see [Layout](../advanced/layout.md) overview.</span></span>  
  
 <span data-ttu-id="7689a-176">La proprietà Stretch accetta uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="7689a-176">The Stretch property takes one of the following values:</span></span>  
  
- <span data-ttu-id="7689a-177"><xref:System.Windows.Media.Stretch.None>: il contenuto dell'oggetto <xref:System.Windows.Shapes.Shape> non viene allungato.</span><span class="sxs-lookup"><span data-stu-id="7689a-177"><xref:System.Windows.Media.Stretch.None>: The <xref:System.Windows.Shapes.Shape> object's contents are not stretched.</span></span>  
  
- <span data-ttu-id="7689a-178"><xref:System.Windows.Media.Stretch.Fill>: il contenuto dell'oggetto <xref:System.Windows.Shapes.Shape> viene allungato per riempire lo spazio del layout.</span><span class="sxs-lookup"><span data-stu-id="7689a-178"><xref:System.Windows.Media.Stretch.Fill>: The <xref:System.Windows.Shapes.Shape> object's contents are stretched to fill its layout space.</span></span>  <span data-ttu-id="7689a-179">Le proporzioni non vengono mantenute.</span><span class="sxs-lookup"><span data-stu-id="7689a-179">Aspect ratio is not preserved.</span></span>  
  
- <span data-ttu-id="7689a-180"><xref:System.Windows.Media.Stretch.Uniform>: il contenuto dell'oggetto <xref:System.Windows.Shapes.Shape> viene allungato il più possibile per riempire lo spazio del layout mantenendo le proporzioni originali.</span><span class="sxs-lookup"><span data-stu-id="7689a-180"><xref:System.Windows.Media.Stretch.Uniform>: The <xref:System.Windows.Shapes.Shape> object's contents are stretched as much as possible to fill its layout space while preserving its original aspect ratio.</span></span>  
  
- <span data-ttu-id="7689a-181"><xref:System.Windows.Media.Stretch.UniformToFill>: il contenuto dell'oggetto <xref:System.Windows.Shapes.Shape> viene allungato per riempire completamente lo spazio del layout mantenendo le proporzioni originali.</span><span class="sxs-lookup"><span data-stu-id="7689a-181"><xref:System.Windows.Media.Stretch.UniformToFill>: The <xref:System.Windows.Shapes.Shape> object's contents are stretched to completely fill its layout space while preserving its original aspect ratio.</span></span>  
  
 <span data-ttu-id="7689a-182">Si noti che, quando il contenuto di un oggetto <xref:System.Windows.Shapes.Shape> viene allungato, il contorno dell'oggetto <xref:System.Windows.Shapes.Shape> viene disegnato dopo l'estensione.</span><span class="sxs-lookup"><span data-stu-id="7689a-182">Note that, when a <xref:System.Windows.Shapes.Shape> object's contents are stretched, the <xref:System.Windows.Shapes.Shape> object's outline is painted after the stretching.</span></span>  
  
 <span data-ttu-id="7689a-183">Nell'esempio seguente viene usato un <xref:System.Windows.Shapes.Polygon> per creare un triangolo molto piccolo da (0,0) a (0, 1) a (1,1).</span><span class="sxs-lookup"><span data-stu-id="7689a-183">In the following example, a <xref:System.Windows.Shapes.Polygon> is used to draw a very small triangle from (0,0) to (0,1) to (1,1).</span></span> <span data-ttu-id="7689a-184">Il <xref:System.Windows.FrameworkElement.Width%2A> e la <xref:System.Windows.FrameworkElement.Height%2A> dell'oggetto <xref:System.Windows.Shapes.Polygon> sono impostati su 100 e la relativa proprietà Stretch è impostata su Fill.</span><span class="sxs-lookup"><span data-stu-id="7689a-184">The <xref:System.Windows.Shapes.Polygon> object's <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> are set to 100, and its stretch property is set to Fill.</span></span> <span data-ttu-id="7689a-185">Di conseguenza, il contenuto dell'oggetto <xref:System.Windows.Shapes.Polygon> (il triangolo) viene allungato per riempire lo spazio più grande.</span><span class="sxs-lookup"><span data-stu-id="7689a-185">As a result, the <xref:System.Windows.Shapes.Polygon> object's contents (the triangle) are stretched to fill the larger space.</span></span>  
  
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
## <a name="transforming-shapes"></a><span data-ttu-id="7689a-186">Trasformazione degli oggetti Shape</span><span class="sxs-lookup"><span data-stu-id="7689a-186">Transforming Shapes</span></span>  
 <span data-ttu-id="7689a-187">La classe <xref:System.Windows.Media.Transform> fornisce i mezzi per trasformare le forme in un piano bidimensionale.</span><span class="sxs-lookup"><span data-stu-id="7689a-187">The <xref:System.Windows.Media.Transform> class provides the means to transform shapes in a two-dimensional plane.</span></span>  <span data-ttu-id="7689a-188">I diversi tipi di trasformazione includono Rotation (<xref:System.Windows.Media.RotateTransform>), scale (<xref:System.Windows.Media.ScaleTransform>), asimmetria (<xref:System.Windows.Media.SkewTransform>) e Translation (<xref:System.Windows.Media.TranslateTransform>).</span><span class="sxs-lookup"><span data-stu-id="7689a-188">The different types of transformation include rotation (<xref:System.Windows.Media.RotateTransform>), scale (<xref:System.Windows.Media.ScaleTransform>), skew (<xref:System.Windows.Media.SkewTransform>), and translation (<xref:System.Windows.Media.TranslateTransform>).</span></span>  
  
 <span data-ttu-id="7689a-189">Una trasformazione comune da applicare a una forma è una rotazione.</span><span class="sxs-lookup"><span data-stu-id="7689a-189">A common transform to apply to a shape is a rotation.</span></span>  <span data-ttu-id="7689a-190">Per ruotare una forma, creare una <xref:System.Windows.Media.RotateTransform> e specificarne la <xref:System.Windows.Media.RotateTransform.Angle%2A>.</span><span class="sxs-lookup"><span data-stu-id="7689a-190">To rotate a shape, create a <xref:System.Windows.Media.RotateTransform> and specify its <xref:System.Windows.Media.RotateTransform.Angle%2A>.</span></span> <span data-ttu-id="7689a-191">Un <xref:System.Windows.Media.RotateTransform.Angle%2A> di 45 ruota l'elemento 45 gradi in senso orario; un angolo di 90 ruota l'elemento 90 gradi in senso orario; E così via.</span><span class="sxs-lookup"><span data-stu-id="7689a-191">An <xref:System.Windows.Media.RotateTransform.Angle%2A> of 45 rotates the element 45 degrees clockwise; an angle of 90 rotates the element 90 degrees clockwise; and so on.</span></span> <span data-ttu-id="7689a-192">Impostare le proprietà <xref:System.Windows.Media.RotateTransform.CenterX%2A> e <xref:System.Windows.Media.RotateTransform.CenterY%2A> se si desidera controllare il punto in cui viene ruotato l'elemento.</span><span class="sxs-lookup"><span data-stu-id="7689a-192">Set the <xref:System.Windows.Media.RotateTransform.CenterX%2A> and <xref:System.Windows.Media.RotateTransform.CenterY%2A> properties if you want to control the point about which the element is rotated.</span></span> <span data-ttu-id="7689a-193">Questi valori di proprietà sono espressi nello spazio delle coordinate dell'elemento trasformato.</span><span class="sxs-lookup"><span data-stu-id="7689a-193">These property values are expressed in the coordinate space of the element being transformed.</span></span> <span data-ttu-id="7689a-194"><xref:System.Windows.Media.RotateTransform.CenterX%2A> e <xref:System.Windows.Media.RotateTransform.CenterY%2A> hanno valori predefiniti pari a zero.</span><span class="sxs-lookup"><span data-stu-id="7689a-194"><xref:System.Windows.Media.RotateTransform.CenterX%2A> and <xref:System.Windows.Media.RotateTransform.CenterY%2A> have default values of zero.</span></span> <span data-ttu-id="7689a-195">Infine, applicare la <xref:System.Windows.Media.RotateTransform> all'elemento.</span><span class="sxs-lookup"><span data-stu-id="7689a-195">Finally, apply the <xref:System.Windows.Media.RotateTransform> to the element.</span></span> <span data-ttu-id="7689a-196">Se non si desidera che la trasformazione influisca sul layout, impostare la proprietà <xref:System.Windows.UIElement.RenderTransform%2A> della forma.</span><span class="sxs-lookup"><span data-stu-id="7689a-196">If you don't want the transform to affect layout, set the shape's <xref:System.Windows.UIElement.RenderTransform%2A> property.</span></span>  
  
 <span data-ttu-id="7689a-197">Nell'esempio seguente viene usato un <xref:System.Windows.Media.RotateTransform> per ruotare una forma 45 gradi sull'angolo superiore sinistro della forma (0,0).</span><span class="sxs-lookup"><span data-stu-id="7689a-197">In the following example, a <xref:System.Windows.Media.RotateTransform> is used to rotate a shape 45 degrees about the shape's top left corner (0,0).</span></span>  
  
 [!code-xaml[transformssample#14](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/RotateTransformExample.xaml#14)]  
  
 <span data-ttu-id="7689a-198">Nell'esempio successivo un'altra forma viene ruotata di 45 gradi, ma in questo caso rispetto al punto (25,50).</span><span class="sxs-lookup"><span data-stu-id="7689a-198">In the next example, another shape is rotated 45 degrees, but this time it's rotated about the point (25,50).</span></span>  
  
 [!code-xaml[transformssample#15](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/RotateTransformExample.xaml#15)]  
  
 <span data-ttu-id="7689a-199">L'immagine seguente illustra i risultati dell'applicazione delle due trasformazioni.</span><span class="sxs-lookup"><span data-stu-id="7689a-199">The following illustration shows the results of applying the two transforms.</span></span>  
  
 <span data-ttu-id="7689a-200">![Rotazioni di 45 gradi con punti centrali diversi](./media/wcpsdk-graphicsmm-rotatetransform45degrees.gif "wcpsdk_graphicsmm_rotatetransform45degrees")</span><span class="sxs-lookup"><span data-stu-id="7689a-200">![45 degree rotations with different center points](./media/wcpsdk-graphicsmm-rotatetransform45degrees.gif "wcpsdk_graphicsmm_rotatetransform45degrees")</span></span>  
  
 <span data-ttu-id="7689a-201">Negli esempi precedenti è stata applicata una sola trasformazione a ogni oggetto Shape.</span><span class="sxs-lookup"><span data-stu-id="7689a-201">In the previous examples, a single transform was applied to each shape object.</span></span> <span data-ttu-id="7689a-202">Per applicare più trasformazioni a una forma (o a qualsiasi altro elemento dell'interfaccia utente), usare un <xref:System.Windows.Media.TransformGroup>.</span><span class="sxs-lookup"><span data-stu-id="7689a-202">To apply multiple transforms to a shape (or any other UI element), use a <xref:System.Windows.Media.TransformGroup>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7689a-203">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7689a-203">See also</span></span>

- [<span data-ttu-id="7689a-204">Grafica bidimensionale e creazione di immagini</span><span class="sxs-lookup"><span data-stu-id="7689a-204">2D Graphics and Imaging</span></span>](../advanced/optimizing-performance-2d-graphics-and-imaging.md)
- [<span data-ttu-id="7689a-205">Cenni sul disegno con colori a tinta unita e sfumature</span><span class="sxs-lookup"><span data-stu-id="7689a-205">Painting with Solid Colors and Gradients Overview</span></span>](painting-with-solid-colors-and-gradients-overview.md)
- [<span data-ttu-id="7689a-206">Cenni preliminari sulle classi Geometry</span><span class="sxs-lookup"><span data-stu-id="7689a-206">Geometry Overview</span></span>](geometry-overview.md)
- [<span data-ttu-id="7689a-207">Procedura dettagliata: Prima applicazione desktop WPF</span><span class="sxs-lookup"><span data-stu-id="7689a-207">Walkthrough: My first WPF desktop application</span></span>](../getting-started/walkthrough-my-first-wpf-desktop-application.md)
- [<span data-ttu-id="7689a-208">Cenni preliminari sull'animazione</span><span class="sxs-lookup"><span data-stu-id="7689a-208">Animation Overview</span></span>](animation-overview.md)
