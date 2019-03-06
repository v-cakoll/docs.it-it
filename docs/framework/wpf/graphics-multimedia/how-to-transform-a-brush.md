---
title: 'Procedura: Trasformare un oggetto Brush'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- brushes [WPF], rotating contents
- brushes [WPF], Transform property
- rotating contents of brushes [WPF]
ms.assetid: ebada2f9-f01f-4863-9ea2-c2e4e51610f1
ms.openlocfilehash: 990c82b4844ce3ca7f5b553b180280b6b37496ca
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57373764"
---
# <a name="how-to-transform-a-brush"></a><span data-ttu-id="5c81d-102">Procedura: Trasformare un oggetto Brush</span><span class="sxs-lookup"><span data-stu-id="5c81d-102">How to: Transform a Brush</span></span>
<span data-ttu-id="5c81d-103">In questo esempio viene illustrato come trasformare <xref:System.Windows.Media.Brush> gli oggetti utilizzando le due proprietà di trasformazione: <xref:System.Windows.Media.Brush.RelativeTransform%2A> e <xref:System.Windows.Media.Brush.Transform%2A>.</span><span class="sxs-lookup"><span data-stu-id="5c81d-103">This example shows how to transform <xref:System.Windows.Media.Brush> objects by using their two transformation properties: <xref:System.Windows.Media.Brush.RelativeTransform%2A> and <xref:System.Windows.Media.Brush.Transform%2A>.</span></span>  
  
 <span data-ttu-id="5c81d-104">Gli esempi seguenti usano un <xref:System.Windows.Media.RotateTransform> ruotare il contenuto di un <xref:System.Windows.Media.ImageBrush> di 45 gradi.</span><span class="sxs-lookup"><span data-stu-id="5c81d-104">The following examples use a <xref:System.Windows.Media.RotateTransform> to rotate the content of an <xref:System.Windows.Media.ImageBrush> by 45 degrees.</span></span>  
  
 <span data-ttu-id="5c81d-105">La figura seguente mostra il <xref:System.Windows.Media.ImageBrush> senza un <xref:System.Windows.Media.RotateTransform>, con la <xref:System.Windows.Media.RotateTransform> applicato al <xref:System.Windows.Media.Brush.RelativeTransform%2A> proprietà e con il <xref:System.Windows.Media.RotateTransform> applicate al <xref:System.Windows.Media.Brush.Transform%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="5c81d-105">The following illustration shows the <xref:System.Windows.Media.ImageBrush> without a <xref:System.Windows.Media.RotateTransform>, with the <xref:System.Windows.Media.RotateTransform> applied to the <xref:System.Windows.Media.Brush.RelativeTransform%2A> property, and with the <xref:System.Windows.Media.RotateTransform> applied to the <xref:System.Windows.Media.Brush.Transform%2A> property.</span></span>  
  
 <span data-ttu-id="5c81d-106">![Impostazioni RelativeTransform e Transform di Brush](./media/wcpsdk-graphicsmm-transformandrelativetransform.png "wcpsdk_graphicsmm_transformandrelativetransform")</span><span class="sxs-lookup"><span data-stu-id="5c81d-106">![Brush RelativeTransform and Transform settings](./media/wcpsdk-graphicsmm-transformandrelativetransform.png "wcpsdk_graphicsmm_transformandrelativetransform")</span></span>  
  
