---
title: "Procedura: disegnare un'area con una sfumatura radiale"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- brushes [WPF], painting with radial gradients
- radial gradients [WPF], painting with
- painting [WPF], with radial gradients
ms.assetid: b5d0fc8a-8986-4796-b003-a75b41a48928
ms.openlocfilehash: 8a53d5d7247f82905816265f7c92b22f287591c5
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452753"
---
# <a name="how-to-paint-an-area-with-a-radial-gradient"></a><span data-ttu-id="7a058-102">Procedura: disegnare un'area con una sfumatura radiale</span><span class="sxs-lookup"><span data-stu-id="7a058-102">How to: Paint an Area with a Radial Gradient</span></span>
<span data-ttu-id="7a058-103">Questo esempio illustra come usare la classe <xref:System.Windows.Media.RadialGradientBrush> per disegnare un'area con una sfumatura radiale.</span><span class="sxs-lookup"><span data-stu-id="7a058-103">This example shows how to use the <xref:System.Windows.Media.RadialGradientBrush> class to paint an area with a radial gradient.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7a058-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="7a058-104">Example</span></span>  
 <span data-ttu-id="7a058-105">Nell'esempio seguente viene usato un <xref:System.Windows.Media.RadialGradientBrush> per disegnare un rettangolo con una sfumatura radiale che passa da giallo a rosso a blu a verde limone.</span><span class="sxs-lookup"><span data-stu-id="7a058-105">The following example uses a <xref:System.Windows.Media.RadialGradientBrush> to paint a rectangle with a radial gradient that transitions from yellow to red to blue to lime green.</span></span>  
  
 [!code-csharp[BrushesIntroduction_snip#SimpleRadialGradientExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/RadialGradientBrushSnippet.cs#simpleradialgradientexamplewholepage)]
 [!code-vb[BrushesIntroduction_snip#SimpleRadialGradientExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/radialgradientbrushsnippet.vb#simpleradialgradientexamplewholepage)]
 [!code-xaml[BrushesIntroduction_snip#SimpleRadialGradientExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/RadialGradientBrushSnippet.xaml#simpleradialgradientexamplewholepage)]  
  
 <span data-ttu-id="7a058-106">Nella figura seguente viene illustrata la sfumatura dell'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="7a058-106">The following illustration shows the gradient from the preceding example.</span></span> <span data-ttu-id="7a058-107">I cursori della sfumatura sono stati evidenziati.</span><span class="sxs-lookup"><span data-stu-id="7a058-107">The gradient's stops have been highlighted.</span></span>  
  
 <span data-ttu-id="7a058-108">![Cursori sfumatura in una sfumatura radiale](./media/wcpsdk-graphicsmm-4gradientstops-rg.png "wcpsdk_graphicsmm_4gradientstops_rg")</span><span class="sxs-lookup"><span data-stu-id="7a058-108">![Gradient stops in a radial gradient](./media/wcpsdk-graphicsmm-4gradientstops-rg.png "wcpsdk_graphicsmm_4gradientstops_rg")</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7a058-109">Negli esempi di questo argomento viene utilizzato il sistema di coordinate predefinito per l'impostazione dei punti di controllo.</span><span class="sxs-lookup"><span data-stu-id="7a058-109">The examples in this topic use the default coordinate system for setting control points.</span></span> <span data-ttu-id="7a058-110">Il sistema di coordinate predefinito è relativo a un rettangolo di delimitazione: 0 indica lo 0% del rettangolo di delimitazione e 1 indica il 100% del rettangolo di delimitazione.</span><span class="sxs-lookup"><span data-stu-id="7a058-110">The default coordinate system is relative to a bounding box: 0 indicates 0 percent of the bounding box, and 1 indicates 100 percent of the bounding box.</span></span> <span data-ttu-id="7a058-111">È possibile modificare questo sistema di coordinate impostando la proprietà <xref:System.Windows.Media.GradientBrush.MappingMode%2A> sul valore <xref:System.Windows.Media.BrushMappingMode.Absolute>.</span><span class="sxs-lookup"><span data-stu-id="7a058-111">You can change this coordinate system by setting the <xref:System.Windows.Media.GradientBrush.MappingMode%2A> property to the value <xref:System.Windows.Media.BrushMappingMode.Absolute>.</span></span> <span data-ttu-id="7a058-112">Un sistema di coordinate assoluto non è relativo a un rettangolo di selezione.</span><span class="sxs-lookup"><span data-stu-id="7a058-112">An absolute coordinate system is not relative to a bounding box.</span></span> <span data-ttu-id="7a058-113">I valori vengono interpretati direttamente nello spazio locale.</span><span class="sxs-lookup"><span data-stu-id="7a058-113">Values are interpreted directly in local space.</span></span>  
  
 <span data-ttu-id="7a058-114">Per ulteriori <xref:System.Windows.Media.RadialGradientBrush> esempi, vedere l' [esempio pennelli](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes).</span><span class="sxs-lookup"><span data-stu-id="7a058-114">For additional <xref:System.Windows.Media.RadialGradientBrush> examples, see the [Brushes Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes).</span></span> <span data-ttu-id="7a058-115">Per ulteriori informazioni sui gradienti e sugli altri tipi di pennelli, vedere [Cenni preliminari sul disegno con colori a tinta unita e sfumature](painting-with-solid-colors-and-gradients-overview.md).</span><span class="sxs-lookup"><span data-stu-id="7a058-115">For more information about gradients and other types of brushes, see [Painting with Solid Colors and Gradients Overview](painting-with-solid-colors-and-gradients-overview.md).</span></span>
