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
ms.openlocfilehash: 92969778c04c6ac634a2964c402d6c3439b96b49
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186061"
---
# <a name="how-to-paint-an-area-with-an-image"></a><span data-ttu-id="c957d-102">Procedura: disegnare un'area con un'immagine</span><span class="sxs-lookup"><span data-stu-id="c957d-102">How to: Paint an Area with an Image</span></span>
<span data-ttu-id="c957d-103">In questo esempio viene <xref:System.Windows.Media.ImageBrush> illustrato come utilizzare la classe per disegnare un'area con un'immagine.</span><span class="sxs-lookup"><span data-stu-id="c957d-103">This example shows how to use the <xref:System.Windows.Media.ImageBrush> class to paint an area with an image.</span></span> <span data-ttu-id="c957d-104">Un <xref:System.Windows.Media.ImageBrush> visualizza una singola immagine, <xref:System.Windows.Media.ImageBrush.ImageSource%2A> specificata dalla relativa proprietà.</span><span class="sxs-lookup"><span data-stu-id="c957d-104">An <xref:System.Windows.Media.ImageBrush> displays a single image, which is specified by its <xref:System.Windows.Media.ImageBrush.ImageSource%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c957d-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="c957d-105">Example</span></span>  
 <span data-ttu-id="c957d-106">Nell'esempio seguente <xref:System.Windows.Controls.Control.Background%2A> viene disegnato l'oggetto di un pulsante utilizzando un oggetto . <xref:System.Windows.Media.ImageBrush></span><span class="sxs-lookup"><span data-stu-id="c957d-106">The following example paints the <xref:System.Windows.Controls.Control.Background%2A> of a button by using an <xref:System.Windows.Media.ImageBrush>.</span></span>  
  
 [!code-csharp[UsingImageBrush_snip#ImageBrushExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/PaintingWithImagesExample.cs#imagebrushexamplewholepage)]  
  
 <span data-ttu-id="c957d-107">Per impostazione <xref:System.Windows.Media.ImageBrush> predefinita, un'immagine allunga la propria immagine per riempire completamente l'area che si sta disegnando.</span><span class="sxs-lookup"><span data-stu-id="c957d-107">By default, an <xref:System.Windows.Media.ImageBrush> stretches its image to completely fill the area that you are painting.</span></span> <span data-ttu-id="c957d-108">Nell'esempio precedente, l'immagine viene adattata per riempire il pulsante, possibilmente distorcendo l'immagine.</span><span class="sxs-lookup"><span data-stu-id="c957d-108">In the preceding example, the image is stretched to fill the button, possibly distorting the image.</span></span> <span data-ttu-id="c957d-109">È possibile controllare questo <xref:System.Windows.Media.TileBrush.Stretch%2A> comportamento <xref:System.Windows.Media.TileBrush> impostando <xref:System.Windows.Media.Stretch.Uniform> <xref:System.Windows.Media.Stretch.UniformToFill>la proprietà su o , in modo che il pennello mantenga le proporzioni dell'immagine.</span><span class="sxs-lookup"><span data-stu-id="c957d-109">You can control this behavior by setting the <xref:System.Windows.Media.TileBrush.Stretch%2A> property of <xref:System.Windows.Media.TileBrush> to <xref:System.Windows.Media.Stretch.Uniform> or <xref:System.Windows.Media.Stretch.UniformToFill>, which causes the brush to preserve the aspect ratio of the image.</span></span>  
  
 <span data-ttu-id="c957d-110">Se si <xref:System.Windows.Media.TileBrush.Viewport%2A> impostano le proprietà e <xref:System.Windows.Media.TileBrush.TileMode%2A> di un oggetto , è possibile creare un motivo ripetuto. <xref:System.Windows.Media.ImageBrush></span><span class="sxs-lookup"><span data-stu-id="c957d-110">If you set the <xref:System.Windows.Media.TileBrush.Viewport%2A> and <xref:System.Windows.Media.TileBrush.TileMode%2A> properties of an <xref:System.Windows.Media.ImageBrush>, you can create a repeating pattern.</span></span> <span data-ttu-id="c957d-111">L'esempio seguente disegna un pulsante con un modello creato da un'immagine.</span><span class="sxs-lookup"><span data-stu-id="c957d-111">The following example paints a button by using a pattern that is created from an image.</span></span>  
  
 [!code-csharp[UsingImageBrush_snip#TiledImageBrushExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/TiledImageBrushExample.cs#tiledimagebrushexamplewholepage)]
 [!code-vb[UsingImageBrush_snip#TiledImageBrushExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/UsingImageBrush_snip/VisualBasic/TiledImageBrushExample.vb#tiledimagebrushexamplewholepage)]  
  
 <span data-ttu-id="c957d-112">Per ulteriori informazioni <xref:System.Windows.Media.ImageBrush> sulla classe , vedere [Disegno con immagini, disegni e oggetti visivi](painting-with-images-drawings-and-visuals.md).</span><span class="sxs-lookup"><span data-stu-id="c957d-112">For more information about the <xref:System.Windows.Media.ImageBrush> class, see [Painting with Images, Drawings, and Visuals](painting-with-images-drawings-and-visuals.md).</span></span>  
  
 <span data-ttu-id="c957d-113">Questo esempio di codice fa parte di <xref:System.Windows.Media.ImageBrush> un esempio più esaustivo fornito per la classe.</span><span class="sxs-lookup"><span data-stu-id="c957d-113">This code example is part of a larger example that is provided for the <xref:System.Windows.Media.ImageBrush> class.</span></span> <span data-ttu-id="c957d-114">Per l'esempio completo, vedere [Esempio ImageBrush](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ImageBrush).</span><span class="sxs-lookup"><span data-stu-id="c957d-114">For the complete sample, see [ImageBrush Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ImageBrush).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c957d-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c957d-115">See also</span></span>

- [<span data-ttu-id="c957d-116">Disegnare con oggetti Image, Drawing e Visual</span><span class="sxs-lookup"><span data-stu-id="c957d-116">Painting with Images, Drawings, and Visuals</span></span>](painting-with-images-drawings-and-visuals.md)
