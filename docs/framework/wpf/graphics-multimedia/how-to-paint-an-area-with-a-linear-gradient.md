---
title: "Procedura: disegnare un'area con una sfumatura lineare"
ms.date: 03/30/2017
helpviewer_keywords:
- linear gradients [WPF], painting with
- brushes [WPF], painting with linear gradients
- painting [WPF], with linear gradients
ms.assetid: 00e0cd04-48c0-4ec5-850e-d321beb37a34
ms.openlocfilehash: 76c491632911c48db34d932ba3895278591378a5
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452766"
---
# <a name="how-to-paint-an-area-with-a-linear-gradient"></a><span data-ttu-id="5e4c2-102">Procedura: disegnare un'area con una sfumatura lineare</span><span class="sxs-lookup"><span data-stu-id="5e4c2-102">How to: Paint an Area with a Linear Gradient</span></span>
<span data-ttu-id="5e4c2-103">Questo esempio illustra come usare la classe <xref:System.Windows.Media.LinearGradientBrush> per disegnare un'area con una sfumatura lineare.</span><span class="sxs-lookup"><span data-stu-id="5e4c2-103">This example shows how to use the <xref:System.Windows.Media.LinearGradientBrush> class to paint an area with a linear gradient.</span></span> <span data-ttu-id="5e4c2-104">Nell'esempio seguente, il <xref:System.Windows.Shapes.Shape.Fill%2A> di un <xref:System.Windows.Shapes.Rectangle> viene disegnato con una sfumatura lineare diagonale che passa da giallo a rosso a blu a verde limone.</span><span class="sxs-lookup"><span data-stu-id="5e4c2-104">In the following example, the <xref:System.Windows.Shapes.Shape.Fill%2A> of a <xref:System.Windows.Shapes.Rectangle> is painted with a diagonal linear gradient that transitions from yellow to red to blue to lime green.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5e4c2-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="5e4c2-105">Example</span></span>  
 [!code-xaml[GradientBrushExamples_snip#DiagonalGradient1XAML](~/samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#diagonalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#DiagonalGradient1CSharp](~/samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#diagonalgradient1csharp)]  
  
 <span data-ttu-id="5e4c2-106">Nella figura seguente viene illustrata la sfumatura creata dall'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="5e4c2-106">The following illustration shows the gradient created by the previous example.</span></span>  
  
 <span data-ttu-id="5e4c2-107">![Sfumatura lineare diagonale](./media/graphicsmm-diagonallgb.jpg "graphicsmm_DiagonalLGB")</span><span class="sxs-lookup"><span data-stu-id="5e4c2-107">![Diagonal linear gradient](./media/graphicsmm-diagonallgb.jpg "graphicsmm_DiagonalLGB")</span></span>  
  
 <span data-ttu-id="5e4c2-108">Per creare una sfumatura lineare orizzontale, modificare il <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> e <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> del <xref:System.Windows.Media.LinearGradientBrush> in (0, 0,5) e (1, 0,5).</span><span class="sxs-lookup"><span data-stu-id="5e4c2-108">To create a horizontal linear gradient, change the <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> and <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> of the <xref:System.Windows.Media.LinearGradientBrush> to (0,0.5) and (1,0.5).</span></span> <span data-ttu-id="5e4c2-109">Nell'esempio seguente, un <xref:System.Windows.Shapes.Rectangle> viene disegnato con una sfumatura lineare orizzontale.</span><span class="sxs-lookup"><span data-stu-id="5e4c2-109">In the following example, a <xref:System.Windows.Shapes.Rectangle> is painted with a horizontal linear gradient.</span></span>  
  
 [!code-xaml[GradientBrushExamples_snip#HorizontalGradient1XAML](~/samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#horizontalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#HorizontalGradient1CSharp](~/samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#horizontalgradient1csharp)]  
  
 <span data-ttu-id="5e4c2-110">Nella figura seguente viene illustrata la sfumatura creata dall'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="5e4c2-110">The following illustration shows the gradient created by the previous example.</span></span>  
  
 <span data-ttu-id="5e4c2-111">![Sfumatura lineare orizzontale](./media/graphicsmm-horizontallgb.jpg "graphicsmm_HorizontalLGB")</span><span class="sxs-lookup"><span data-stu-id="5e4c2-111">![A horizontal linear gradient](./media/graphicsmm-horizontallgb.jpg "graphicsmm_HorizontalLGB")</span></span>  
  
 <span data-ttu-id="5e4c2-112">Per creare una sfumatura lineare verticale, modificare il <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> e <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> del <xref:System.Windows.Media.LinearGradientBrush> in (0,5, 0) e (0,5, 1).</span><span class="sxs-lookup"><span data-stu-id="5e4c2-112">To create a vertical linear gradient, change the <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> and <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> of the <xref:System.Windows.Media.LinearGradientBrush> to (0.5,0) and (0.5,1).</span></span> <span data-ttu-id="5e4c2-113">Nell'esempio seguente, un <xref:System.Windows.Shapes.Rectangle> viene disegnato con una sfumatura lineare verticale.</span><span class="sxs-lookup"><span data-stu-id="5e4c2-113">In the following example, a <xref:System.Windows.Shapes.Rectangle> is painted with a vertical linear gradient.</span></span>  
  
 [!code-xaml[GradientBrushExamples_snip#VerticalGradient1XAML](~/samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#verticalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#VerticalGradient1CSharp](~/samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#verticalgradient1csharp)]  
  
 <span data-ttu-id="5e4c2-114">Nella figura seguente viene illustrata la sfumatura creata dall'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="5e4c2-114">The following illustration shows the gradient created by the previous example.</span></span>  
  
 <span data-ttu-id="5e4c2-115">![Sfumatura lineare verticale](./media/graphicsmm-verticallgb.jpg "graphicsmm_VerticalLGB")</span><span class="sxs-lookup"><span data-stu-id="5e4c2-115">![Vertical linear gradient](./media/graphicsmm-verticallgb.jpg "graphicsmm_VerticalLGB")</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5e4c2-116">Negli esempi di questo argomento viene utilizzato il sistema di coordinate predefinito per l'impostazione di punti di inizio e di fine.</span><span class="sxs-lookup"><span data-stu-id="5e4c2-116">The examples in this topic use the default coordinate system for setting start points and end points.</span></span> <span data-ttu-id="5e4c2-117">Il sistema di coordinate predefinito è relativo a un rettangolo di delimitazione: 0 indica lo 0% del rettangolo di delimitazione e 1 indica il 100% del rettangolo di delimitazione.</span><span class="sxs-lookup"><span data-stu-id="5e4c2-117">The default coordinate system is relative to a bounding box: 0 indicates 0 percent of the bounding box, and 1 indicates 100 percent of the bounding box.</span></span> <span data-ttu-id="5e4c2-118">È possibile modificare questo sistema di coordinate impostando la proprietà <xref:System.Windows.Media.GradientBrush.MappingMode%2A> sul valore <xref:System.Windows.Media.BrushMappingMode.Absolute?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="5e4c2-118">You can change this coordinate system by setting the <xref:System.Windows.Media.GradientBrush.MappingMode%2A> property to the value <xref:System.Windows.Media.BrushMappingMode.Absolute?displayProperty=nameWithType>.</span></span> <span data-ttu-id="5e4c2-119">Un sistema di coordinate assoluto non è relativo a un rettangolo di selezione.</span><span class="sxs-lookup"><span data-stu-id="5e4c2-119">An absolute coordinate system is not relative to a bounding box.</span></span> <span data-ttu-id="5e4c2-120">I valori vengono interpretati direttamente nello spazio locale.</span><span class="sxs-lookup"><span data-stu-id="5e4c2-120">Values are interpreted directly in local space.</span></span>  
  
 <span data-ttu-id="5e4c2-121">Per altri esempi, vedere [esempio di pennelli](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes).</span><span class="sxs-lookup"><span data-stu-id="5e4c2-121">For additional examples, see [Brushes Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes).</span></span> <span data-ttu-id="5e4c2-122">Per ulteriori informazioni sui gradienti e sugli altri tipi di pennelli, vedere [Cenni preliminari sul disegno con colori a tinta unita e sfumature](painting-with-solid-colors-and-gradients-overview.md).</span><span class="sxs-lookup"><span data-stu-id="5e4c2-122">For more information about gradients and other types of brushes, see [Painting with Solid Colors and Gradients Overview](painting-with-solid-colors-and-gradients-overview.md).</span></span>
