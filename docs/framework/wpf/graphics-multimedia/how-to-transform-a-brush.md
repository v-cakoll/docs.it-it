---
title: 'Procedura: trasformare un oggetto Brush'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- brushes [WPF], rotating contents
- brushes [WPF], Transform property
- rotating contents of brushes [WPF]
ms.assetid: ebada2f9-f01f-4863-9ea2-c2e4e51610f1
ms.openlocfilehash: b4484e2fc1ae3e969b02b1d8f3ae4ab2a035558e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187329"
---
# <a name="how-to-transform-a-brush"></a><span data-ttu-id="58529-102">Procedura: trasformare un oggetto Brush</span><span class="sxs-lookup"><span data-stu-id="58529-102">How to: Transform a Brush</span></span>
<span data-ttu-id="58529-103">In questo esempio <xref:System.Windows.Media.Brush> viene illustrato come trasformare <xref:System.Windows.Media.Brush.RelativeTransform%2A> gli <xref:System.Windows.Media.Brush.Transform%2A>oggetti utilizzando le relative due proprietà di trasformazione: e .</span><span class="sxs-lookup"><span data-stu-id="58529-103">This example shows how to transform <xref:System.Windows.Media.Brush> objects by using their two transformation properties: <xref:System.Windows.Media.Brush.RelativeTransform%2A> and <xref:System.Windows.Media.Brush.Transform%2A>.</span></span>  
  
 <span data-ttu-id="58529-104">Negli esempi seguenti <xref:System.Windows.Media.RotateTransform> viene utilizzato un <xref:System.Windows.Media.ImageBrush> per ruotare il contenuto di un oggetto di 45 gradi.</span><span class="sxs-lookup"><span data-stu-id="58529-104">The following examples use a <xref:System.Windows.Media.RotateTransform> to rotate the content of an <xref:System.Windows.Media.ImageBrush> by 45 degrees.</span></span>  
  
 <span data-ttu-id="58529-105">Nella figura seguente <xref:System.Windows.Media.ImageBrush> viene <xref:System.Windows.Media.RotateTransform>illustrato <xref:System.Windows.Media.RotateTransform> l'oggetto <xref:System.Windows.Media.Brush.RelativeTransform%2A> without a <xref:System.Windows.Media.RotateTransform> , con <xref:System.Windows.Media.Brush.Transform%2A> l'oggetto applicato alla proprietà e con l'oggetto applicato alla proprietà .</span><span class="sxs-lookup"><span data-stu-id="58529-105">The following illustration shows the <xref:System.Windows.Media.ImageBrush> without a <xref:System.Windows.Media.RotateTransform>, with the <xref:System.Windows.Media.RotateTransform> applied to the <xref:System.Windows.Media.Brush.RelativeTransform%2A> property, and with the <xref:System.Windows.Media.RotateTransform> applied to the <xref:System.Windows.Media.Brush.Transform%2A> property.</span></span>  
  
 <span data-ttu-id="58529-106">![Impostazioni RelativeTransform e Transform di Brush](./media/wcpsdk-graphicsmm-transformandrelativetransform.png "wcpsdk_graphicsmm_transformandrelativetransform")</span><span class="sxs-lookup"><span data-stu-id="58529-106">![Brush RelativeTransform and Transform settings](./media/wcpsdk-graphicsmm-transformandrelativetransform.png "wcpsdk_graphicsmm_transformandrelativetransform")</span></span>  
  
