---
title: 'Procedura: Eseguire un hit test utilizzando la geometria come parametro'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hit tests [WPF], on visual objects using Geometry objects [WPF]
- visual objects [WPF], hit tests on
- Geometry objects [WPF], hit tests on visual objects [WPF]
ms.assetid: 6c8bdbf2-19e0-4fbb-bf89-c1252b2ebc61
ms.openlocfilehash: d52f8da891ecdf632952c441f94aab4c0b56da7f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54564253"
---
# <a name="how-to-hit-test-using-geometry-as-a-parameter"></a><span data-ttu-id="6616c-102">Procedura: Eseguire un hit test utilizzando la geometria come parametro</span><span class="sxs-lookup"><span data-stu-id="6616c-102">How to: Hit Test Using Geometry as a Parameter</span></span>
<span data-ttu-id="6616c-103">Questo esempio viene illustrato come eseguire un hit test su un oggetto visivo usando un <xref:System.Windows.Media.Geometry> come relativo parametro di test.</span><span class="sxs-lookup"><span data-stu-id="6616c-103">This example shows how to perform a hit test on a visual object using a <xref:System.Windows.Media.Geometry> as a hit test parameter.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6616c-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="6616c-104">Example</span></span>  
 <span data-ttu-id="6616c-105">Nell'esempio seguente viene illustrato come impostare un hit test utilizzando <xref:System.Windows.Media.GeometryHitTestParameters> per il <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> (metodo).</span><span class="sxs-lookup"><span data-stu-id="6616c-105">The following example shows how to set up a hit test using <xref:System.Windows.Media.GeometryHitTestParameters> for the <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> method.</span></span> <span data-ttu-id="6616c-106">Il <xref:System.Windows.Point> valore passato per il `OnMouseDown` metodo viene utilizzato per creare un <xref:System.Windows.Media.Geometry> oggetti ed espandere l'intervallo dell'hit test.</span><span class="sxs-lookup"><span data-stu-id="6616c-106">The <xref:System.Windows.Point> value that is passed to the `OnMouseDown` method is used to create a <xref:System.Windows.Media.Geometry> object in order to expand the range of the hit test.</span></span>  
  
 [!code-csharp[HitTestingOverview#HitTestingOverviewSnippet10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/GeometryHitTest.cs#hittestingoverviewsnippet10)]
 [!code-vb[HitTestingOverview#HitTestingOverviewSnippet10](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/geometryhittest.vb#hittestingoverviewsnippet10)]  
  
 <span data-ttu-id="6616c-107">Il <xref:System.Windows.Media.GeometryHitTestResult.IntersectionDetail%2A> proprietà di <xref:System.Windows.Media.GeometryHitTestResult> fornisce informazioni sui risultati di un hit test che usa un <xref:System.Windows.Media.Geometry> come relativo parametro di test.</span><span class="sxs-lookup"><span data-stu-id="6616c-107">The <xref:System.Windows.Media.GeometryHitTestResult.IntersectionDetail%2A> property of <xref:System.Windows.Media.GeometryHitTestResult> provides information about the results of a hit test that uses a <xref:System.Windows.Media.Geometry> as a hit test parameter.</span></span> <span data-ttu-id="6616c-108">La figura seguente mostra la relazione tra la geometria di hit test (cerchio blu) e il contenuto sottoposto a rendering dell'oggetto visivo di destinazione (quadrato rosso).</span><span class="sxs-lookup"><span data-stu-id="6616c-108">The following illustration shows the relationship between the hit test geometry (the blue circle) and the rendered content of the target visual object (the red square).</span></span>  
  
 <span data-ttu-id="6616c-109">![Diagramma di IntersectionDetail usato nell'hit testing](../../../../docs/framework/wpf/graphics-multimedia/media/intersectiondetail01.png "IntersectionDetail01")</span><span class="sxs-lookup"><span data-stu-id="6616c-109">![Diagram of IntersectionDetail used in hit testing](../../../../docs/framework/wpf/graphics-multimedia/media/intersectiondetail01.png "IntersectionDetail01")</span></span>  
<span data-ttu-id="6616c-110">Intersezione tra la geometria di hit test e l'oggetto visivo di destinazione</span><span class="sxs-lookup"><span data-stu-id="6616c-110">Intersection between hit test geometry and target visual object</span></span>  
  
 <span data-ttu-id="6616c-111">Nell'esempio seguente viene illustrato come implementare un callback dell'hit test quando un <xref:System.Windows.Media.Geometry> viene usato come parametro di hit test.</span><span class="sxs-lookup"><span data-stu-id="6616c-111">The following example shows how to implement a hit test callback when a <xref:System.Windows.Media.Geometry> is used as a hit test parameter.</span></span> <span data-ttu-id="6616c-112">Il `result` parametro viene eseguito il cast a un <xref:System.Windows.Media.GeometryHitTestResult> per recuperare il valore della <xref:System.Windows.Media.GeometryHitTestResult.IntersectionDetail%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="6616c-112">The `result` parameter is cast to a <xref:System.Windows.Media.GeometryHitTestResult> in order to retrieve the value of the <xref:System.Windows.Media.GeometryHitTestResult.IntersectionDetail%2A> property.</span></span> <span data-ttu-id="6616c-113">Il valore della proprietà consente di determinare se il <xref:System.Windows.Media.Geometry> parametro di hit test è contenuto completamente o parzialmente all'interno di contenuto di cui viene eseguito il rendering di destinazione dell'hit test.</span><span class="sxs-lookup"><span data-stu-id="6616c-113">The property value allows you to determine if the <xref:System.Windows.Media.Geometry> hit test parameter is fully or partially contained within the rendered content of the hit test target.</span></span> <span data-ttu-id="6616c-114">In questo caso, il codice di esempio aggiunge i risultati dell'hit test all'elenco solo per gli oggetti visivi completamente contenuti all'interno del limite della destinazione.</span><span class="sxs-lookup"><span data-stu-id="6616c-114">In this case, the sample code is only adding hit test results to the list for visuals that are fully contained within the target boundary.</span></span>  
  
 [!code-csharp[HitTestingOverview#HitTestingOverviewSnippet11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/GeometryHitTest.cs#hittestingoverviewsnippet11)]
 [!code-vb[HitTestingOverview#HitTestingOverviewSnippet11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/geometryhittest.vb#hittestingoverviewsnippet11)]  
  
> [!NOTE]
>  <span data-ttu-id="6616c-115">Il <xref:System.Windows.Media.HitTestResult> callback non deve essere chiamato una volta il dettaglio dell'intersezione <xref:System.Windows.Media.IntersectionDetail.Empty>.</span><span class="sxs-lookup"><span data-stu-id="6616c-115">The <xref:System.Windows.Media.HitTestResult> callback should not be called when the intersection detail is <xref:System.Windows.Media.IntersectionDetail.Empty>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6616c-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6616c-116">See also</span></span>
- [<span data-ttu-id="6616c-117">Hit testing a livello visivo</span><span class="sxs-lookup"><span data-stu-id="6616c-117">Hit Testing in the Visual Layer</span></span>](../../../../docs/framework/wpf/graphics-multimedia/hit-testing-in-the-visual-layer.md)
- [<span data-ttu-id="6616c-118">Eseguire un hit test della geometria in un oggetto Visual</span><span class="sxs-lookup"><span data-stu-id="6616c-118">Hit Test Geometry in a Visual</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-hit-test-geometry-in-a-visual.md)
