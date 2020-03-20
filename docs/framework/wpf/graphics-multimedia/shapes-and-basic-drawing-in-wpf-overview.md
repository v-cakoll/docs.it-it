---
title: Panoramica delle forme e dei disegni di base
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
ms.openlocfilehash: 44104bec478f1fbb10acc0e591af43ea95fecdc5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141328"
---
# <a name="shapes-and-basic-drawing-in-wpf-overview"></a><span data-ttu-id="6e21c-102">Cenni preliminari sugli oggetti Shape e sulle funzionalità di disegno di base di WPF</span><span class="sxs-lookup"><span data-stu-id="6e21c-102">Shapes and Basic Drawing in WPF Overview</span></span>
<span data-ttu-id="6e21c-103">In questo argomento viene fornita <xref:System.Windows.Shapes.Shape> una panoramica su come disegnare con gli oggetti.</span><span class="sxs-lookup"><span data-stu-id="6e21c-103">This topic gives an overview of how to draw with <xref:System.Windows.Shapes.Shape> objects.</span></span> <span data-ttu-id="6e21c-104">A <xref:System.Windows.Shapes.Shape> è un <xref:System.Windows.UIElement> tipo di che consente di disegnare una forma sullo schermo.</span><span class="sxs-lookup"><span data-stu-id="6e21c-104">A <xref:System.Windows.Shapes.Shape> is a type of <xref:System.Windows.UIElement> that enables you to draw a shape to the screen.</span></span> <span data-ttu-id="6e21c-105">Poiché sono elementi <xref:System.Windows.Shapes.Shape> dell'interfaccia <xref:System.Windows.Controls.Panel> utente, gli oggetti possono essere utilizzati all'interno di elementi e la maggior parte dei controlli.</span><span class="sxs-lookup"><span data-stu-id="6e21c-105">Because they are UI elements, <xref:System.Windows.Shapes.Shape> objects can be used inside <xref:System.Windows.Controls.Panel> elements and most controls.</span></span>  
  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <span data-ttu-id="6e21c-106">offre diversi livelli di accesso alla grafica e ai servizi di rendering.</span><span class="sxs-lookup"><span data-stu-id="6e21c-106">offers several layers of access to graphics and rendering services.</span></span> <span data-ttu-id="6e21c-107">Al livello superiore, <xref:System.Windows.Shapes.Shape> gli oggetti sono facili da usare e forniscono [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] molte funzioni utili, come il layout e la partecipazione al sistema di eventi.</span><span class="sxs-lookup"><span data-stu-id="6e21c-107">At the top layer, <xref:System.Windows.Shapes.Shape> objects are easy to use and provide many useful features, such as layout and participation in the [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] event system.</span></span>  

<a name="shapes"></a>
## <a name="shape-objects"></a><span data-ttu-id="6e21c-108">Oggetti Shape</span><span class="sxs-lookup"><span data-stu-id="6e21c-108">Shape Objects</span></span>  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<span data-ttu-id="6e21c-109">fornisce una serie di oggetti <xref:System.Windows.Shapes.Shape> pronti all'uso.</span><span class="sxs-lookup"><span data-stu-id="6e21c-109">provides a number of ready-to-use <xref:System.Windows.Shapes.Shape> objects.</span></span>  <span data-ttu-id="6e21c-110">Tutti gli oggetti <xref:System.Windows.Shapes.Shape> forma ereditano dalla classe.</span><span class="sxs-lookup"><span data-stu-id="6e21c-110">All shape objects inherit from the <xref:System.Windows.Shapes.Shape> class.</span></span> <span data-ttu-id="6e21c-111">Gli oggetti <xref:System.Windows.Shapes.Ellipse>forma <xref:System.Windows.Shapes.Line> <xref:System.Windows.Shapes.Path>disponibili <xref:System.Windows.Shapes.Polygon> <xref:System.Windows.Shapes.Polyline>includono <xref:System.Windows.Shapes.Rectangle>, , , , e .</span><span class="sxs-lookup"><span data-stu-id="6e21c-111">Available shape objects include <xref:System.Windows.Shapes.Ellipse>, <xref:System.Windows.Shapes.Line>, <xref:System.Windows.Shapes.Path>, <xref:System.Windows.Shapes.Polygon>, <xref:System.Windows.Shapes.Polyline>, and <xref:System.Windows.Shapes.Rectangle>.</span></span> <span data-ttu-id="6e21c-112"><xref:System.Windows.Shapes.Shape>gli oggetti condividono le seguenti proprietà comuni.</span><span class="sxs-lookup"><span data-stu-id="6e21c-112"><xref:System.Windows.Shapes.Shape> objects share the following common properties.</span></span>  
  
- <span data-ttu-id="6e21c-113"><xref:System.Windows.Shapes.Shape.Stroke%2A>: descrive come viene disegnato il contorno della forma.</span><span class="sxs-lookup"><span data-stu-id="6e21c-113"><xref:System.Windows.Shapes.Shape.Stroke%2A>: Describes how the shape's outline is painted.</span></span>  
  
- <span data-ttu-id="6e21c-114"><xref:System.Windows.Shapes.Shape.StrokeThickness%2A>: descrive lo spessore del contorno della forma.</span><span class="sxs-lookup"><span data-stu-id="6e21c-114"><xref:System.Windows.Shapes.Shape.StrokeThickness%2A>: Describes the thickness of the shape's outline.</span></span>  
  
