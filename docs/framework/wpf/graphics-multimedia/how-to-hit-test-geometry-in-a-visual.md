---
title: 'Procedura: Eseguire un hit test della geometria in un oggetto visivo'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hit tests [WPF], on visual objects comprising Geometry objects [WPF]
- visual objects [WPF], hit tests on
- Geometry objects [WPF], visual objects comprising
ms.assetid: 8bf2643f-d7f9-4cb4-9ea6-5b893c23200d
ms.openlocfilehash: 87b626e575d889447ef061d1ed62ef28efe5dfeb
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59227340"
---
# <a name="how-to-hit-test-geometry-in-a-visual"></a><span data-ttu-id="e03c2-102">Procedura: Eseguire un hit test della geometria in un oggetto visivo</span><span class="sxs-lookup"><span data-stu-id="e03c2-102">How to: Hit Test Geometry in a Visual</span></span>
<span data-ttu-id="e03c2-103">In questo esempio illustra come eseguire un hit test su un oggetto visivo costituito da uno o più <xref:System.Windows.Media.Geometry> oggetti.</span><span class="sxs-lookup"><span data-stu-id="e03c2-103">This example shows how to perform a hit test on a visual object that is composed of one or more <xref:System.Windows.Media.Geometry> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e03c2-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="e03c2-104">Example</span></span>  
 <span data-ttu-id="e03c2-105">Nell'esempio seguente viene illustrato come recuperare il <xref:System.Windows.Media.DrawingGroup> da un oggetto visivo che usa il <xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A> (metodo).</span><span class="sxs-lookup"><span data-stu-id="e03c2-105">The following example shows how to retrieve the <xref:System.Windows.Media.DrawingGroup> from a visual object that uses the <xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A> method.</span></span> <span data-ttu-id="e03c2-106">Viene quindi eseguito un hit test sul contenuto di cui viene eseguito rendering di ogni disegno nel <xref:System.Windows.Media.DrawingGroup> per determinare la geometria raggiunta.</span><span class="sxs-lookup"><span data-stu-id="e03c2-106">A hit test is then performed on the rendered content of each drawing in the <xref:System.Windows.Media.DrawingGroup> to determine which geometry was hit.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e03c2-107">Nella maggior parte dei casi, utilizzerebbe il <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> metodo per determinare se un punto interseca un contenuto di cui viene eseguito il rendering di un oggetto visivo.</span><span class="sxs-lookup"><span data-stu-id="e03c2-107">In most cases, you would use the <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> method to determine whether a point intersects any of the rendered content of a visual.</span></span>  
  
 [!code-csharp[VisualsOverview#VisualsOverviewSnippet4](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsOverview/CSharp/Window1.xaml.cs#visualsoverviewsnippet4)]
 [!code-vb[VisualsOverview#VisualsOverviewSnippet4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsOverview/visualbasic/window1.xaml.vb#visualsoverviewsnippet4)]  
  
 <span data-ttu-id="e03c2-108">Il <xref:System.Windows.Media.Geometry.FillContains%2A> metodo è un metodo di overload che consente di eseguire un hit test utilizzando un oggetto specificato <xref:System.Windows.Point> o <xref:System.Windows.Media.Geometry>.</span><span class="sxs-lookup"><span data-stu-id="e03c2-108">The <xref:System.Windows.Media.Geometry.FillContains%2A> method is an overloaded method that allows you to hit test by using a specified <xref:System.Windows.Point> or <xref:System.Windows.Media.Geometry>.</span></span> <span data-ttu-id="e03c2-109">Se viene tracciata una geometria, il tratto può estendersi oltre i limiti del riempimento.</span><span class="sxs-lookup"><span data-stu-id="e03c2-109">If a geometry is stroked, the stroke can extend outside the fill bounds.</span></span> <span data-ttu-id="e03c2-110">In questo caso, è possibile chiamare <xref:System.Windows.Media.Geometry.StrokeContains%2A> oltre a <xref:System.Windows.Media.Geometry.FillContains%2A>.</span><span class="sxs-lookup"><span data-stu-id="e03c2-110">In which case, you may want to call <xref:System.Windows.Media.Geometry.StrokeContains%2A> in addition to <xref:System.Windows.Media.Geometry.FillContains%2A>.</span></span>  
  
 <span data-ttu-id="e03c2-111">È anche possibile fornire un <xref:System.Windows.Media.ToleranceType> usato ai fini di appiattimento di Bézier.</span><span class="sxs-lookup"><span data-stu-id="e03c2-111">You can also provide a <xref:System.Windows.Media.ToleranceType> that is used for the purposes of Bezier flattening.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e03c2-112">Questo esempio non prende in considerazione eventuali trasformazioni o ritagli applicabili alla geometria.</span><span class="sxs-lookup"><span data-stu-id="e03c2-112">This sample does not take into account any transforms or clipping that may be applied to the geometry.</span></span> <span data-ttu-id="e03c2-113">L'esempio, inoltre, non funziona con un controllo con stili, poiché a esso non saranno direttamente associati disegni.</span><span class="sxs-lookup"><span data-stu-id="e03c2-113">In addition, this sample will not work with a styled control, since it does not have any drawings directly associated with it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e03c2-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e03c2-114">See also</span></span>

- [<span data-ttu-id="e03c2-115">Hit testing a livello visivo</span><span class="sxs-lookup"><span data-stu-id="e03c2-115">Hit Testing in the Visual Layer</span></span>](hit-testing-in-the-visual-layer.md)
- [<span data-ttu-id="e03c2-116">Eseguire un hit test utilizzando la geometria come parametro</span><span class="sxs-lookup"><span data-stu-id="e03c2-116">Hit Test Using Geometry as a Parameter</span></span>](how-to-hit-test-using-geometry-as-a-parameter.md)
