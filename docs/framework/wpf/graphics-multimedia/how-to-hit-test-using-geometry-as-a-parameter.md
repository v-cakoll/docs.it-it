---
title: 'Procedura: Eseguire un hit test usando la geometria come parametro'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hit tests [WPF], on visual objects using Geometry objects [WPF]
- visual objects [WPF], hit tests on
- Geometry objects [WPF], hit tests on visual objects [WPF]
ms.assetid: 6c8bdbf2-19e0-4fbb-bf89-c1252b2ebc61
ms.openlocfilehash: 8bed7784b00f49178c9a87def74b62f7ce620ec7
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69923399"
---
# <a name="how-to-hit-test-using-geometry-as-a-parameter"></a><span data-ttu-id="9907b-102">Procedura: Eseguire un hit test usando la geometria come parametro</span><span class="sxs-lookup"><span data-stu-id="9907b-102">How to: Hit Test Using Geometry as a Parameter</span></span>
<span data-ttu-id="9907b-103">Questo esempio illustra come eseguire un hit test su un oggetto visivo usando un <xref:System.Windows.Media.Geometry> come parametro dell'hit test.</span><span class="sxs-lookup"><span data-stu-id="9907b-103">This example shows how to perform a hit test on a visual object using a <xref:System.Windows.Media.Geometry> as a hit test parameter.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9907b-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="9907b-104">Example</span></span>  
 <span data-ttu-id="9907b-105">Nell'esempio seguente viene illustrato come impostare un hit test utilizzando <xref:System.Windows.Media.GeometryHitTestParameters> per il <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="9907b-105">The following example shows how to set up a hit test using <xref:System.Windows.Media.GeometryHitTestParameters> for the <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> method.</span></span> <span data-ttu-id="9907b-106">Il <xref:System.Windows.Point> valore passato `OnMouseDown` al metodo viene usato per creare un <xref:System.Windows.Media.Geometry> oggetto per espandere l'intervallo dell'hit test.</span><span class="sxs-lookup"><span data-stu-id="9907b-106">The <xref:System.Windows.Point> value that is passed to the `OnMouseDown` method is used to create a <xref:System.Windows.Media.Geometry> object in order to expand the range of the hit test.</span></span>  
  
 [!code-csharp[HitTestingOverview#HitTestingOverviewSnippet10](~/samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/GeometryHitTest.cs#hittestingoverviewsnippet10)]
 [!code-vb[HitTestingOverview#HitTestingOverviewSnippet10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/geometryhittest.vb#hittestingoverviewsnippet10)]  
  
 <span data-ttu-id="9907b-107">La <xref:System.Windows.Media.GeometryHitTestResult.IntersectionDetail%2A> proprietà di <xref:System.Windows.Media.GeometryHitTestResult> fornisce informazioni sui risultati di un <xref:System.Windows.Media.Geometry> hit test che usa come parametro dell'hit test.</span><span class="sxs-lookup"><span data-stu-id="9907b-107">The <xref:System.Windows.Media.GeometryHitTestResult.IntersectionDetail%2A> property of <xref:System.Windows.Media.GeometryHitTestResult> provides information about the results of a hit test that uses a <xref:System.Windows.Media.Geometry> as a hit test parameter.</span></span> <span data-ttu-id="9907b-108">La figura seguente mostra la relazione tra la geometria di hit test (cerchio blu) e il contenuto sottoposto a rendering dell'oggetto visivo di destinazione (quadrato rosso).</span><span class="sxs-lookup"><span data-stu-id="9907b-108">The following illustration shows the relationship between the hit test geometry (the blue circle) and the rendered content of the target visual object (the red square).</span></span>  
  
 ![Diagramma che mostra IntersectionDetail usati nell'hit testing.](./media/how-to-hit-test-using-geometry-as-a-parameter/intersectiondetail-hit-test.png)  
  
 <span data-ttu-id="9907b-110">Nell'esempio seguente viene illustrato come implementare un callback di hit test quando <xref:System.Windows.Media.Geometry> un oggetto viene utilizzato come parametro dell'hit test.</span><span class="sxs-lookup"><span data-stu-id="9907b-110">The following example shows how to implement a hit test callback when a <xref:System.Windows.Media.Geometry> is used as a hit test parameter.</span></span> <span data-ttu-id="9907b-111">Viene `result` eseguito il cast del parametro <xref:System.Windows.Media.GeometryHitTestResult> a un oggetto per <xref:System.Windows.Media.GeometryHitTestResult.IntersectionDetail%2A> recuperare il valore della proprietà.</span><span class="sxs-lookup"><span data-stu-id="9907b-111">The `result` parameter is cast to a <xref:System.Windows.Media.GeometryHitTestResult> in order to retrieve the value of the <xref:System.Windows.Media.GeometryHitTestResult.IntersectionDetail%2A> property.</span></span> <span data-ttu-id="9907b-112">Il valore della proprietà consente di determinare se il <xref:System.Windows.Media.Geometry> parametro dell'hit test è completamente o parzialmente contenuto all'interno del contenuto sottoposto a rendering della destinazione dell'hit test.</span><span class="sxs-lookup"><span data-stu-id="9907b-112">The property value allows you to determine if the <xref:System.Windows.Media.Geometry> hit test parameter is fully or partially contained within the rendered content of the hit test target.</span></span> <span data-ttu-id="9907b-113">In questo caso, il codice di esempio aggiunge i risultati dell'hit test all'elenco solo per gli oggetti visivi completamente contenuti all'interno del limite della destinazione.</span><span class="sxs-lookup"><span data-stu-id="9907b-113">In this case, the sample code is only adding hit test results to the list for visuals that are fully contained within the target boundary.</span></span>  
  
 [!code-csharp[HitTestingOverview#HitTestingOverviewSnippet11](~/samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/GeometryHitTest.cs#hittestingoverviewsnippet11)]
 [!code-vb[HitTestingOverview#HitTestingOverviewSnippet11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/geometryhittest.vb#hittestingoverviewsnippet11)]  
  
> [!NOTE]
> <span data-ttu-id="9907b-114">Il <xref:System.Windows.Media.HitTestResult> callback non deve essere chiamato quando il dettaglio di intersezione è <xref:System.Windows.Media.IntersectionDetail.Empty>.</span><span class="sxs-lookup"><span data-stu-id="9907b-114">The <xref:System.Windows.Media.HitTestResult> callback should not be called when the intersection detail is <xref:System.Windows.Media.IntersectionDetail.Empty>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9907b-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9907b-115">See also</span></span>

- [<span data-ttu-id="9907b-116">Hit testing a livello visivo</span><span class="sxs-lookup"><span data-stu-id="9907b-116">Hit Testing in the Visual Layer</span></span>](hit-testing-in-the-visual-layer.md)
- [<span data-ttu-id="9907b-117">Eseguire un hit test della geometria in un oggetto Visual</span><span class="sxs-lookup"><span data-stu-id="9907b-117">Hit Test Geometry in a Visual</span></span>](how-to-hit-test-geometry-in-a-visual.md)
