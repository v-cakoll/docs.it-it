---
title: "Cenni preliminari sugli oggetti Shape e sulle funzionalità di disegno di base di WPF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2912215cb8fb0090cef58e0201cc355da1f0bf19
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="shapes-and-basic-drawing-in-wpf-overview"></a><span data-ttu-id="9e3ba-102">Cenni preliminari sugli oggetti Shape e sulle funzionalità di disegno di base di WPF</span><span class="sxs-lookup"><span data-stu-id="9e3ba-102">Shapes and Basic Drawing in WPF Overview</span></span>
<span data-ttu-id="9e3ba-103">In questo argomento viene fornita una panoramica di come disegnare con <xref:System.Windows.Shapes.Shape> oggetti.</span><span class="sxs-lookup"><span data-stu-id="9e3ba-103">This topic gives an overview of how to draw with <xref:System.Windows.Shapes.Shape> objects.</span></span> <span data-ttu-id="9e3ba-104">Oggetto <xref:System.Windows.Shapes.Shape> è un tipo di <xref:System.Windows.UIElement> che consente di disegnare una forma sullo schermo.</span><span class="sxs-lookup"><span data-stu-id="9e3ba-104">A <xref:System.Windows.Shapes.Shape> is a type of <xref:System.Windows.UIElement> that enables you to draw a shape to the screen.</span></span> <span data-ttu-id="9e3ba-105">Poiché si tratta di elementi dell'interfaccia utente <xref:System.Windows.Shapes.Shape> oggetti possono essere utilizzati all'interno di <xref:System.Windows.Controls.Panel> la maggior parte dei controlli e gli elementi.</span><span class="sxs-lookup"><span data-stu-id="9e3ba-105">Because they are UI elements, <xref:System.Windows.Shapes.Shape> objects can be used inside <xref:System.Windows.Controls.Panel> elements and most controls.</span></span>  
  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]<span data-ttu-id="9e3ba-106"> offre diversi livelli di accesso alla grafica e ai servizi di rendering.</span><span class="sxs-lookup"><span data-stu-id="9e3ba-106"> offers several layers of access to graphics and rendering services.</span></span> <span data-ttu-id="9e3ba-107">Al livello superiore, <xref:System.Windows.Shapes.Shape> gli oggetti sono facili da utilizzare e forniscono numerose funzionalità, quali layout e la partecipazione di [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] sistema di eventi.</span><span class="sxs-lookup"><span data-stu-id="9e3ba-107">At the top layer, <xref:System.Windows.Shapes.Shape> objects are easy to use and provide many useful features, such as layout and participation in the [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] event system.</span></span>  
  
  
<a name="shapes"></a>   
## <a name="shape-objects"></a><span data-ttu-id="9e3ba-108">Oggetti Shape</span><span class="sxs-lookup"><span data-stu-id="9e3ba-108">Shape Objects</span></span>  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<span data-ttu-id="9e3ba-109">fornisce una serie di pronto all'uso <xref:System.Windows.Shapes.Shape> oggetti.</span><span class="sxs-lookup"><span data-stu-id="9e3ba-109"> provides a number of ready-to-use <xref:System.Windows.Shapes.Shape> objects.</span></span>  <span data-ttu-id="9e3ba-110">Tutti gli oggetti shape ereditano la <xref:System.Windows.Shapes.Shape> classe.</span><span class="sxs-lookup"><span data-stu-id="9e3ba-110">All shape objects inherit from the <xref:System.Windows.Shapes.Shape> class.</span></span> <span data-ttu-id="9e3ba-111">Gli oggetti shape disponibili includono <xref:System.Windows.Shapes.Ellipse>, <xref:System.Windows.Shapes.Line>, <xref:System.Windows.Shapes.Path>, <xref:System.Windows.Shapes.Polygon>, <xref:System.Windows.Shapes.Polyline>, e <xref:System.Windows.Shapes.Rectangle>.</span><span class="sxs-lookup"><span data-stu-id="9e3ba-111">Available shape objects include <xref:System.Windows.Shapes.Ellipse>, <xref:System.Windows.Shapes.Line>, <xref:System.Windows.Shapes.Path>, <xref:System.Windows.Shapes.Polygon>, <xref:System.Windows.Shapes.Polyline>, and <xref:System.Windows.Shapes.Rectangle>.</span></span> <span data-ttu-id="9e3ba-112"><xref:System.Windows.Shapes.Shape>gli oggetti condividono le proprietà comuni seguenti.</span><span class="sxs-lookup"><span data-stu-id="9e3ba-112"><xref:System.Windows.Shapes.Shape> objects share the following common properties.</span></span>  
  
-   <span data-ttu-id="9e3ba-113"><xref:System.Windows.Shapes.Shape.Stroke%2A>: Descrive come viene disegnata la struttura della forma.</span><span class="sxs-lookup"><span data-stu-id="9e3ba-113"><xref:System.Windows.Shapes.Shape.Stroke%2A>: Describes how the shape's outline is painted.</span></span>  
  
-   <span data-ttu-id="9e3ba-114"><xref:System.Windows.Shapes.Shape.StrokeThickness%2A>: Descrive lo spessore del contorno della forma.</span><span class="sxs-lookup"><span data-stu-id="9e3ba-114"><xref:System.Windows.Shapes.Shape.StrokeThickness%2A>: Describes the thickness of the shape's outline.</span></span>  
  
