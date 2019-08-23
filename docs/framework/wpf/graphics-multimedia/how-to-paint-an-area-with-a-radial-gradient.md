---
title: "Procedura: Disegnare un'area con una sfumatura radiale"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- brushes [WPF], painting with radial gradients
- radial gradients [WPF], painting with
- painting [WPF], with radial gradients
ms.assetid: b5d0fc8a-8986-4796-b003-a75b41a48928
ms.openlocfilehash: 5762ef1a1526ba6f004917c8a947e35ce731c86d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69916095"
---
# <a name="how-to-paint-an-area-with-a-radial-gradient"></a><span data-ttu-id="e170f-102">Procedura: Disegnare un'area con una sfumatura radiale</span><span class="sxs-lookup"><span data-stu-id="e170f-102">How to: Paint an Area with a Radial Gradient</span></span>
<span data-ttu-id="e170f-103">Questo esempio illustra come usare la <xref:System.Windows.Media.RadialGradientBrush> classe per disegnare un'area con una sfumatura radiale.</span><span class="sxs-lookup"><span data-stu-id="e170f-103">This example shows how to use the <xref:System.Windows.Media.RadialGradientBrush> class to paint an area with a radial gradient.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e170f-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="e170f-104">Example</span></span>  
 <span data-ttu-id="e170f-105">Nell'esempio seguente viene usato <xref:System.Windows.Media.RadialGradientBrush> un oggetto per disegnare un rettangolo con una sfumatura radiale che passa da giallo a rosso a blu a verde limone.</span><span class="sxs-lookup"><span data-stu-id="e170f-105">The following example uses a <xref:System.Windows.Media.RadialGradientBrush> to paint a rectangle with a radial gradient that transitions from yellow to red to blue to lime green.</span></span>  
  
 [!code-csharp[BrushesIntroduction_snip#SimpleRadialGradientExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/RadialGradientBrushSnippet.cs#simpleradialgradientexamplewholepage)]
 [!code-vb[BrushesIntroduction_snip#SimpleRadialGradientExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/radialgradientbrushsnippet.vb#simpleradialgradientexamplewholepage)]
 [!code-xaml[BrushesIntroduction_snip#SimpleRadialGradientExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/RadialGradientBrushSnippet.xaml#simpleradialgradientexamplewholepage)]  
  
 <span data-ttu-id="e170f-106">Nella figura seguente viene illustrata la sfumatura dell'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="e170f-106">The following illustration shows the gradient from the preceding example.</span></span> <span data-ttu-id="e170f-107">I cursori della sfumatura sono stati evidenziati.</span><span class="sxs-lookup"><span data-stu-id="e170f-107">The gradient's stops have been highlighted.</span></span>  
  
 <span data-ttu-id="e170f-108">![Cursori sfumatura in una sfumatura radiale](./media/wcpsdk-graphicsmm-4gradientstops-rg.png "wcpsdk_graphicsmm_4gradientstops_rg")</span><span class="sxs-lookup"><span data-stu-id="e170f-108">![Gradient stops in a radial gradient](./media/wcpsdk-graphicsmm-4gradientstops-rg.png "wcpsdk_graphicsmm_4gradientstops_rg")</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e170f-109">Negli esempi di questo argomento viene utilizzato il sistema di coordinate predefinito per l'impostazione dei punti di controllo.</span><span class="sxs-lookup"><span data-stu-id="e170f-109">The examples in this topic use the default coordinate system for setting control points.</span></span> <span data-ttu-id="e170f-110">Il sistema di coordinate predefinito è relativo a un rettangolo di delimitazione: 0 indica lo 0% del riquadro e 1 indica il 100% del riquadro.</span><span class="sxs-lookup"><span data-stu-id="e170f-110">The default coordinate system is relative to a bounding box: 0 indicates 0 percent of the bounding box, and 1 indicates 100 percent of the bounding box.</span></span> <span data-ttu-id="e170f-111">È possibile modificare questo sistema di coordinate impostando <xref:System.Windows.Media.GradientBrush.MappingMode%2A> la proprietà sul valore <xref:System.Windows.Media.BrushMappingMode.Absolute>.</span><span class="sxs-lookup"><span data-stu-id="e170f-111">You can change this coordinate system by setting the <xref:System.Windows.Media.GradientBrush.MappingMode%2A> property to the value <xref:System.Windows.Media.BrushMappingMode.Absolute>.</span></span> <span data-ttu-id="e170f-112">Un sistema di coordinate assoluto non è relativo a un rettangolo di selezione.</span><span class="sxs-lookup"><span data-stu-id="e170f-112">An absolute coordinate system is not relative to a bounding box.</span></span> <span data-ttu-id="e170f-113">I valori vengono interpretati direttamente nello spazio locale.</span><span class="sxs-lookup"><span data-stu-id="e170f-113">Values are interpreted directly in local space.</span></span>  
  
 <span data-ttu-id="e170f-114">Per altri <xref:System.Windows.Media.RadialGradientBrush> esempi, vedere l' [esempio](https://go.microsoft.com/fwlink/?LinkID=159973)di pennelli.</span><span class="sxs-lookup"><span data-stu-id="e170f-114">For additional <xref:System.Windows.Media.RadialGradientBrush> examples, see the [Brushes Sample](https://go.microsoft.com/fwlink/?LinkID=159973).</span></span> <span data-ttu-id="e170f-115">Per ulteriori informazioni sui gradienti e sugli altri tipi di pennelli, vedere [Cenni preliminari sul disegno con colori a tinta unita e sfumature](painting-with-solid-colors-and-gradients-overview.md).</span><span class="sxs-lookup"><span data-stu-id="e170f-115">For more information about gradients and other types of brushes, see [Painting with Solid Colors and Gradients Overview](painting-with-solid-colors-and-gradients-overview.md).</span></span>