## <a name="example"></a><span data-ttu-id="58529-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="58529-107">Example</span></span>  
 <span data-ttu-id="58529-108">Nel primo esempio <xref:System.Windows.Media.RotateTransform> viene <xref:System.Windows.Media.Brush.RelativeTransform%2A> applicato <xref:System.Windows.Media.ImageBrush>un alla proprietà di un oggetto .</span><span class="sxs-lookup"><span data-stu-id="58529-108">The first example applies a <xref:System.Windows.Media.RotateTransform> to the <xref:System.Windows.Media.Brush.RelativeTransform%2A> property of an <xref:System.Windows.Media.ImageBrush>.</span></span> <span data-ttu-id="58529-109">Le <xref:System.Windows.Media.RotateTransform.CenterX%2A> <xref:System.Windows.Media.RotateTransform.CenterY%2A> proprietà e <xref:System.Windows.Media.RotateTransform> di un oggetto sono entrambe impostate su 0,5, che è la coordinata relativa del punto centrale di questo contenuto.</span><span class="sxs-lookup"><span data-stu-id="58529-109">The <xref:System.Windows.Media.RotateTransform.CenterX%2A> and <xref:System.Windows.Media.RotateTransform.CenterY%2A> properties of a <xref:System.Windows.Media.RotateTransform> object are both set to 0.5, which is the relative coordinate of the center point of this content.</span></span> <span data-ttu-id="58529-110">Di conseguenza, <xref:System.Windows.Media.ImageBrush> il contenuto ruota intorno al suo centro.</span><span class="sxs-lookup"><span data-stu-id="58529-110">As a result, the <xref:System.Windows.Media.ImageBrush> content rotates about its center.</span></span>  
  
 [!code-csharp[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTransformExample.cs#imagebrushrelativetransformexample)]
 [!code-vb[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtransformexample.vb#imagebrushrelativetransformexample)]
 [!code-xaml[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTransformExample.xaml#imagebrushrelativetransformexample)]  
  
 <span data-ttu-id="58529-111">Il secondo esempio <xref:System.Windows.Media.RotateTransform> applica <xref:System.Windows.Media.ImageBrush>anche a a un oggetto ; tuttavia, in <xref:System.Windows.Media.Brush.Transform%2A> questo esempio <xref:System.Windows.Media.Brush.RelativeTransform%2A> viene utilizzata la proprietà anziché la proprietà .</span><span class="sxs-lookup"><span data-stu-id="58529-111">The second example also applies a <xref:System.Windows.Media.RotateTransform> to an <xref:System.Windows.Media.ImageBrush>; however, this example uses the <xref:System.Windows.Media.Brush.Transform%2A> property instead of the <xref:System.Windows.Media.Brush.RelativeTransform%2A> property.</span></span>  
  
 <span data-ttu-id="58529-112">Per ruotare il pennello intorno <xref:System.Windows.Media.RotateTransform.CenterX%2A> al <xref:System.Windows.Media.RotateTransform.CenterY%2A> centro, <xref:System.Windows.Media.RotateTransform> l'esempio imposta le proprietà e dell'oggetto su coordinate assolute.</span><span class="sxs-lookup"><span data-stu-id="58529-112">To rotate the brush about its center, the example sets the <xref:System.Windows.Media.RotateTransform.CenterX%2A> and <xref:System.Windows.Media.RotateTransform.CenterY%2A> properties of the <xref:System.Windows.Media.RotateTransform> object to absolute coordinates.</span></span> <span data-ttu-id="58529-113">Poiché il pennello disegna un rettangolo di 175 x 90 pixel, il punto centrale del rettangolo è (87,5, 45).</span><span class="sxs-lookup"><span data-stu-id="58529-113">Because the brush paints a rectangle that is 175 by 90 pixels, the center point of the rectangle is (87.5, 45).</span></span>  
  
 [!code-csharp[BrushesIntroduction_snip#ImageBrushTransformExample](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTransformExample.cs#imagebrushtransformexample)]
 [!code-vb[BrushesIntroduction_snip#ImageBrushTransformExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtransformexample.vb#imagebrushtransformexample)]
 [!code-xaml[BrushesIntroduction_snip#ImageBrushTransformExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTransformExample.xaml#imagebrushtransformexample)]  
  
 <span data-ttu-id="58529-114">Per una descrizione <xref:System.Windows.Media.Brush.RelativeTransform%2A> del <xref:System.Windows.Media.Brush.Transform%2A> funzionamento delle proprietà e , vedere Cenni preliminari [sulla trasformazione del pennello](brush-transformation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="58529-114">For a description of how the <xref:System.Windows.Media.Brush.RelativeTransform%2A> and <xref:System.Windows.Media.Brush.Transform%2A> properties work, see the [Brush Transformation Overview](brush-transformation-overview.md).</span></span>  
  
 <span data-ttu-id="58529-115">Per l'esempio completo, vedere [Brushes Sample (Esempio di pennelli)](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes).</span><span class="sxs-lookup"><span data-stu-id="58529-115">For the complete sample, see [Brushes Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes).</span></span> <span data-ttu-id="58529-116">Per altre informazioni sui pennelli, vedere [Cenni sul disegno con colori a tinta unita e sfumature](painting-with-solid-colors-and-gradients-overview.md).</span><span class="sxs-lookup"><span data-stu-id="58529-116">For more information about brushes, see [Painting with Solid Colors and Gradients Overview](painting-with-solid-colors-and-gradients-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58529-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="58529-117">See also</span></span>

- [<span data-ttu-id="58529-118">Panoramica sulle proprietà di trasformazione Brush</span><span class="sxs-lookup"><span data-stu-id="58529-118">Brush Transformation Overview</span></span>](brush-transformation-overview.md)
- [<span data-ttu-id="58529-119">Cenni sul disegno con colori a tinta unita e sfumature</span><span class="sxs-lookup"><span data-stu-id="58529-119">Painting with Solid Colors and Gradients Overview</span></span>](painting-with-solid-colors-and-gradients-overview.md)
- [<span data-ttu-id="58529-120">Cenni preliminari sulle trasformazioni</span><span class="sxs-lookup"><span data-stu-id="58529-120">Transforms Overview</span></span>](transforms-overview.md)
