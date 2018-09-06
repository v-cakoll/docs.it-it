---
title: "Procedura: disegnare un'area con un'immagine"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [WPF], painting with
- painting [WPF], with images
- brushes [WPF], painting with images
ms.assetid: 3432c533-1fc7-492d-94ee-0b13d60125ae
ms.openlocfilehash: 5899531291c22ada76213905d0f2ca6944fcbba7
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2018
ms.locfileid: "43857206"
---
# <a name="how-to-paint-an-area-with-an-image"></a><span data-ttu-id="52bca-102">Procedura: disegnare un'area con un'immagine</span><span class="sxs-lookup"><span data-stu-id="52bca-102">How to: Paint an Area with an Image</span></span>
<span data-ttu-id="52bca-103">In questo esempio viene illustrato come utilizzare il <xref:System.Windows.Media.ImageBrush> classe disegnare un'area con un'immagine.</span><span class="sxs-lookup"><span data-stu-id="52bca-103">This example shows how to use the <xref:System.Windows.Media.ImageBrush> class to paint an area with an image.</span></span> <span data-ttu-id="52bca-104">Un' <xref:System.Windows.Media.ImageBrush> Visualizza una singola immagine specificata dal relativo <xref:System.Windows.Media.ImageBrush.ImageSource%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="52bca-104">An <xref:System.Windows.Media.ImageBrush> displays a single image, which is specified by its <xref:System.Windows.Media.ImageBrush.ImageSource%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="52bca-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="52bca-105">Example</span></span>  
 <span data-ttu-id="52bca-106">Di seguito viene riportato di seguito viene disegnata la <xref:System.Windows.Controls.Control.Background%2A> di un pulsante usando un <xref:System.Windows.Media.ImageBrush>.</span><span class="sxs-lookup"><span data-stu-id="52bca-106">The following example paints the <xref:System.Windows.Controls.Control.Background%2A> of a button by using an <xref:System.Windows.Media.ImageBrush>.</span></span>  
  
 [!code-csharp[UsingImageBrush_snip#ImageBrushExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/PaintingWithImagesExample.cs#imagebrushexamplewholepage)]  
  
 <span data-ttu-id="52bca-107">Per impostazione predefinita, un <xref:System.Windows.Media.ImageBrush> estende la propria immagine per riempire completamente l'area da disegnare.</span><span class="sxs-lookup"><span data-stu-id="52bca-107">By default, an <xref:System.Windows.Media.ImageBrush> stretches its image to completely fill the area that you are painting.</span></span> <span data-ttu-id="52bca-108">Nell'esempio precedente, l'immagine viene adattata per riempire il pulsante, possibilmente distorcendo l'immagine.</span><span class="sxs-lookup"><span data-stu-id="52bca-108">In the preceding example, the image is stretched to fill the button, possibly distorting the image.</span></span> <span data-ttu-id="52bca-109">È possibile controllare questo comportamento impostando il <xref:System.Windows.Media.TileBrush.Stretch%2A> proprietà di <xref:System.Windows.Media.TileBrush> al <xref:System.Windows.Media.Stretch.Uniform> o <xref:System.Windows.Media.Stretch.UniformToFill>, in modo che il pennello conservi le proporzioni dell'immagine.</span><span class="sxs-lookup"><span data-stu-id="52bca-109">You can control this behavior by setting the <xref:System.Windows.Media.TileBrush.Stretch%2A> property of <xref:System.Windows.Media.TileBrush> to <xref:System.Windows.Media.Stretch.Uniform> or <xref:System.Windows.Media.Stretch.UniformToFill>, which causes the brush to preserve the aspect ratio of the image.</span></span>  
  
 <span data-ttu-id="52bca-110">Se si impostano i <xref:System.Windows.Media.TileBrush.Viewport%2A> e <xref:System.Windows.Media.TileBrush.TileMode%2A> proprietà di un <xref:System.Windows.Media.ImageBrush>, è possibile creare un criterio di ripetizione.</span><span class="sxs-lookup"><span data-stu-id="52bca-110">If you set the <xref:System.Windows.Media.TileBrush.Viewport%2A> and <xref:System.Windows.Media.TileBrush.TileMode%2A> properties of an <xref:System.Windows.Media.ImageBrush>, you can create a repeating pattern.</span></span> <span data-ttu-id="52bca-111">L'esempio seguente disegna un pulsante con un modello creato da un'immagine.</span><span class="sxs-lookup"><span data-stu-id="52bca-111">The following example paints a button by using a pattern that is created from an image.</span></span>  
  
 [!code-csharp[UsingImageBrush_snip#TiledImageBrushExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/TiledImageBrushExample.cs#tiledimagebrushexamplewholepage)]
 [!code-vb[UsingImageBrush_snip#TiledImageBrushExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UsingImageBrush_snip/VisualBasic/TiledImageBrushExample.vb#tiledimagebrushexamplewholepage)]  
  
 <span data-ttu-id="52bca-112">Per altre informazioni sul <xref:System.Windows.Media.ImageBrush> classe, vedere [disegnare con immagini, disegni e oggetti visivi](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md).</span><span class="sxs-lookup"><span data-stu-id="52bca-112">For more information about the <xref:System.Windows.Media.ImageBrush> class, see [Painting with Images, Drawings, and Visuals](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md).</span></span>  
  
 <span data-ttu-id="52bca-113">Questo esempio di codice fa parte di un esempio più esaustivo fornito per il <xref:System.Windows.Media.ImageBrush> classe.</span><span class="sxs-lookup"><span data-stu-id="52bca-113">This code example is part of a larger example that is provided for the <xref:System.Windows.Media.ImageBrush> class.</span></span> <span data-ttu-id="52bca-114">Per l'esempio completo, vedere [esempio ImageBrush](https://go.microsoft.com/fwlink/?LinkID=160005).</span><span class="sxs-lookup"><span data-stu-id="52bca-114">For the complete sample, see [ImageBrush Sample](https://go.microsoft.com/fwlink/?LinkID=160005).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52bca-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="52bca-115">See Also</span></span>  
 [<span data-ttu-id="52bca-116">Disegnare con oggetti Image, Drawing e Visual</span><span class="sxs-lookup"><span data-stu-id="52bca-116">Painting with Images, Drawings, and Visuals</span></span>](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)