-   <span data-ttu-id="9e3ba-115"><xref:System.Windows.Shapes.Shape.Fill%2A>: Descrive come viene disegnato l'interno della forma.</span><span class="sxs-lookup"><span data-stu-id="9e3ba-115"><xref:System.Windows.Shapes.Shape.Fill%2A>: Describes how the interior of the shape is painted.</span></span>  
  
-   <span data-ttu-id="9e3ba-116">Proprietà dei dati per specificare coordinate e vertici, misurati in pixel indipendenti dal dispositivo.</span><span class="sxs-lookup"><span data-stu-id="9e3ba-116">Data properties to specify coordinates and vertices, measured in device-independent pixels.</span></span>  
  
 <span data-ttu-id="9e3ba-117">Dal momento che derivano da <xref:System.Windows.UIElement>, forma oggetti possono essere utilizzati nei pannelli e nella maggior parte dei controlli.</span><span class="sxs-lookup"><span data-stu-id="9e3ba-117">Because they derive from <xref:System.Windows.UIElement>, shape objects can be used inside panels and most controls.</span></span> <span data-ttu-id="9e3ba-118">Il <xref:System.Windows.Controls.Canvas> pannello è particolarmente indicato per la creazione di disegni complessi, poiché supporta il posizionamento assoluto degli oggetti figlio.</span><span class="sxs-lookup"><span data-stu-id="9e3ba-118">The <xref:System.Windows.Controls.Canvas> panel is a particularly good choice for creating complex drawings because it supports absolute positioning of its child objects.</span></span>  
  
 <span data-ttu-id="9e3ba-119">La <xref:System.Windows.Shapes.Line> classe consente di disegnare una linea tra due punti.</span><span class="sxs-lookup"><span data-stu-id="9e3ba-119">The <xref:System.Windows.Shapes.Line> class enables you to draw a line between two points.</span></span> <span data-ttu-id="9e3ba-120">L'esempio seguente illustra molti modi per specificare le coordinate della riga e le proprietà del tratto.</span><span class="sxs-lookup"><span data-stu-id="9e3ba-120">The following example shows several ways to specify line coordinates and stroke properties.</span></span>  
  
 [!code-xaml[drawingwithshapeelements#LineExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/lineexample.xaml#lineexample1)]  
  
 [!code-cpp[shapesprocedural#ShapesProceduralLine](../../../../samples/snippets/cpp/VS_Snippets_Wpf/ShapesProcedural/CPP/ShapesProcedural.cpp#shapesproceduralline)]
 [!code-csharp[shapesprocedural#ShapesProceduralLine](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ShapesProcedural/Csharp/ShapesProcedural.cs#shapesproceduralline)]
 [!code-vb[shapesprocedural#ShapesProceduralLine](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ShapesProcedural/VisualBasic/ShapesProceduralVB.vb#shapesproceduralline)]  
  
 <span data-ttu-id="9e3ba-121">Nell'immagine riportata di seguito viene eseguito il rendering <xref:System.Windows.Shapes.Line>.</span><span class="sxs-lookup"><span data-stu-id="9e3ba-121">The following image shows the rendered <xref:System.Windows.Shapes.Line>.</span></span>  
  
 <span data-ttu-id="9e3ba-122">![Line illustration](../../../../docs/framework/wpf/graphics-multimedia/media/shape-ovw-line2.gif "shape_ovw_line2")</span><span class="sxs-lookup"><span data-stu-id="9e3ba-122">![Line illustration](../../../../docs/framework/wpf/graphics-multimedia/media/shape-ovw-line2.gif "shape_ovw_line2")</span></span>  
  
 <span data-ttu-id="9e3ba-123">Sebbene il <xref:System.Windows.Shapes.Line> classe fornisce un <xref:System.Windows.Shapes.Shape.Fill%2A> proprietà, impostazione non ha effetto poiché un <xref:System.Windows.Shapes.Line> non presenta un'area.</span><span class="sxs-lookup"><span data-stu-id="9e3ba-123">Although the <xref:System.Windows.Shapes.Line> class does provide a <xref:System.Windows.Shapes.Shape.Fill%2A> property, setting it has no effect because a <xref:System.Windows.Shapes.Line> has no area.</span></span>  
  
 <span data-ttu-id="9e3ba-124">È un'altra forma comune di <xref:System.Windows.Shapes.Ellipse>.</span><span class="sxs-lookup"><span data-stu-id="9e3ba-124">Another common shape is the <xref:System.Windows.Shapes.Ellipse>.</span></span>  <span data-ttu-id="9e3ba-125">Creare un <xref:System.Windows.Shapes.Ellipse> definendo la forma <xref:System.Windows.FrameworkElement.Width%2A> e <xref:System.Windows.FrameworkElement.Height%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="9e3ba-125">Create an <xref:System.Windows.Shapes.Ellipse> by defining the shape's <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties.</span></span> <span data-ttu-id="9e3ba-126">Per disegnare un cerchio, specificare un <xref:System.Windows.Shapes.Ellipse> cui <xref:System.Windows.FrameworkElement.Width%2A> e <xref:System.Windows.FrameworkElement.Height%2A> i valori sono uguali.</span><span class="sxs-lookup"><span data-stu-id="9e3ba-126">To draw a circle, specify an <xref:System.Windows.Shapes.Ellipse> whose <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> values are equal.</span></span>  
  
 [!code-xaml[ShapeOverviews#ShapesOVW1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ShapeOverviews/CS/Window1.xaml#shapesovw1)]  
  
 [!code-csharp[brushesmiscsnippets_procedural_snip#SetBackgroundColorOfShapeCodeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesMiscSnippets_procedural_snip/CSharp/SetBackgroundColorOfShapeExample.cs#setbackgroundcolorofshapecodeexamplewholepage)]
 [!code-vb[brushesmiscsnippets_procedural_snip#SetBackgroundColorOfShapeCodeExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesMiscSnippets_procedural_snip/visualbasic/setbackgroundcolorofshapeexample.vb#setbackgroundcolorofshapecodeexamplewholepage)]  
  
 <span data-ttu-id="9e3ba-127">La figura seguente mostra un esempio di sottoposto a rendering <xref:System.Windows.Shapes.Ellipse>.</span><span class="sxs-lookup"><span data-stu-id="9e3ba-127">The following image shows an example of a rendered <xref:System.Windows.Shapes.Ellipse>.</span></span>  
  
 <span data-ttu-id="9e3ba-128">![Ellipse illustration](../../../../docs/framework/wpf/graphics-multimedia/media/shape-ovw-ellipse2.png "shape_ovw_ellipse2")</span><span class="sxs-lookup"><span data-stu-id="9e3ba-128">![Ellipse illustration](../../../../docs/framework/wpf/graphics-multimedia/media/shape-ovw-ellipse2.png "shape_ovw_ellipse2")</span></span>  
  
<a name="paths"></a>   
## <a name="using-paths-and-geometries"></a><span data-ttu-id="9e3ba-129">Utilizzo di tracciati e geometrie</span><span class="sxs-lookup"><span data-stu-id="9e3ba-129">Using Paths and Geometries</span></span>  
 <span data-ttu-id="9e3ba-130">La <xref:System.Windows.Shapes.Path> classe consente di disegnare curve e forme complesse.</span><span class="sxs-lookup"><span data-stu-id="9e3ba-130">The <xref:System.Windows.Shapes.Path> class enables you to draw curves and complex shapes.</span></span> <span data-ttu-id="9e3ba-131">Vengono descritte queste curve e forme utilizzando <xref:System.Windows.Media.Geometry> oggetti.</span><span class="sxs-lookup"><span data-stu-id="9e3ba-131">These curves and shapes are described using <xref:System.Windows.Media.Geometry> objects.</span></span> <span data-ttu-id="9e3ba-132">Per utilizzare un <xref:System.Windows.Shapes.Path>, si crea un <xref:System.Windows.Media.Geometry> e utilizzarla per impostare il <xref:System.Windows.Shapes.Path> dell'oggetto <xref:System.Windows.Shapes.Path.Data%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="9e3ba-132">To use a <xref:System.Windows.Shapes.Path>, you create a <xref:System.Windows.Media.Geometry> and use it to set the <xref:System.Windows.Shapes.Path> object's <xref:System.Windows.Shapes.Path.Data%2A> property.</span></span>  
  
 <span data-ttu-id="9e3ba-133">Sono disponibili un'ampia gamma di <xref:System.Windows.Media.Geometry> oggetti da selezionare.</span><span class="sxs-lookup"><span data-stu-id="9e3ba-133">There are a variety of <xref:System.Windows.Media.Geometry> objects to choose from.</span></span> <span data-ttu-id="9e3ba-134">Il <xref:System.Windows.Media.LineGeometry>, <xref:System.Windows.Media.RectangleGeometry>, e <xref:System.Windows.Media.EllipseGeometry> classi descrivono forme relativamente semplici.</span><span class="sxs-lookup"><span data-stu-id="9e3ba-134">The <xref:System.Windows.Media.LineGeometry>, <xref:System.Windows.Media.RectangleGeometry>, and <xref:System.Windows.Media.EllipseGeometry> classes describe relatively simple shapes.</span></span> <span data-ttu-id="9e3ba-135">Per creare forme più complesse o curve, utilizzare un <xref:System.Windows.Media.PathGeometry>.</span><span class="sxs-lookup"><span data-stu-id="9e3ba-135">To create more complex shapes or create curves, use a <xref:System.Windows.Media.PathGeometry>.</span></span>  
  
<a name="pathgeometry"></a>   
### <a name="pathgeometry-and-pathsegments"></a><span data-ttu-id="9e3ba-136">PathGeometry e PathSegments</span><span class="sxs-lookup"><span data-stu-id="9e3ba-136">PathGeometry and PathSegments</span></span>  
 <span data-ttu-id="9e3ba-137"><xref:System.Windows.Media.PathGeometry>gli oggetti sono costituiti da uno o più <xref:System.Windows.Media.PathFigure> oggetti; ogni <xref:System.Windows.Media.PathFigure> rappresenta un "importo" diverso o una forma.</span><span class="sxs-lookup"><span data-stu-id="9e3ba-137"><xref:System.Windows.Media.PathGeometry> objects are comprised of one or more <xref:System.Windows.Media.PathFigure> objects; each <xref:System.Windows.Media.PathFigure> represents a different "figure" or shape.</span></span> <span data-ttu-id="9e3ba-138">Ogni <xref:System.Windows.Media.PathFigure> è a sua volta composto da uno o più <xref:System.Windows.Media.PathSegment> oggetti, ognuno dei quali rappresenta una parte collegata della figura o forma.</span><span class="sxs-lookup"><span data-stu-id="9e3ba-138">Each <xref:System.Windows.Media.PathFigure> is itself comprised of one or more <xref:System.Windows.Media.PathSegment> objects, each representing a connected portion of the figure or shape.</span></span> <span data-ttu-id="9e3ba-139">Tipi di segmento includono i seguenti: <xref:System.Windows.Media.LineSegment>, <xref:System.Windows.Media.BezierSegment>, e <xref:System.Windows.Media.ArcSegment>.</span><span class="sxs-lookup"><span data-stu-id="9e3ba-139">Segment types include the following: <xref:System.Windows.Media.LineSegment>, <xref:System.Windows.Media.BezierSegment>, and <xref:System.Windows.Media.ArcSegment>.</span></span>  
  
 <span data-ttu-id="9e3ba-140">Nell'esempio seguente, un <xref:System.Windows.Shapes.Path> viene utilizzato per disegnare una curva di Bézier quadratica.</span><span class="sxs-lookup"><span data-stu-id="9e3ba-140">In the following example, a <xref:System.Windows.Shapes.Path> is used to draw a quadratic Bezier curve.</span></span>  
  
 [!code-xaml[geometrysample#34](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#34)]  
  
 <span data-ttu-id="9e3ba-141">L'immagine seguente illustra la forma sottoposta a rendering.</span><span class="sxs-lookup"><span data-stu-id="9e3ba-141">The following image shows the rendered shape.</span></span>  
  
 <span data-ttu-id="9e3ba-142">![Path illustration](../../../../docs/framework/wpf/graphics-multimedia/media/shape-ovw-path2.gif "shape_ovw_path2")</span><span class="sxs-lookup"><span data-stu-id="9e3ba-142">![Path illustration](../../../../docs/framework/wpf/graphics-multimedia/media/shape-ovw-path2.gif "shape_ovw_path2")</span></span>  
  
 <span data-ttu-id="9e3ba-143">Per ulteriori informazioni su <xref:System.Windows.Media.PathGeometry> e l'altro <xref:System.Windows.Media.Geometry> classi, vedere il [Geometry Overview](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md).</span><span class="sxs-lookup"><span data-stu-id="9e3ba-143">For more information about <xref:System.Windows.Media.PathGeometry> and the other <xref:System.Windows.Media.Geometry> classes, see the [Geometry Overview](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md).</span></span>  
  
<a name="pathdatastring"></a>   
### <a name="xaml-abbreviated-syntax"></a><span data-ttu-id="9e3ba-144">Sintassi abbreviata XAML</span><span class="sxs-lookup"><span data-stu-id="9e3ba-144">XAML Abbreviated Syntax</span></span>  
 <span data-ttu-id="9e3ba-145">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], è inoltre possibile utilizzare una sintassi abbreviata speciale per descrivere un <xref:System.Windows.Shapes.Path>.</span><span class="sxs-lookup"><span data-stu-id="9e3ba-145">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], you may also use a special abbreviated syntax to describe a <xref:System.Windows.Shapes.Path>.</span></span> <span data-ttu-id="9e3ba-146">Nell'esempio seguente viene usata la sintassi abbreviata per disegnare una forma complessa.</span><span class="sxs-lookup"><span data-stu-id="9e3ba-146">In the following example, abbreviated syntax is used to draw a complex shape.</span></span>  
  
```xaml  
      <Path Stroke="DarkGoldenRod" StrokeThickness="3"   
Data="M 100,200 C 100,25 400,350 400,175 H 280" />  
```  
  
 <span data-ttu-id="9e3ba-147">La figura seguente mostra un rendering <xref:System.Windows.Shapes.Path>.</span><span class="sxs-lookup"><span data-stu-id="9e3ba-147">The following image shows a rendered <xref:System.Windows.Shapes.Path>.</span></span>  
  
 <span data-ttu-id="9e3ba-148">![Path illustration](../../../../docs/framework/wpf/graphics-multimedia/media/shape-ovw-path.PNG "shape_ovw_path")</span><span class="sxs-lookup"><span data-stu-id="9e3ba-148">![Path illustration](../../../../docs/framework/wpf/graphics-multimedia/media/shape-ovw-path.PNG "shape_ovw_path")</span></span>  
  
 <span data-ttu-id="9e3ba-149">Il <xref:System.Windows.Shapes.Path.Data%2A> stringa dell'attributo inizia con il comando "moveto", che stabilisce un punto di inizio per il percorso nel sistema di coordinate dell'indicata da M, il <xref:System.Windows.Controls.Canvas>.</span><span class="sxs-lookup"><span data-stu-id="9e3ba-149">The <xref:System.Windows.Shapes.Path.Data%2A> attribute string begins with the "moveto" command, indicated by M, which establishes a start point for the path in the coordinate system of the <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="9e3ba-150"><xref:System.Windows.Shapes.Path>i parametri di dati tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="9e3ba-150"><xref:System.Windows.Shapes.Path> data parameters are case-sensitive.</span></span> <span data-ttu-id="9e3ba-151">La lettera M maiuscola indica un percorso assoluto per il nuovo punto corrente.</span><span class="sxs-lookup"><span data-stu-id="9e3ba-151">The capital M indicates an absolute location for the new current point.</span></span> <span data-ttu-id="9e3ba-152">Una lettera m minuscola indica le coordinate relative.</span><span class="sxs-lookup"><span data-stu-id="9e3ba-152">A lowercase m would indicate relative coordinates.</span></span> <span data-ttu-id="9e3ba-153">Il primo segmento è una curva di Bézier cubica che inizia in corrispondenza del punto (100,200) e termina in corrispondenza del punto (400,175) e viene disegnata usando i due punti di controllo (100,25) e (400,350).</span><span class="sxs-lookup"><span data-stu-id="9e3ba-153">The first segment is a cubic Bezier curve beginning at (100,200) and ending at (400,175), drawn using the two control points (100,25) and (400,350).</span></span> <span data-ttu-id="9e3ba-154">Questo segmento è indicato dal comando C nella <xref:System.Windows.Shapes.Path.Data%2A> stringa dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="9e3ba-154">This segment is indicated by the C command in the <xref:System.Windows.Shapes.Path.Data%2A> attribute string.</span></span> <span data-ttu-id="9e3ba-155">Anche in questo caso la lettera C maiuscola indica un percorso assoluto, mentre la lettera c minuscola indica un percorso relativo.</span><span class="sxs-lookup"><span data-stu-id="9e3ba-155">Again, the capital C indicates an absolute path; the lowercase c would indicate a relative path.</span></span>  
  
 <span data-ttu-id="9e3ba-156">Il secondo segmento inizia con un comando orizzontale assoluto "lineto" H, che specifica una riga disegnata dal punto finale del sottopercorso precedente (400,175) a un nuovo punto finale (280,175).</span><span class="sxs-lookup"><span data-stu-id="9e3ba-156">The second segment begins with an absolute horizontal "lineto" command H, which specifies a line drawn from the preceding subpath's endpoint (400,175) to a new endpoint (280,175).</span></span> <span data-ttu-id="9e3ba-157">Poiché si tratta di un comando orizzontale "lineto", il valore specificato è un *x*-coordinate.</span><span class="sxs-lookup"><span data-stu-id="9e3ba-157">Because it is a horizontal "lineto" command, the value specified is an *x*-coordinate.</span></span>  
  
 <span data-ttu-id="9e3ba-158">Per la sintassi del percorso completo, vedere il <xref:System.Windows.Shapes.Path.Data%2A> riferimento e [creare una forma con PathGeometry](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-shape-by-using-a-pathgeometry.md).</span><span class="sxs-lookup"><span data-stu-id="9e3ba-158">For the complete path syntax, see the <xref:System.Windows.Shapes.Path.Data%2A> reference and [Create a Shape by Using a PathGeometry](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-shape-by-using-a-pathgeometry.md).</span></span>  
  
<a name="fillpaint"></a>   
## <a name="painting-shapes"></a><span data-ttu-id="9e3ba-159">Disegno di oggetti Shape</span><span class="sxs-lookup"><span data-stu-id="9e3ba-159">Painting Shapes</span></span>  
 <span data-ttu-id="9e3ba-160"><xref:System.Windows.Media.Brush>gli oggetti vengono utilizzati per disegnare una forma <xref:System.Windows.Shapes.Shape.Stroke%2A> e <xref:System.Windows.Shapes.Shape.Fill%2A>.</span><span class="sxs-lookup"><span data-stu-id="9e3ba-160"><xref:System.Windows.Media.Brush> objects are used to paint a shape's <xref:System.Windows.Shapes.Shape.Stroke%2A> and <xref:System.Windows.Shapes.Shape.Fill%2A>.</span></span> <span data-ttu-id="9e3ba-161">Nell'esempio seguente, tratto e riempimento di un <xref:System.Windows.Shapes.Ellipse> specificati.</span><span class="sxs-lookup"><span data-stu-id="9e3ba-161">In the following example, the stroke and fill of an <xref:System.Windows.Shapes.Ellipse> are specified.</span></span> <span data-ttu-id="9e3ba-162">Si noti che un input valido per le proprietà del pennello può essere rappresentato da una parola chiave o da un valore di colore esadecimale.</span><span class="sxs-lookup"><span data-stu-id="9e3ba-162">Note that valid input for brush properties can be either a keyword or hexadecimal color value.</span></span> <span data-ttu-id="9e3ba-163">Per ulteriori informazioni sulle parole chiave di colore disponibili, vedere la proprietà del <xref:System.Windows.Media.Colors> classe il <xref:System.Windows.Media> dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="9e3ba-163">For more information about available color keywords, see properties of the <xref:System.Windows.Media.Colors> class in the <xref:System.Windows.Media> namespace.</span></span>  
  
```  
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
  
 <span data-ttu-id="9e3ba-164">Nell'immagine riportata di seguito viene eseguito il rendering <xref:System.Windows.Shapes.Ellipse>.</span><span class="sxs-lookup"><span data-stu-id="9e3ba-164">The following image shows the rendered <xref:System.Windows.Shapes.Ellipse>.</span></span>  
  
 <span data-ttu-id="9e3ba-165">![An ellipse](../../../../docs/framework/wpf/graphics-multimedia/media/shape-ovw-ellipsefill.PNG "shape_ovw_ellipsefill")</span><span class="sxs-lookup"><span data-stu-id="9e3ba-165">![An ellipse](../../../../docs/framework/wpf/graphics-multimedia/media/shape-ovw-ellipsefill.PNG "shape_ovw_ellipsefill")</span></span>  
  
 <span data-ttu-id="9e3ba-166">In alternativa, è possibile utilizzare la sintassi degli elementi di proprietà per creare in modo esplicito un <xref:System.Windows.Media.SolidColorBrush> oggetto da disegnare la forma con un colore a tinta unita.</span><span class="sxs-lookup"><span data-stu-id="9e3ba-166">Alternatively, you can use property element syntax to explicitly create a <xref:System.Windows.Media.SolidColorBrush> object to paint the shape with a solid color.</span></span>  
  
```  
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
  
 <span data-ttu-id="9e3ba-167">La figura seguente mostra la forma sottoposta a rendering.</span><span class="sxs-lookup"><span data-stu-id="9e3ba-167">The following illustration shows the rendered shape.</span></span>  
  
 <span data-ttu-id="9e3ba-168">![SolidColorBrush illustration](../../../../docs/framework/wpf/graphics-multimedia/media/shape-ovw-solidcolorbrush.PNG "shape_ovw_solidcolorbrush")</span><span class="sxs-lookup"><span data-stu-id="9e3ba-168">![SolidColorBrush illustration](../../../../docs/framework/wpf/graphics-multimedia/media/shape-ovw-solidcolorbrush.PNG "shape_ovw_solidcolorbrush")</span></span>  
  
 <span data-ttu-id="9e3ba-169">È anche possibile disegnare il tratto o il riempimento di una forma con sfumature, immagini, motivi e così via.</span><span class="sxs-lookup"><span data-stu-id="9e3ba-169">You can also paint a shape's stroke or fill with gradients, images, patterns, and more.</span></span> <span data-ttu-id="9e3ba-170">Per ulteriori informazioni, vedere il [disegni con colori a tinta unita e sfumature Panoramica](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md).</span><span class="sxs-lookup"><span data-stu-id="9e3ba-170">For more information, see the [Painting with Solid Colors and Gradients Overview](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md).</span></span>  
  
<a name="stretchableshapessection"></a>   
## <a name="stretchable-shapes"></a><span data-ttu-id="9e3ba-171">Oggetti Shape allungabili</span><span class="sxs-lookup"><span data-stu-id="9e3ba-171">Stretchable Shapes</span></span>  
 <span data-ttu-id="9e3ba-172">Il <xref:System.Windows.Shapes.Line>, <xref:System.Windows.Shapes.Path>, <xref:System.Windows.Shapes.Polygon>, <xref:System.Windows.Shapes.Polyline>, e <xref:System.Windows.Shapes.Rectangle> classi hanno una <xref:System.Windows.Shapes.Shape.Stretch%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="9e3ba-172">The <xref:System.Windows.Shapes.Line>, <xref:System.Windows.Shapes.Path>, <xref:System.Windows.Shapes.Polygon>, <xref:System.Windows.Shapes.Polyline>, and <xref:System.Windows.Shapes.Rectangle> classes all have a <xref:System.Windows.Shapes.Shape.Stretch%2A> property.</span></span> <span data-ttu-id="9e3ba-173">Questa proprietà determina come un <xref:System.Windows.Shapes.Shape> il contenuto dell'oggetto (forma da disegnare) viene estesa per riempire il <xref:System.Windows.Shapes.Shape> spazio del layout dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="9e3ba-173">This property determines how a <xref:System.Windows.Shapes.Shape> object's contents (the shape to be drawn) is stretched to fill the <xref:System.Windows.Shapes.Shape> object's layout space.</span></span> <span data-ttu-id="9e3ba-174">A <xref:System.Windows.Shapes.Shape> spazio del layout è la quantità di spazio di <xref:System.Windows.Shapes.Shape> allocata dal sistema di layout, in una esplicita <xref:System.Windows.FrameworkElement.Width%2A> e <xref:System.Windows.FrameworkElement.Height%2A> impostazione o a causa di relativo <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> e <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> impostazioni.</span><span class="sxs-lookup"><span data-stu-id="9e3ba-174">A <xref:System.Windows.Shapes.Shape> object's layout space is the amount of space the <xref:System.Windows.Shapes.Shape> is allocated by the layout system, because of either an explicit <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> setting or because of its <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> and <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> settings.</span></span> <span data-ttu-id="9e3ba-175">Per ulteriori informazioni sul layout di Windows Presentation Foundation, vedere [Layout](../../../../docs/framework/wpf/advanced/layout.md) Panoramica.</span><span class="sxs-lookup"><span data-stu-id="9e3ba-175">For additional information on layout in Windows Presentation Foundation, see [Layout](../../../../docs/framework/wpf/advanced/layout.md) overview.</span></span>  
  
 <span data-ttu-id="9e3ba-176">La proprietà Stretch accetta uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="9e3ba-176">The Stretch property takes one of the following values:</span></span>  
  
-   <span data-ttu-id="9e3ba-177"><xref:System.Windows.Media.Stretch.None>: il <xref:System.Windows.Shapes.Shape> contenuto dell'oggetto non viene estese.</span><span class="sxs-lookup"><span data-stu-id="9e3ba-177"><xref:System.Windows.Media.Stretch.None>: The <xref:System.Windows.Shapes.Shape> object's contents are not stretched.</span></span>  
  
-   <span data-ttu-id="9e3ba-178"><xref:System.Windows.Media.Stretch.Fill>: il <xref:System.Windows.Shapes.Shape> contenuto dell'oggetto è estesa per riempire lo spazio del layout.</span><span class="sxs-lookup"><span data-stu-id="9e3ba-178"><xref:System.Windows.Media.Stretch.Fill>: The <xref:System.Windows.Shapes.Shape> object's contents are stretched to fill its layout space.</span></span>  <span data-ttu-id="9e3ba-179">Le proporzioni non vengono mantenute.</span><span class="sxs-lookup"><span data-stu-id="9e3ba-179">Aspect ratio is not preserved.</span></span>  
  
-   <span data-ttu-id="9e3ba-180"><xref:System.Windows.Media.Stretch.Uniform>: il <xref:System.Windows.Shapes.Shape> contenuto dell'oggetto viene allungato il più possibile per riempire lo spazio del layout mantenendo le proporzioni originali.</span><span class="sxs-lookup"><span data-stu-id="9e3ba-180"><xref:System.Windows.Media.Stretch.Uniform>: The <xref:System.Windows.Shapes.Shape> object's contents are stretched as much as possible to fill its layout space while preserving its original aspect ratio.</span></span>  
  
-   <span data-ttu-id="9e3ba-181"><xref:System.Windows.Media.Stretch.UniformToFill>: il <xref:System.Windows.Shapes.Shape> contenuto dell'oggetto è estesa per riempire completamente lo spazio del layout mantenendo le proporzioni originali.</span><span class="sxs-lookup"><span data-stu-id="9e3ba-181"><xref:System.Windows.Media.Stretch.UniformToFill>: The <xref:System.Windows.Shapes.Shape> object's contents are stretched to completely fill its layout space while preserving its original aspect ratio.</span></span>  
  
 <span data-ttu-id="9e3ba-182">Si noti che, quando un <xref:System.Windows.Shapes.Shape> contenuto dell'oggetto viene allungato, il <xref:System.Windows.Shapes.Shape> viene disegnata la struttura dell'oggetto dopo l'adattamento.</span><span class="sxs-lookup"><span data-stu-id="9e3ba-182">Note that, when a <xref:System.Windows.Shapes.Shape> object's contents are stretched, the <xref:System.Windows.Shapes.Shape> object's outline is painted after the stretching.</span></span>  
  
 <span data-ttu-id="9e3ba-183">Nell'esempio seguente, un <xref:System.Windows.Shapes.Polygon> viene utilizzato per disegnare un triangolo molto piccolo da (0,0) a (0,1) a (1,1).</span><span class="sxs-lookup"><span data-stu-id="9e3ba-183">In the following example, a <xref:System.Windows.Shapes.Polygon> is used to draw a very small triangle from (0,0) to (0,1) to (1,1).</span></span> <span data-ttu-id="9e3ba-184">Il <xref:System.Windows.Shapes.Polygon> dell'oggetto <xref:System.Windows.FrameworkElement.Width%2A> e <xref:System.Windows.FrameworkElement.Height%2A> è impostato su 100, e la proprietà stretch è impostata su Fill.</span><span class="sxs-lookup"><span data-stu-id="9e3ba-184">The <xref:System.Windows.Shapes.Polygon> object's <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> are set to 100, and its stretch property is set to Fill.</span></span> <span data-ttu-id="9e3ba-185">Di conseguenza, il <xref:System.Windows.Shapes.Polygon> il contenuto dell'oggetto (triangolo) è estesa per riempire lo spazio più ampio.</span><span class="sxs-lookup"><span data-stu-id="9e3ba-185">As a result, the <xref:System.Windows.Shapes.Polygon> object's contents (the triangle) are stretched to fill the larger space.</span></span>  
  
```  
...  
<Polygon  
  Points="0,0 0,1 1,1"  
  Fill="Blue"  
  Width="100"  
  Height="100"  
  Stretch="Fill"  
  Stroke="Black"  
  StrokeThickness="2" />  
...  
```  
  
```  
...  
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
...  
```  
  
<a name="transforms"></a>   
## <a name="transforming-shapes"></a><span data-ttu-id="9e3ba-186">Trasformazione degli oggetti Shape</span><span class="sxs-lookup"><span data-stu-id="9e3ba-186">Transforming Shapes</span></span>  
 <span data-ttu-id="9e3ba-187">La <xref:System.Windows.Media.Transform> classe fornisce i mezzi per trasformare le forme in un piano bidimensionale.</span><span class="sxs-lookup"><span data-stu-id="9e3ba-187">The <xref:System.Windows.Media.Transform> class provides the means to transform shapes in a two-dimensional plane.</span></span>  <span data-ttu-id="9e3ba-188">I diversi tipi di trasformazione includono rotazione (<xref:System.Windows.Media.RotateTransform>), scala (<xref:System.Windows.Media.ScaleTransform>), inclinazione (<xref:System.Windows.Media.SkewTransform>) e conversione (<xref:System.Windows.Media.TranslateTransform>).</span><span class="sxs-lookup"><span data-stu-id="9e3ba-188">The different types of transformation include rotation (<xref:System.Windows.Media.RotateTransform>), scale (<xref:System.Windows.Media.ScaleTransform>), skew (<xref:System.Windows.Media.SkewTransform>), and translation (<xref:System.Windows.Media.TranslateTransform>).</span></span>  
  
 <span data-ttu-id="9e3ba-189">Una trasformazione comune da applicare a una forma è una rotazione.</span><span class="sxs-lookup"><span data-stu-id="9e3ba-189">A common transform to apply to a shape is a rotation.</span></span>  <span data-ttu-id="9e3ba-190">Per ruotare una forma, creare un <xref:System.Windows.Media.RotateTransform> e specificare il relativo <xref:System.Windows.Media.RotateTransform.Angle%2A>.</span><span class="sxs-lookup"><span data-stu-id="9e3ba-190">To rotate a shape, create a <xref:System.Windows.Media.RotateTransform> and specify its <xref:System.Windows.Media.RotateTransform.Angle%2A>.</span></span> <span data-ttu-id="9e3ba-191">Un <xref:System.Windows.Media.RotateTransform.Angle%2A> 45 Ruota l'elemento di 45 gradi in senso antiorario; un angolo di 90 Ruota l'elemento di 90 gradi in senso orario; e così via.</span><span class="sxs-lookup"><span data-stu-id="9e3ba-191">An <xref:System.Windows.Media.RotateTransform.Angle%2A> of 45 rotates the element 45 degrees clockwise; an angle of 90 rotates the element 90 degrees clockwise; and so on.</span></span> <span data-ttu-id="9e3ba-192">Impostare il <xref:System.Windows.Media.RotateTransform.CenterX%2A> e <xref:System.Windows.Media.RotateTransform.CenterY%2A> proprietà se si desidera controllare il punto in cui l'elemento viene ruotato.</span><span class="sxs-lookup"><span data-stu-id="9e3ba-192">Set the <xref:System.Windows.Media.RotateTransform.CenterX%2A> and <xref:System.Windows.Media.RotateTransform.CenterY%2A> properties if you want to control the point about which the element is rotated.</span></span> <span data-ttu-id="9e3ba-193">Questi valori di proprietà sono espressi nello spazio delle coordinate dell'elemento trasformato.</span><span class="sxs-lookup"><span data-stu-id="9e3ba-193">These property values are expressed in the coordinate space of the element being transformed.</span></span> <span data-ttu-id="9e3ba-194"><xref:System.Windows.Media.RotateTransform.CenterX%2A>e <xref:System.Windows.Media.RotateTransform.CenterY%2A> hanno valori predefiniti pari a zero.</span><span class="sxs-lookup"><span data-stu-id="9e3ba-194"><xref:System.Windows.Media.RotateTransform.CenterX%2A> and <xref:System.Windows.Media.RotateTransform.CenterY%2A> have default values of zero.</span></span> <span data-ttu-id="9e3ba-195">Infine, applicare il <xref:System.Windows.Media.RotateTransform> all'elemento.</span><span class="sxs-lookup"><span data-stu-id="9e3ba-195">Finally, apply the <xref:System.Windows.Media.RotateTransform> to the element.</span></span> <span data-ttu-id="9e3ba-196">Se non si desidera la trasformazione per influire sul layout, impostare la forma <xref:System.Windows.UIElement.RenderTransform%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="9e3ba-196">If you don't want the transform to affect layout, set the shape's <xref:System.Windows.UIElement.RenderTransform%2A> property.</span></span>  
  
 <span data-ttu-id="9e3ba-197">Nell'esempio seguente, un <xref:System.Windows.Media.RotateTransform> viene utilizzato per ruotare una forma di 45 gradi rispetto alto a sinistra della forma (0,0).</span><span class="sxs-lookup"><span data-stu-id="9e3ba-197">In the following example, a <xref:System.Windows.Media.RotateTransform> is used to rotate a shape 45 degrees about the shape's top left corner (0,0).</span></span>  
  
 [!code-xaml[transformssample#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/RotateTransformExample.xaml#14)]  
  
 <span data-ttu-id="9e3ba-198">Nell'esempio successivo un'altra forma viene ruotata di 45 gradi, ma in questo caso rispetto al punto (25,50).</span><span class="sxs-lookup"><span data-stu-id="9e3ba-198">In the next example, another shape is rotated 45 degrees, but this time it's rotated about the point (25,50).</span></span>  
  
 [!code-xaml[transformssample#15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/RotateTransformExample.xaml#15)]  
  
 <span data-ttu-id="9e3ba-199">L'immagine seguente illustra i risultati dell'applicazione delle due trasformazioni.</span><span class="sxs-lookup"><span data-stu-id="9e3ba-199">The following illustration shows the results of applying the two transforms.</span></span>  
  
 <span data-ttu-id="9e3ba-200">![45 degree rotations with different center points](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-rotatetransform45degrees.gif "wcpsdk_graphicsmm_rotatetransform45degrees")</span><span class="sxs-lookup"><span data-stu-id="9e3ba-200">![45 degree rotations with different center points](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-rotatetransform45degrees.gif "wcpsdk_graphicsmm_rotatetransform45degrees")</span></span>  
  
 <span data-ttu-id="9e3ba-201">Negli esempi precedenti è stata applicata una sola trasformazione a ogni oggetto Shape.</span><span class="sxs-lookup"><span data-stu-id="9e3ba-201">In the previous examples, a single transform was applied to each shape object.</span></span> <span data-ttu-id="9e3ba-202">Per applicare più trasformazioni a una forma (o qualsiasi altro elemento dell'interfaccia utente), utilizzare un <xref:System.Windows.Media.TransformGroup>.</span><span class="sxs-lookup"><span data-stu-id="9e3ba-202">To apply multiple transforms to a shape (or any other UI element), use a <xref:System.Windows.Media.TransformGroup>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e3ba-203">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9e3ba-203">See Also</span></span>  
 [<span data-ttu-id="9e3ba-204">Grafica bidimensionale e creazione di immagini</span><span class="sxs-lookup"><span data-stu-id="9e3ba-204">2D Graphics and Imaging</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)  
 [<span data-ttu-id="9e3ba-205">Cenni sul disegno con colori a tinta unita e sfumature</span><span class="sxs-lookup"><span data-stu-id="9e3ba-205">Painting with Solid Colors and Gradients Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)  
 [<span data-ttu-id="9e3ba-206">Cenni preliminari sulle classi Geometry</span><span class="sxs-lookup"><span data-stu-id="9e3ba-206">Geometry Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)  
 [<span data-ttu-id="9e3ba-207">Procedura dettagliata: Prima applicazione desktop WPF</span><span class="sxs-lookup"><span data-stu-id="9e3ba-207">Walkthrough: My first WPF desktop application</span></span>](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md)  
 [<span data-ttu-id="9e3ba-208">Cenni preliminari sull'animazione</span><span class="sxs-lookup"><span data-stu-id="9e3ba-208">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)