## <a name="example"></a><span data-ttu-id="5c81d-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="5c81d-107">Example</span></span>  
 <span data-ttu-id="5c81d-108">Il primo esempio applica un' <xref:System.Windows.Media.RotateTransform> per il <xref:System.Windows.Media.Brush.RelativeTransform%2A> proprietà di un <xref:System.Windows.Media.ImageBrush>.</span><span class="sxs-lookup"><span data-stu-id="5c81d-108">The first example applies a <xref:System.Windows.Media.RotateTransform> to the <xref:System.Windows.Media.Brush.RelativeTransform%2A> property of an <xref:System.Windows.Media.ImageBrush>.</span></span> <span data-ttu-id="5c81d-109">Il <xref:System.Windows.Media.RotateTransform.CenterX%2A> e <xref:System.Windows.Media.RotateTransform.CenterY%2A> delle proprietà di un <xref:System.Windows.Media.RotateTransform> sono entrambe impostate su 0,5, ovvero la coordinata relativa del punto centrale del contenuto dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="5c81d-109">The <xref:System.Windows.Media.RotateTransform.CenterX%2A> and <xref:System.Windows.Media.RotateTransform.CenterY%2A> properties of a <xref:System.Windows.Media.RotateTransform> object are both set to 0.5, which is the relative coordinate of the center point of this content.</span></span> <span data-ttu-id="5c81d-110">Di conseguenza, il <xref:System.Windows.Media.ImageBrush> contenuto ruota intorno al relativo centro.</span><span class="sxs-lookup"><span data-stu-id="5c81d-110">As a result, the <xref:System.Windows.Media.ImageBrush> content rotates about its center.</span></span>  
  
 [!code-csharp[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTransformExample.cs#imagebrushrelativetransformexample)]
 [!code-vb[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtransformexample.vb#imagebrushrelativetransformexample)]
 [!code-xaml[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTransformExample.xaml#imagebrushrelativetransformexample)]  
  
 <span data-ttu-id="5c81d-111">Si applica anche nel secondo esempio una <xref:System.Windows.Media.RotateTransform> a un <xref:System.Windows.Media.ImageBrush>; tuttavia, questo esempio viene usato il <xref:System.Windows.Media.Brush.Transform%2A> proprietà invece del <xref:System.Windows.Media.Brush.RelativeTransform%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="5c81d-111">The second example also applies a <xref:System.Windows.Media.RotateTransform> to an <xref:System.Windows.Media.ImageBrush>; however, this example uses the <xref:System.Windows.Media.Brush.Transform%2A> property instead of the <xref:System.Windows.Media.Brush.RelativeTransform%2A> property.</span></span>  
  
 <span data-ttu-id="5c81d-112">Per ruotare il pennello intorno al relativo centro, l'esempio imposta il <xref:System.Windows.Media.RotateTransform.CenterX%2A> e <xref:System.Windows.Media.RotateTransform.CenterY%2A> delle proprietà del <xref:System.Windows.Media.RotateTransform> oggetto su coordinate assolute.</span><span class="sxs-lookup"><span data-stu-id="5c81d-112">To rotate the brush about its center, the example sets the <xref:System.Windows.Media.RotateTransform.CenterX%2A> and <xref:System.Windows.Media.RotateTransform.CenterY%2A> properties of the <xref:System.Windows.Media.RotateTransform> object to absolute coordinates.</span></span> <span data-ttu-id="5c81d-113">Poiché il pennello disegna un rettangolo di 175 x 90 pixel, il punto centrale del rettangolo è (87,5, 45).</span><span class="sxs-lookup"><span data-stu-id="5c81d-113">Because the brush paints a rectangle that is 175 by 90 pixels, the center point of the rectangle is (87.5, 45).</span></span>  
  
 [!code-csharp[BrushesIntroduction_snip#ImageBrushTransformExample](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTransformExample.cs#imagebrushtransformexample)]
 [!code-vb[BrushesIntroduction_snip#ImageBrushTransformExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtransformexample.vb#imagebrushtransformexample)]
 [!code-xaml[BrushesIntroduction_snip#ImageBrushTransformExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTransformExample.xaml#imagebrushtransformexample)]  
  
 <span data-ttu-id="5c81d-114">Per una descrizione del modo in cui il <xref:System.Windows.Media.Brush.RelativeTransform%2A> e <xref:System.Windows.Media.Brush.Transform%2A> delle proprietà, vedere la [Cenni preliminari sulle trasformazione Brush](brush-transformation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="5c81d-114">For a description of how the <xref:System.Windows.Media.Brush.RelativeTransform%2A> and <xref:System.Windows.Media.Brush.Transform%2A> properties work, see the [Brush Transformation Overview](brush-transformation-overview.md).</span></span>  
  
 <span data-ttu-id="5c81d-115">Per l'esempio completo, vedere [Brushes Sample (Esempio di pennelli)](https://go.microsoft.com/fwlink/?LinkID=159973).</span><span class="sxs-lookup"><span data-stu-id="5c81d-115">For the complete sample, see [Brushes Sample](https://go.microsoft.com/fwlink/?LinkID=159973).</span></span> <span data-ttu-id="5c81d-116">Per altre informazioni sui pennelli, vedere [Cenni sul disegno con colori a tinta unita e sfumature](painting-with-solid-colors-and-gradients-overview.md).</span><span class="sxs-lookup"><span data-stu-id="5c81d-116">For more information about brushes, see [Painting with Solid Colors and Gradients Overview](painting-with-solid-colors-and-gradients-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c81d-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5c81d-117">See also</span></span>
- [<span data-ttu-id="5c81d-118">Panoramica sulle proprietà di trasformazione Brush</span><span class="sxs-lookup"><span data-stu-id="5c81d-118">Brush Transformation Overview</span></span>](brush-transformation-overview.md)
- [<span data-ttu-id="5c81d-119">Cenni sul disegno con colori a tinta unita e sfumature</span><span class="sxs-lookup"><span data-stu-id="5c81d-119">Painting with Solid Colors and Gradients Overview</span></span>](painting-with-solid-colors-and-gradients-overview.md)
- [<span data-ttu-id="5c81d-120">Cenni preliminari sulle trasformazioni</span><span class="sxs-lookup"><span data-stu-id="5c81d-120">Transforms Overview</span></span>](transforms-overview.md)