- <span data-ttu-id="6e21c-115"><xref:System.Windows.Shapes.Shape.Fill%2A>: descrive come viene dipinto l'interno della forma.</span><span class="sxs-lookup"><span data-stu-id="6e21c-115"><xref:System.Windows.Shapes.Shape.Fill%2A>: Describes how the interior of the shape is painted.</span></span>  
  
- <span data-ttu-id="6e21c-116">Proprietà dei dati per specificare coordinate e vertici, misurati in pixel indipendenti dal dispositivo.</span><span class="sxs-lookup"><span data-stu-id="6e21c-116">Data properties to specify coordinates and vertices, measured in device-independent pixels.</span></span>  
  
 <span data-ttu-id="6e21c-117">Poiché derivano da <xref:System.Windows.UIElement>, gli oggetti forma possono essere utilizzati all'interno di pannelli e la maggior parte dei controlli.</span><span class="sxs-lookup"><span data-stu-id="6e21c-117">Because they derive from <xref:System.Windows.UIElement>, shape objects can be used inside panels and most controls.</span></span> <span data-ttu-id="6e21c-118">Il <xref:System.Windows.Controls.Canvas> pannello è una scelta particolarmente buona per la creazione di disegni complessi perché supporta il posizionamento assoluto dei relativi oggetti figlio.</span><span class="sxs-lookup"><span data-stu-id="6e21c-118">The <xref:System.Windows.Controls.Canvas> panel is a particularly good choice for creating complex drawings because it supports absolute positioning of its child objects.</span></span>  
  
 <span data-ttu-id="6e21c-119">La <xref:System.Windows.Shapes.Line> classe consente di disegnare una linea tra due punti.</span><span class="sxs-lookup"><span data-stu-id="6e21c-119">The <xref:System.Windows.Shapes.Line> class enables you to draw a line between two points.</span></span> <span data-ttu-id="6e21c-120">L'esempio seguente illustra molti modi per specificare le coordinate della riga e le proprietà del tratto.</span><span class="sxs-lookup"><span data-stu-id="6e21c-120">The following example shows several ways to specify line coordinates and stroke properties.</span></span>  
  
 [!code-xaml[drawingwithshapeelements#LineExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/lineexample.xaml#lineexample1)]  
  
 [!code-cpp[shapesprocedural#ShapesProceduralLine](~/samples/snippets/cpp/VS_Snippets_Wpf/ShapesProcedural/CPP/ShapesProcedural.cpp#shapesproceduralline)]
 [!code-csharp[shapesprocedural#ShapesProceduralLine](~/samples/snippets/csharp/VS_Snippets_Wpf/ShapesProcedural/Csharp/ShapesProcedural.cs#shapesproceduralline)]
 [!code-vb[shapesprocedural#ShapesProceduralLine](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ShapesProcedural/VisualBasic/ShapesProceduralVB.vb#shapesproceduralline)]  
  
 <span data-ttu-id="6e21c-121">L'immagine seguente <xref:System.Windows.Shapes.Line>mostra l'oggetto renderizzato .</span><span class="sxs-lookup"><span data-stu-id="6e21c-121">The following image shows the rendered <xref:System.Windows.Shapes.Line>.</span></span>  
  
 <span data-ttu-id="6e21c-122">![Illustrazione di Line](./media/shape-ovw-line2.gif "shape_ovw_line2")</span><span class="sxs-lookup"><span data-stu-id="6e21c-122">![Line illustration](./media/shape-ovw-line2.gif "shape_ovw_line2")</span></span>  
  
 <span data-ttu-id="6e21c-123">Anche <xref:System.Windows.Shapes.Line> se la <xref:System.Windows.Shapes.Shape.Fill%2A> classe fornisce una proprietà, <xref:System.Windows.Shapes.Line> l'impostazione non ha alcun effetto perché un oggetto non ha alcuna area.</span><span class="sxs-lookup"><span data-stu-id="6e21c-123">Although the <xref:System.Windows.Shapes.Line> class does provide a <xref:System.Windows.Shapes.Shape.Fill%2A> property, setting it has no effect because a <xref:System.Windows.Shapes.Line> has no area.</span></span>  
  
 <span data-ttu-id="6e21c-124">Un'altra forma <xref:System.Windows.Shapes.Ellipse>comune è la .</span><span class="sxs-lookup"><span data-stu-id="6e21c-124">Another common shape is the <xref:System.Windows.Shapes.Ellipse>.</span></span>  <span data-ttu-id="6e21c-125">Creare <xref:System.Windows.Shapes.Ellipse> un oggetto definendo <xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.FrameworkElement.Height%2A> la forma e le proprietà.</span><span class="sxs-lookup"><span data-stu-id="6e21c-125">Create an <xref:System.Windows.Shapes.Ellipse> by defining the shape's <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties.</span></span> <span data-ttu-id="6e21c-126">Per disegnare un cerchio, <xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.FrameworkElement.Height%2A> specificare un <xref:System.Windows.Shapes.Ellipse> i cui valori sono uguali.</span><span class="sxs-lookup"><span data-stu-id="6e21c-126">To draw a circle, specify an <xref:System.Windows.Shapes.Ellipse> whose <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> values are equal.</span></span>  
  
 [!code-xaml[ShapeOverviews#ShapesOVW1](~/samples/snippets/csharp/VS_Snippets_Wpf/ShapeOverviews/CS/Window1.xaml#shapesovw1)]  
  
 [!code-csharp[brushesmiscsnippets_procedural_snip#SetBackgroundColorOfShapeCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesMiscSnippets_procedural_snip/CSharp/SetBackgroundColorOfShapeExample.cs#setbackgroundcolorofshapecodeexamplewholepage)]
 [!code-vb[brushesmiscsnippets_procedural_snip#SetBackgroundColorOfShapeCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesMiscSnippets_procedural_snip/visualbasic/setbackgroundcolorofshapeexample.vb#setbackgroundcolorofshapecodeexamplewholepage)]  
  
 <span data-ttu-id="6e21c-127">L'immagine seguente mostra un <xref:System.Windows.Shapes.Ellipse>esempio di un oggetto renderizzato .</span><span class="sxs-lookup"><span data-stu-id="6e21c-127">The following image shows an example of a rendered <xref:System.Windows.Shapes.Ellipse>.</span></span>  
  
 <span data-ttu-id="6e21c-128">![Illustrazione di Ellipse](./media/shape-ovw-ellipse2.png "shape_ovw_ellipse2")</span><span class="sxs-lookup"><span data-stu-id="6e21c-128">![Ellipse illustration](./media/shape-ovw-ellipse2.png "shape_ovw_ellipse2")</span></span>  
  
<a name="paths"></a>
## <a name="using-paths-and-geometries"></a><span data-ttu-id="6e21c-129">Utilizzo di tracciati e geometrie</span><span class="sxs-lookup"><span data-stu-id="6e21c-129">Using Paths and Geometries</span></span>  
 <span data-ttu-id="6e21c-130">La <xref:System.Windows.Shapes.Path> classe consente di disegnare curve e forme complesse.</span><span class="sxs-lookup"><span data-stu-id="6e21c-130">The <xref:System.Windows.Shapes.Path> class enables you to draw curves and complex shapes.</span></span> <span data-ttu-id="6e21c-131">Queste curve e forme <xref:System.Windows.Media.Geometry> vengono descritte utilizzando gli oggetti.</span><span class="sxs-lookup"><span data-stu-id="6e21c-131">These curves and shapes are described using <xref:System.Windows.Media.Geometry> objects.</span></span> <span data-ttu-id="6e21c-132">Per utilizzare <xref:System.Windows.Shapes.Path>un oggetto <xref:System.Windows.Media.Geometry> , creare un <xref:System.Windows.Shapes.Path> oggetto <xref:System.Windows.Shapes.Path.Data%2A> e utilizzarlo per impostare la proprietà dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="6e21c-132">To use a <xref:System.Windows.Shapes.Path>, you create a <xref:System.Windows.Media.Geometry> and use it to set the <xref:System.Windows.Shapes.Path> object's <xref:System.Windows.Shapes.Path.Data%2A> property.</span></span>  
  
 <span data-ttu-id="6e21c-133">Ci sono una <xref:System.Windows.Media.Geometry> varietà di oggetti tra cui scegliere.</span><span class="sxs-lookup"><span data-stu-id="6e21c-133">There are a variety of <xref:System.Windows.Media.Geometry> objects to choose from.</span></span> <span data-ttu-id="6e21c-134">Le <xref:System.Windows.Media.LineGeometry> <xref:System.Windows.Media.RectangleGeometry>classi <xref:System.Windows.Media.EllipseGeometry> , e descrivono forme relativamente semplici.</span><span class="sxs-lookup"><span data-stu-id="6e21c-134">The <xref:System.Windows.Media.LineGeometry>, <xref:System.Windows.Media.RectangleGeometry>, and <xref:System.Windows.Media.EllipseGeometry> classes describe relatively simple shapes.</span></span> <span data-ttu-id="6e21c-135">Per creare forme più complesse o <xref:System.Windows.Media.PathGeometry>curve, utilizzare un file .</span><span class="sxs-lookup"><span data-stu-id="6e21c-135">To create more complex shapes or create curves, use a <xref:System.Windows.Media.PathGeometry>.</span></span>  
  
<a name="pathgeometry"></a>
### <a name="pathgeometry-and-pathsegments"></a><span data-ttu-id="6e21c-136">PathGeometry e PathSegments</span><span class="sxs-lookup"><span data-stu-id="6e21c-136">PathGeometry and PathSegments</span></span>  
 <span data-ttu-id="6e21c-137"><xref:System.Windows.Media.PathGeometry>gli oggetti sono costituiti <xref:System.Windows.Media.PathFigure> da uno o più oggetti; ognuna rappresenta una "figura" o una <xref:System.Windows.Media.PathFigure> forma diversa.</span><span class="sxs-lookup"><span data-stu-id="6e21c-137"><xref:System.Windows.Media.PathGeometry> objects are comprised of one or more <xref:System.Windows.Media.PathFigure> objects; each <xref:System.Windows.Media.PathFigure> represents a different "figure" or shape.</span></span> <span data-ttu-id="6e21c-138">Ciascuno <xref:System.Windows.Media.PathFigure> di essi è costituito da uno o più <xref:System.Windows.Media.PathSegment> oggetti, ognuno dei quali rappresenta una parte connessa della figura o della forma.</span><span class="sxs-lookup"><span data-stu-id="6e21c-138">Each <xref:System.Windows.Media.PathFigure> is itself comprised of one or more <xref:System.Windows.Media.PathSegment> objects, each representing a connected portion of the figure or shape.</span></span> <span data-ttu-id="6e21c-139">I tipi di <xref:System.Windows.Media.LineSegment>segmento includono quanto segue: , <xref:System.Windows.Media.BezierSegment>, e <xref:System.Windows.Media.ArcSegment>.</span><span class="sxs-lookup"><span data-stu-id="6e21c-139">Segment types include the following: <xref:System.Windows.Media.LineSegment>, <xref:System.Windows.Media.BezierSegment>, and <xref:System.Windows.Media.ArcSegment>.</span></span>  
  
 <span data-ttu-id="6e21c-140">Nell'esempio seguente, <xref:System.Windows.Shapes.Path> a viene utilizzato per disegnare una curva di Bézier quadratica.</span><span class="sxs-lookup"><span data-stu-id="6e21c-140">In the following example, a <xref:System.Windows.Shapes.Path> is used to draw a quadratic Bezier curve.</span></span>  
  
 [!code-xaml[geometrysample#34](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#34)]  
  
 <span data-ttu-id="6e21c-141">L'immagine seguente illustra la forma sottoposta a rendering.</span><span class="sxs-lookup"><span data-stu-id="6e21c-141">The following image shows the rendered shape.</span></span>  
  
 <span data-ttu-id="6e21c-142">![Illustrazione di Path](./media/shape-ovw-path2.gif "shape_ovw_path2")</span><span class="sxs-lookup"><span data-stu-id="6e21c-142">![Path illustration](./media/shape-ovw-path2.gif "shape_ovw_path2")</span></span>  
  
 <span data-ttu-id="6e21c-143">Per ulteriori <xref:System.Windows.Media.PathGeometry> informazioni su <xref:System.Windows.Media.Geometry> e sulle altre classi, vedere [Cenni preliminari](geometry-overview.md)sulla geometria .</span><span class="sxs-lookup"><span data-stu-id="6e21c-143">For more information about <xref:System.Windows.Media.PathGeometry> and the other <xref:System.Windows.Media.Geometry> classes, see the [Geometry Overview](geometry-overview.md).</span></span>  
  
<a name="pathdatastring"></a>
### <a name="xaml-abbreviated-syntax"></a><span data-ttu-id="6e21c-144">Sintassi abbreviata XAML</span><span class="sxs-lookup"><span data-stu-id="6e21c-144">XAML Abbreviated Syntax</span></span>  
 <span data-ttu-id="6e21c-145">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], è inoltre possibile utilizzare una <xref:System.Windows.Shapes.Path>sintassi abbreviata speciale per descrivere un oggetto .</span><span class="sxs-lookup"><span data-stu-id="6e21c-145">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], you may also use a special abbreviated syntax to describe a <xref:System.Windows.Shapes.Path>.</span></span> <span data-ttu-id="6e21c-146">Nell'esempio seguente viene usata la sintassi abbreviata per disegnare una forma complessa.</span><span class="sxs-lookup"><span data-stu-id="6e21c-146">In the following example, abbreviated syntax is used to draw a complex shape.</span></span>  
  
```xaml  
      <Path Stroke="DarkGoldenRod" StrokeThickness="3"
Data="M 100,200 C 100,25 400,350 400,175 H 280" />  
```  
  
 <span data-ttu-id="6e21c-147">L'immagine seguente <xref:System.Windows.Shapes.Path>mostra un rendering .</span><span class="sxs-lookup"><span data-stu-id="6e21c-147">The following image shows a rendered <xref:System.Windows.Shapes.Path>.</span></span>  
  
 <span data-ttu-id="6e21c-148">![Illustrazione di Path](./media/shape-ovw-path.PNG "shape_ovw_path")</span><span class="sxs-lookup"><span data-stu-id="6e21c-148">![Path illustration](./media/shape-ovw-path.PNG "shape_ovw_path")</span></span>  
  
 <span data-ttu-id="6e21c-149">La <xref:System.Windows.Shapes.Path.Data%2A> stringa di attributo inizia con il comando "moveto", indicato da M, che stabilisce un punto iniziale per il percorso nel sistema di coordinate dell'oggetto <xref:System.Windows.Controls.Canvas>.</span><span class="sxs-lookup"><span data-stu-id="6e21c-149">The <xref:System.Windows.Shapes.Path.Data%2A> attribute string begins with the "moveto" command, indicated by M, which establishes a start point for the path in the coordinate system of the <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="6e21c-150"><xref:System.Windows.Shapes.Path>parametri di dati fanno distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="6e21c-150"><xref:System.Windows.Shapes.Path> data parameters are case-sensitive.</span></span> <span data-ttu-id="6e21c-151">La M maiuscola indica una posizione assoluta per il nuovo punto corrente.</span><span class="sxs-lookup"><span data-stu-id="6e21c-151">The capital M indicates an absolute location for the new current point.</span></span> <span data-ttu-id="6e21c-152">Una lettera m minuscola indica le coordinate relative.</span><span class="sxs-lookup"><span data-stu-id="6e21c-152">A lowercase m would indicate relative coordinates.</span></span> <span data-ttu-id="6e21c-153">Il primo segmento è una curva di Bézier cubica che inizia in corrispondenza del punto (100,200) e termina in corrispondenza del punto (400,175) e viene disegnata usando i due punti di controllo (100,25) e (400,350).</span><span class="sxs-lookup"><span data-stu-id="6e21c-153">The first segment is a cubic Bezier curve beginning at (100,200) and ending at (400,175), drawn using the two control points (100,25) and (400,350).</span></span> <span data-ttu-id="6e21c-154">Questo segmento è indicato dal <xref:System.Windows.Shapes.Path.Data%2A> comando C nella stringa di attributo.</span><span class="sxs-lookup"><span data-stu-id="6e21c-154">This segment is indicated by the C command in the <xref:System.Windows.Shapes.Path.Data%2A> attribute string.</span></span> <span data-ttu-id="6e21c-155">Anche in questo caso la lettera C maiuscola indica un percorso assoluto, mentre la lettera c minuscola indica un percorso relativo.</span><span class="sxs-lookup"><span data-stu-id="6e21c-155">Again, the capital C indicates an absolute path; the lowercase c would indicate a relative path.</span></span>  
  
 <span data-ttu-id="6e21c-156">Il secondo segmento inizia con un comando orizzontale assoluto "lineto" H, che specifica una riga disegnata dal punto finale del sottopercorso precedente (400,175) a un nuovo punto finale (280,175).</span><span class="sxs-lookup"><span data-stu-id="6e21c-156">The second segment begins with an absolute horizontal "lineto" command H, which specifies a line drawn from the preceding subpath's endpoint (400,175) to a new endpoint (280,175).</span></span> <span data-ttu-id="6e21c-157">Poiché è un comando "lineto" orizzontale, il valore specificato è una coordinata *x.*</span><span class="sxs-lookup"><span data-stu-id="6e21c-157">Because it is a horizontal "lineto" command, the value specified is an *x*-coordinate.</span></span>  
  
 <span data-ttu-id="6e21c-158">Per la sintassi del <xref:System.Windows.Shapes.Path.Data%2A> percorso completo, vedere il riferimento e [Creare una forma utilizzando un PathGeometry](how-to-create-a-shape-by-using-a-pathgeometry.md).</span><span class="sxs-lookup"><span data-stu-id="6e21c-158">For the complete path syntax, see the <xref:System.Windows.Shapes.Path.Data%2A> reference and [Create a Shape by Using a PathGeometry](how-to-create-a-shape-by-using-a-pathgeometry.md).</span></span>  
  
<a name="fillpaint"></a>
## <a name="painting-shapes"></a><span data-ttu-id="6e21c-159">Disegno di oggetti Shape</span><span class="sxs-lookup"><span data-stu-id="6e21c-159">Painting Shapes</span></span>  
 <span data-ttu-id="6e21c-160"><xref:System.Windows.Media.Brush>gli oggetti vengono utilizzati <xref:System.Windows.Shapes.Shape.Stroke%2A> per <xref:System.Windows.Shapes.Shape.Fill%2A>disegnare una forma e .</span><span class="sxs-lookup"><span data-stu-id="6e21c-160"><xref:System.Windows.Media.Brush> objects are used to paint a shape's <xref:System.Windows.Shapes.Shape.Stroke%2A> and <xref:System.Windows.Shapes.Shape.Fill%2A>.</span></span> <span data-ttu-id="6e21c-161">Nell'esempio seguente vengono specificati il <xref:System.Windows.Shapes.Ellipse> tratto e il riempimento di un oggetto .</span><span class="sxs-lookup"><span data-stu-id="6e21c-161">In the following example, the stroke and fill of an <xref:System.Windows.Shapes.Ellipse> are specified.</span></span> <span data-ttu-id="6e21c-162">Si noti che un input valido per le proprietà del pennello può essere rappresentato da una parola chiave o da un valore di colore esadecimale.</span><span class="sxs-lookup"><span data-stu-id="6e21c-162">Note that valid input for brush properties can be either a keyword or hexadecimal color value.</span></span> <span data-ttu-id="6e21c-163">Per altre informazioni sulle parole chiave <xref:System.Windows.Media.Colors> di colore <xref:System.Windows.Media> disponibili, vedere proprietà della classe nello spazio dei nomi .</span><span class="sxs-lookup"><span data-stu-id="6e21c-163">For more information about available color keywords, see properties of the <xref:System.Windows.Media.Colors> class in the <xref:System.Windows.Media> namespace.</span></span>  
  
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
  
 <span data-ttu-id="6e21c-164">L'immagine seguente <xref:System.Windows.Shapes.Ellipse>mostra l'oggetto renderizzato .</span><span class="sxs-lookup"><span data-stu-id="6e21c-164">The following image shows the rendered <xref:System.Windows.Shapes.Ellipse>.</span></span>  
  
 <span data-ttu-id="6e21c-165">![Ellisse](./media/shape-ovw-ellipsefill.PNG "shape_ovw_ellipsefill")</span><span class="sxs-lookup"><span data-stu-id="6e21c-165">![An ellipse](./media/shape-ovw-ellipsefill.PNG "shape_ovw_ellipsefill")</span></span>  
  
 <span data-ttu-id="6e21c-166">In alternativa, è possibile utilizzare la <xref:System.Windows.Media.SolidColorBrush> sintassi degli elementi proprietà per creare in modo esplicito un oggetto per disegnare la forma con un colore a tinta unita.</span><span class="sxs-lookup"><span data-stu-id="6e21c-166">Alternatively, you can use property element syntax to explicitly create a <xref:System.Windows.Media.SolidColorBrush> object to paint the shape with a solid color.</span></span>  
  
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
  
 <span data-ttu-id="6e21c-167">La figura seguente mostra la forma sottoposta a rendering.</span><span class="sxs-lookup"><span data-stu-id="6e21c-167">The following illustration shows the rendered shape.</span></span>  
  
 <span data-ttu-id="6e21c-168">![Illustrazione di SolidColorBrush](./media/shape-ovw-solidcolorbrush.PNG "shape_ovw_solidcolorbrush")</span><span class="sxs-lookup"><span data-stu-id="6e21c-168">![SolidColorBrush illustration](./media/shape-ovw-solidcolorbrush.PNG "shape_ovw_solidcolorbrush")</span></span>  
  
 <span data-ttu-id="6e21c-169">È anche possibile disegnare il tratto o il riempimento di una forma con sfumature, immagini, motivi e così via.</span><span class="sxs-lookup"><span data-stu-id="6e21c-169">You can also paint a shape's stroke or fill with gradients, images, patterns, and more.</span></span> <span data-ttu-id="6e21c-170">Per ulteriori informazioni, vedere [Cenni preliminari sul disegno con colori a tinta unita e gradienti](painting-with-solid-colors-and-gradients-overview.md).</span><span class="sxs-lookup"><span data-stu-id="6e21c-170">For more information, see the [Painting with Solid Colors and Gradients Overview](painting-with-solid-colors-and-gradients-overview.md).</span></span>  
  
<a name="stretchableshapessection"></a>
## <a name="stretchable-shapes"></a><span data-ttu-id="6e21c-171">Oggetti Shape allungabili</span><span class="sxs-lookup"><span data-stu-id="6e21c-171">Stretchable Shapes</span></span>  
 <span data-ttu-id="6e21c-172">Le <xref:System.Windows.Shapes.Line> <xref:System.Windows.Shapes.Path>classi <xref:System.Windows.Shapes.Polygon> <xref:System.Windows.Shapes.Polyline>, <xref:System.Windows.Shapes.Rectangle> , , <xref:System.Windows.Shapes.Shape.Stretch%2A> e dispongono tutte di una proprietà .</span><span class="sxs-lookup"><span data-stu-id="6e21c-172">The <xref:System.Windows.Shapes.Line>, <xref:System.Windows.Shapes.Path>, <xref:System.Windows.Shapes.Polygon>, <xref:System.Windows.Shapes.Polyline>, and <xref:System.Windows.Shapes.Rectangle> classes all have a <xref:System.Windows.Shapes.Shape.Stretch%2A> property.</span></span> <span data-ttu-id="6e21c-173">Questa proprietà determina <xref:System.Windows.Shapes.Shape> il modo in cui il contenuto di un <xref:System.Windows.Shapes.Shape> oggetto (la forma da disegnare) viene allungato per riempire lo spazio di layout dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="6e21c-173">This property determines how a <xref:System.Windows.Shapes.Shape> object's contents (the shape to be drawn) is stretched to fill the <xref:System.Windows.Shapes.Shape> object's layout space.</span></span> <span data-ttu-id="6e21c-174">Lo <xref:System.Windows.Shapes.Shape> spazio di layout di un <xref:System.Windows.Shapes.Shape> oggetto è la quantità di spazio <xref:System.Windows.FrameworkElement.Width%2A> che <xref:System.Windows.FrameworkElement.Height%2A> viene allocata dal sistema di layout, a causa di un esplicito e dell'impostazione o a causa delle sue <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> impostazioni e <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> .</span><span class="sxs-lookup"><span data-stu-id="6e21c-174">A <xref:System.Windows.Shapes.Shape> object's layout space is the amount of space the <xref:System.Windows.Shapes.Shape> is allocated by the layout system, because of either an explicit <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> setting or because of its <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> and <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> settings.</span></span> <span data-ttu-id="6e21c-175">Per ulteriori informazioni sul layout in Windows Presentation Foundation, vedere [Panoramica del layout.](../advanced/layout.md)</span><span class="sxs-lookup"><span data-stu-id="6e21c-175">For additional information on layout in Windows Presentation Foundation, see [Layout](../advanced/layout.md) overview.</span></span>  
  
 <span data-ttu-id="6e21c-176">La proprietà Stretch accetta uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="6e21c-176">The Stretch property takes one of the following values:</span></span>  
  
- <span data-ttu-id="6e21c-177"><xref:System.Windows.Media.Stretch.None>: <xref:System.Windows.Shapes.Shape> il contenuto dell'oggetto non viene allungato.</span><span class="sxs-lookup"><span data-stu-id="6e21c-177"><xref:System.Windows.Media.Stretch.None>: The <xref:System.Windows.Shapes.Shape> object's contents are not stretched.</span></span>  
  
- <span data-ttu-id="6e21c-178"><xref:System.Windows.Media.Stretch.Fill>: <xref:System.Windows.Shapes.Shape> il contenuto dell'oggetto viene allungato per riempire lo spazio di layout.</span><span class="sxs-lookup"><span data-stu-id="6e21c-178"><xref:System.Windows.Media.Stretch.Fill>: The <xref:System.Windows.Shapes.Shape> object's contents are stretched to fill its layout space.</span></span>  <span data-ttu-id="6e21c-179">Le proporzioni non vengono mantenute.</span><span class="sxs-lookup"><span data-stu-id="6e21c-179">Aspect ratio is not preserved.</span></span>  
  
- <span data-ttu-id="6e21c-180"><xref:System.Windows.Media.Stretch.Uniform>: <xref:System.Windows.Shapes.Shape> il contenuto dell'oggetto viene allungato il più possibile per riempire lo spazio di layout mantenendo le proporzioni originali.</span><span class="sxs-lookup"><span data-stu-id="6e21c-180"><xref:System.Windows.Media.Stretch.Uniform>: The <xref:System.Windows.Shapes.Shape> object's contents are stretched as much as possible to fill its layout space while preserving its original aspect ratio.</span></span>  
  
- <span data-ttu-id="6e21c-181"><xref:System.Windows.Media.Stretch.UniformToFill>: <xref:System.Windows.Shapes.Shape> il contenuto dell'oggetto viene allungato per riempire completamente lo spazio di layout mantenendo le proporzioni originali.</span><span class="sxs-lookup"><span data-stu-id="6e21c-181"><xref:System.Windows.Media.Stretch.UniformToFill>: The <xref:System.Windows.Shapes.Shape> object's contents are stretched to completely fill its layout space while preserving its original aspect ratio.</span></span>  
  
 <span data-ttu-id="6e21c-182">Si noti <xref:System.Windows.Shapes.Shape> che, quando il contenuto <xref:System.Windows.Shapes.Shape> di un oggetto viene allungato, il contorno dell'oggetto viene disegnato dopo l'allungamento.</span><span class="sxs-lookup"><span data-stu-id="6e21c-182">Note that, when a <xref:System.Windows.Shapes.Shape> object's contents are stretched, the <xref:System.Windows.Shapes.Shape> object's outline is painted after the stretching.</span></span>  
  
 <span data-ttu-id="6e21c-183">Nell'esempio seguente, <xref:System.Windows.Shapes.Polygon> a viene usato per disegnare un triangolo molto piccolo da (0,0) a (0,1) a (1,1).</span><span class="sxs-lookup"><span data-stu-id="6e21c-183">In the following example, a <xref:System.Windows.Shapes.Polygon> is used to draw a very small triangle from (0,0) to (0,1) to (1,1).</span></span> <span data-ttu-id="6e21c-184">L'oggetto <xref:System.Windows.Shapes.Polygon> <xref:System.Windows.FrameworkElement.Width%2A> e <xref:System.Windows.FrameworkElement.Height%2A> sono impostati su 100 e la relativa proprietà stretch è impostata su Fill.</span><span class="sxs-lookup"><span data-stu-id="6e21c-184">The <xref:System.Windows.Shapes.Polygon> object's <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> are set to 100, and its stretch property is set to Fill.</span></span> <span data-ttu-id="6e21c-185">Di conseguenza, <xref:System.Windows.Shapes.Polygon> il contenuto dell'oggetto (il triangolo) viene allungato per riempire lo spazio più grande.</span><span class="sxs-lookup"><span data-stu-id="6e21c-185">As a result, the <xref:System.Windows.Shapes.Polygon> object's contents (the triangle) are stretched to fill the larger space.</span></span>  
  
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
## <a name="transforming-shapes"></a><span data-ttu-id="6e21c-186">Trasformazione degli oggetti Shape</span><span class="sxs-lookup"><span data-stu-id="6e21c-186">Transforming Shapes</span></span>  
 <span data-ttu-id="6e21c-187">La <xref:System.Windows.Media.Transform> classe fornisce i mezzi per trasformare le forme in un piano bidimensionale.</span><span class="sxs-lookup"><span data-stu-id="6e21c-187">The <xref:System.Windows.Media.Transform> class provides the means to transform shapes in a two-dimensional plane.</span></span>  <span data-ttu-id="6e21c-188">I diversi tipi di<xref:System.Windows.Media.RotateTransform>trasformazione<xref:System.Windows.Media.ScaleTransform>includono la<xref:System.Windows.Media.SkewTransform>rotazione (<xref:System.Windows.Media.TranslateTransform>), la scala ( ), l'inclinazione ( ) e la traslazione ( ).</span><span class="sxs-lookup"><span data-stu-id="6e21c-188">The different types of transformation include rotation (<xref:System.Windows.Media.RotateTransform>), scale (<xref:System.Windows.Media.ScaleTransform>), skew (<xref:System.Windows.Media.SkewTransform>), and translation (<xref:System.Windows.Media.TranslateTransform>).</span></span>  
  
 <span data-ttu-id="6e21c-189">Una trasformazione comune da applicare a una forma è una rotazione.</span><span class="sxs-lookup"><span data-stu-id="6e21c-189">A common transform to apply to a shape is a rotation.</span></span>  <span data-ttu-id="6e21c-190">Per ruotare una <xref:System.Windows.Media.RotateTransform> forma, <xref:System.Windows.Media.RotateTransform.Angle%2A>creare a e specificarne il file .</span><span class="sxs-lookup"><span data-stu-id="6e21c-190">To rotate a shape, create a <xref:System.Windows.Media.RotateTransform> and specify its <xref:System.Windows.Media.RotateTransform.Angle%2A>.</span></span> <span data-ttu-id="6e21c-191">Un <xref:System.Windows.Media.RotateTransform.Angle%2A> di 45 ruota l'elemento di 45 gradi in senso orario; un angolo di 90 ruota l'elemento di 90 gradi in senso orario; E così via.</span><span class="sxs-lookup"><span data-stu-id="6e21c-191">An <xref:System.Windows.Media.RotateTransform.Angle%2A> of 45 rotates the element 45 degrees clockwise; an angle of 90 rotates the element 90 degrees clockwise; and so on.</span></span> <span data-ttu-id="6e21c-192">Impostare <xref:System.Windows.Media.RotateTransform.CenterX%2A> <xref:System.Windows.Media.RotateTransform.CenterY%2A> le proprietà e se si desidera controllare il punto attorno al quale viene ruotato l'elemento.</span><span class="sxs-lookup"><span data-stu-id="6e21c-192">Set the <xref:System.Windows.Media.RotateTransform.CenterX%2A> and <xref:System.Windows.Media.RotateTransform.CenterY%2A> properties if you want to control the point about which the element is rotated.</span></span> <span data-ttu-id="6e21c-193">Questi valori di proprietà sono espressi nello spazio delle coordinate dell'elemento trasformato.</span><span class="sxs-lookup"><span data-stu-id="6e21c-193">These property values are expressed in the coordinate space of the element being transformed.</span></span> <span data-ttu-id="6e21c-194"><xref:System.Windows.Media.RotateTransform.CenterX%2A>e <xref:System.Windows.Media.RotateTransform.CenterY%2A> hanno valori predefiniti pari a zero.</span><span class="sxs-lookup"><span data-stu-id="6e21c-194"><xref:System.Windows.Media.RotateTransform.CenterX%2A> and <xref:System.Windows.Media.RotateTransform.CenterY%2A> have default values of zero.</span></span> <span data-ttu-id="6e21c-195">Infine, applicare <xref:System.Windows.Media.RotateTransform> l'oggetto all'elemento.</span><span class="sxs-lookup"><span data-stu-id="6e21c-195">Finally, apply the <xref:System.Windows.Media.RotateTransform> to the element.</span></span> <span data-ttu-id="6e21c-196">Se non si desidera che la trasformazione influisca <xref:System.Windows.UIElement.RenderTransform%2A> sul layout, impostare la proprietà della forma.</span><span class="sxs-lookup"><span data-stu-id="6e21c-196">If you don't want the transform to affect layout, set the shape's <xref:System.Windows.UIElement.RenderTransform%2A> property.</span></span>  
  
 <span data-ttu-id="6e21c-197">Nell'esempio seguente, <xref:System.Windows.Media.RotateTransform> a viene utilizzato per ruotare una forma di 45 gradi intorno all'angolo superiore sinistro della forma (0,0).</span><span class="sxs-lookup"><span data-stu-id="6e21c-197">In the following example, a <xref:System.Windows.Media.RotateTransform> is used to rotate a shape 45 degrees about the shape's top left corner (0,0).</span></span>  
  
 [!code-xaml[transformssample#14](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/RotateTransformExample.xaml#14)]  
  
 <span data-ttu-id="6e21c-198">Nell'esempio successivo un'altra forma viene ruotata di 45 gradi, ma in questo caso rispetto al punto (25,50).</span><span class="sxs-lookup"><span data-stu-id="6e21c-198">In the next example, another shape is rotated 45 degrees, but this time it's rotated about the point (25,50).</span></span>  
  
 [!code-xaml[transformssample#15](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/RotateTransformExample.xaml#15)]  
  
 <span data-ttu-id="6e21c-199">L'immagine seguente illustra i risultati dell'applicazione delle due trasformazioni.</span><span class="sxs-lookup"><span data-stu-id="6e21c-199">The following illustration shows the results of applying the two transforms.</span></span>  
  
 <span data-ttu-id="6e21c-200">![Rotazioni di 45 gradi con punti centrali diversi](./media/wcpsdk-graphicsmm-rotatetransform45degrees.gif "wcpsdk_graphicsmm_rotatetransform45degrees")</span><span class="sxs-lookup"><span data-stu-id="6e21c-200">![45 degree rotations with different center points](./media/wcpsdk-graphicsmm-rotatetransform45degrees.gif "wcpsdk_graphicsmm_rotatetransform45degrees")</span></span>  
  
 <span data-ttu-id="6e21c-201">Negli esempi precedenti è stata applicata una sola trasformazione a ogni oggetto Shape.</span><span class="sxs-lookup"><span data-stu-id="6e21c-201">In the previous examples, a single transform was applied to each shape object.</span></span> <span data-ttu-id="6e21c-202">Per applicare più trasformazioni a una forma (o <xref:System.Windows.Media.TransformGroup>a qualsiasi altro elemento dell'interfaccia utente), utilizzare un' estensione .</span><span class="sxs-lookup"><span data-stu-id="6e21c-202">To apply multiple transforms to a shape (or any other UI element), use a <xref:System.Windows.Media.TransformGroup>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e21c-203">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6e21c-203">See also</span></span>

- [<span data-ttu-id="6e21c-204">Grafica 2D e creazione di immagini</span><span class="sxs-lookup"><span data-stu-id="6e21c-204">2D Graphics and Imaging</span></span>](../advanced/optimizing-performance-2d-graphics-and-imaging.md)
- [<span data-ttu-id="6e21c-205">Cenni sul disegno con colori a tinta unita e sfumature</span><span class="sxs-lookup"><span data-stu-id="6e21c-205">Painting with Solid Colors and Gradients Overview</span></span>](painting-with-solid-colors-and-gradients-overview.md)
- [<span data-ttu-id="6e21c-206">Cenni preliminari sulle classi Geometry</span><span class="sxs-lookup"><span data-stu-id="6e21c-206">Geometry Overview</span></span>](geometry-overview.md)
- [<span data-ttu-id="6e21c-207">Procedura dettagliata: Prima applicazione desktop WPF</span><span class="sxs-lookup"><span data-stu-id="6e21c-207">Walkthrough: My first WPF desktop application</span></span>](../getting-started/walkthrough-my-first-wpf-desktop-application.md)
- [<span data-ttu-id="6e21c-208">Cenni preliminari sull'animazione</span><span class="sxs-lookup"><span data-stu-id="6e21c-208">Animation Overview</span></span>](animation-overview.md)
