---
title: "Procedura: Disegnare un'area con una sfumatura lineare"
ms.date: 03/30/2017
helpviewer_keywords:
- linear gradients [WPF], painting with
- brushes [WPF], painting with linear gradients
- painting [WPF], with linear gradients
ms.assetid: 00e0cd04-48c0-4ec5-850e-d321beb37a34
ms.openlocfilehash: 92c9ccd846dbbce043d13e6ba82b9fa8e72fa8b5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69916168"
---
# <a name="how-to-paint-an-area-with-a-linear-gradient"></a><span data-ttu-id="d7b82-102">Procedura: Disegnare un'area con una sfumatura lineare</span><span class="sxs-lookup"><span data-stu-id="d7b82-102">How to: Paint an Area with a Linear Gradient</span></span>
<span data-ttu-id="d7b82-103">Questo esempio illustra come usare la <xref:System.Windows.Media.LinearGradientBrush> classe per disegnare un'area con una sfumatura lineare.</span><span class="sxs-lookup"><span data-stu-id="d7b82-103">This example shows how to use the <xref:System.Windows.Media.LinearGradientBrush> class to paint an area with a linear gradient.</span></span> <span data-ttu-id="d7b82-104">Nell'esempio seguente, l' <xref:System.Windows.Shapes.Shape.Fill%2A> oggetto di un oggetto <xref:System.Windows.Shapes.Rectangle> viene disegnato con una sfumatura lineare diagonale che passa da giallo a rosso a blu a verde limone.</span><span class="sxs-lookup"><span data-stu-id="d7b82-104">In the following example, the <xref:System.Windows.Shapes.Shape.Fill%2A> of a <xref:System.Windows.Shapes.Rectangle> is painted with a diagonal linear gradient that transitions from yellow to red to blue to lime green.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d7b82-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="d7b82-105">Example</span></span>  
 [!code-xaml[GradientBrushExamples_snip#DiagonalGradient1XAML](~/samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#diagonalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#DiagonalGradient1CSharp](~/samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#diagonalgradient1csharp)]  
  
 <span data-ttu-id="d7b82-106">Nella figura seguente viene illustrata la sfumatura creata dall'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="d7b82-106">The following illustration shows the gradient created by the previous example.</span></span>  
  
 <span data-ttu-id="d7b82-107">![Sfumatura lineare diagonale](./media/graphicsmm-diagonallgb.jpg "graphicsmm_DiagonalLGB")</span><span class="sxs-lookup"><span data-stu-id="d7b82-107">![Diagonal linear gradient](./media/graphicsmm-diagonallgb.jpg "graphicsmm_DiagonalLGB")</span></span>  
  
 <span data-ttu-id="d7b82-108">Per creare una sfumatura lineare orizzontale, modificare <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> e <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> di <xref:System.Windows.Media.LinearGradientBrush> in (0, 0,5) e (1, 0,5).</span><span class="sxs-lookup"><span data-stu-id="d7b82-108">To create a horizontal linear gradient, change the <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> and <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> of the <xref:System.Windows.Media.LinearGradientBrush> to (0,0.5) and (1,0.5).</span></span> <span data-ttu-id="d7b82-109">Nell'esempio seguente viene disegnato un <xref:System.Windows.Shapes.Rectangle> oggetto con una sfumatura lineare orizzontale.</span><span class="sxs-lookup"><span data-stu-id="d7b82-109">In the following example, a <xref:System.Windows.Shapes.Rectangle> is painted with a horizontal linear gradient.</span></span>  
  
 [!code-xaml[GradientBrushExamples_snip#HorizontalGradient1XAML](~/samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#horizontalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#HorizontalGradient1CSharp](~/samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#horizontalgradient1csharp)]  
  
 <span data-ttu-id="d7b82-110">Nella figura seguente viene illustrata la sfumatura creata dall'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="d7b82-110">The following illustration shows the gradient created by the previous example.</span></span>  
  
 <span data-ttu-id="d7b82-111">![Sfumatura lineare orizzontale](./media/graphicsmm-horizontallgb.jpg "graphicsmm_HorizontalLGB")</span><span class="sxs-lookup"><span data-stu-id="d7b82-111">![A horizontal linear gradient](./media/graphicsmm-horizontallgb.jpg "graphicsmm_HorizontalLGB")</span></span>  
  
 <span data-ttu-id="d7b82-112">Per creare una sfumatura lineare verticale, modificare <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> e <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> di <xref:System.Windows.Media.LinearGradientBrush> in (0,5, 0) e (0,5, 1).</span><span class="sxs-lookup"><span data-stu-id="d7b82-112">To create a vertical linear gradient, change the <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> and <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> of the <xref:System.Windows.Media.LinearGradientBrush> to (0.5,0) and (0.5,1).</span></span> <span data-ttu-id="d7b82-113">Nell'esempio seguente viene disegnato un <xref:System.Windows.Shapes.Rectangle> oggetto con una sfumatura lineare verticale.</span><span class="sxs-lookup"><span data-stu-id="d7b82-113">In the following example, a <xref:System.Windows.Shapes.Rectangle> is painted with a vertical linear gradient.</span></span>  
  
 [!code-xaml[GradientBrushExamples_snip#VerticalGradient1XAML](~/samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#verticalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#VerticalGradient1CSharp](~/samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#verticalgradient1csharp)]  
  
 <span data-ttu-id="d7b82-114">Nella figura seguente viene illustrata la sfumatura creata dall'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="d7b82-114">The following illustration shows the gradient created by the previous example.</span></span>  
  
 <span data-ttu-id="d7b82-115">![Sfumatura lineare verticale](./media/graphicsmm-verticallgb.jpg "graphicsmm_VerticalLGB")</span><span class="sxs-lookup"><span data-stu-id="d7b82-115">![Vertical linear gradient](./media/graphicsmm-verticallgb.jpg "graphicsmm_VerticalLGB")</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d7b82-116">Negli esempi di questo argomento viene utilizzato il sistema di coordinate predefinito per l'impostazione di punti di inizio e di fine.</span><span class="sxs-lookup"><span data-stu-id="d7b82-116">The examples in this topic use the default coordinate system for setting start points and end points.</span></span> <span data-ttu-id="d7b82-117">Il sistema di coordinate predefinito è relativo a un rettangolo di delimitazione: 0 indica lo 0% del riquadro e 1 indica il 100% del riquadro.</span><span class="sxs-lookup"><span data-stu-id="d7b82-117">The default coordinate system is relative to a bounding box: 0 indicates 0 percent of the bounding box, and 1 indicates 100 percent of the bounding box.</span></span> <span data-ttu-id="d7b82-118">È possibile modificare questo sistema di coordinate impostando <xref:System.Windows.Media.GradientBrush.MappingMode%2A> la proprietà sul valore <xref:System.Windows.Media.BrushMappingMode.Absolute?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d7b82-118">You can change this coordinate system by setting the <xref:System.Windows.Media.GradientBrush.MappingMode%2A> property to the value <xref:System.Windows.Media.BrushMappingMode.Absolute?displayProperty=nameWithType>.</span></span> <span data-ttu-id="d7b82-119">Un sistema di coordinate assoluto non è relativo a un rettangolo di selezione.</span><span class="sxs-lookup"><span data-stu-id="d7b82-119">An absolute coordinate system is not relative to a bounding box.</span></span> <span data-ttu-id="d7b82-120">I valori vengono interpretati direttamente nello spazio locale.</span><span class="sxs-lookup"><span data-stu-id="d7b82-120">Values are interpreted directly in local space.</span></span>  
  
 <span data-ttu-id="d7b82-121">Per altri esempi, vedere [esempio](https://go.microsoft.com/fwlink/?LinkID=159973)di pennelli.</span><span class="sxs-lookup"><span data-stu-id="d7b82-121">For additional examples, see [Brushes Sample](https://go.microsoft.com/fwlink/?LinkID=159973).</span></span> <span data-ttu-id="d7b82-122">Per ulteriori informazioni sui gradienti e sugli altri tipi di pennelli, vedere [Cenni preliminari sul disegno con colori a tinta unita e sfumature](painting-with-solid-colors-and-gradients-overview.md).</span><span class="sxs-lookup"><span data-stu-id="d7b82-122">For more information about gradients and other types of brushes, see [Painting with Solid Colors and Gradients Overview](painting-with-solid-colors-and-gradients-overview.md).</span></span>
