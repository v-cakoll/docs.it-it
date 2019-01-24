---
title: "Procedura: Disegnare un'area con un video"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- painting with a video [WPF]
- video [WPF], painting with
- brushes [WPF], painting with a video
ms.assetid: 04dd6600-4a6e-4b43-a93e-21cce7dfbcb8
ms.openlocfilehash: c5995359486bcc415b048256c772ec5012b066f0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54580200"
---
# <a name="how-to-paint-an-area-with-a-video"></a><span data-ttu-id="662f9-102">Procedura: Disegnare un'area con un video</span><span class="sxs-lookup"><span data-stu-id="662f9-102">How to: Paint an Area with a Video</span></span>
<span data-ttu-id="662f9-103">In questo esempio viene illustrato come disegnare un'area con supporto di memorizzazione.</span><span class="sxs-lookup"><span data-stu-id="662f9-103">This example shows how to paint an area with media.</span></span> <span data-ttu-id="662f9-104">Un modo per disegnare un'area con supporto consiste nell'utilizzare un <xref:System.Windows.Controls.MediaElement> insieme a un <xref:System.Windows.Media.VisualBrush>.</span><span class="sxs-lookup"><span data-stu-id="662f9-104">One way to paint an area with media is to use a <xref:System.Windows.Controls.MediaElement> together with a <xref:System.Windows.Media.VisualBrush>.</span></span> <span data-ttu-id="662f9-105">Usare la <xref:System.Windows.Controls.MediaElement> per caricare e riprodurre i contenuti multimediali e quindi utilizzarla per impostare il <xref:System.Windows.Media.VisualBrush.Visual%2A> proprietà del <xref:System.Windows.Media.VisualBrush>.</span><span class="sxs-lookup"><span data-stu-id="662f9-105">Use the <xref:System.Windows.Controls.MediaElement> to load and play the media, and then use it to set the <xref:System.Windows.Media.VisualBrush.Visual%2A> property of the <xref:System.Windows.Media.VisualBrush>.</span></span> <span data-ttu-id="662f9-106">È quindi possibile usare il <xref:System.Windows.Media.VisualBrush> per disegnare un'area con elementi multimediali caricati.</span><span class="sxs-lookup"><span data-stu-id="662f9-106">You can then use the <xref:System.Windows.Media.VisualBrush> to paint an area with the loaded media.</span></span>  
  
## <a name="example"></a><span data-ttu-id="662f9-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="662f9-107">Example</span></span>  
 <span data-ttu-id="662f9-108">L'esempio seguente usa un' <xref:System.Windows.Controls.MediaElement> e una <xref:System.Windows.Media.VisualBrush> per disegnare il <xref:System.Windows.Controls.TextBlock.Foreground%2A> di un <xref:System.Windows.Controls.TextBlock> controllo con i video.</span><span class="sxs-lookup"><span data-stu-id="662f9-108">The following example uses a <xref:System.Windows.Controls.MediaElement> and a <xref:System.Windows.Media.VisualBrush> to paint the <xref:System.Windows.Controls.TextBlock.Foreground%2A> of a <xref:System.Windows.Controls.TextBlock> control with video.</span></span> <span data-ttu-id="662f9-109">Questo esempio viene impostato il <xref:System.Windows.Controls.MediaElement.IsMuted%2A> proprietà del <xref:System.Windows.Controls.MediaElement> a `true` in modo che non riprodurre suoni.</span><span class="sxs-lookup"><span data-stu-id="662f9-109">This example sets the <xref:System.Windows.Controls.MediaElement.IsMuted%2A> property of the <xref:System.Windows.Controls.MediaElement> to `true` so that it produces no sound.</span></span>  
  
 [!code-csharp[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/visualbrush_markup_snip/CSharp/PaintWithVideoExample.cs#graphicsmmvideoastextbackgroundinline)]
 [!code-vb[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/visualbrush_markup_snip/visualbasic/paintwithvideoexample.vb#graphicsmmvideoastextbackgroundinline)]
 [!code-xaml[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/visualbrush_markup_snip/XAML/PaintWithVideoExample.xaml#graphicsmmvideoastextbackgroundinline)]  
  
## <a name="example"></a><span data-ttu-id="662f9-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="662f9-110">Example</span></span>  
 <span data-ttu-id="662f9-111">In quanto <xref:System.Windows.Media.VisualBrush> eredita il <xref:System.Windows.Media.TileBrush> (classe), offre diverse modalità di affiancamento.</span><span class="sxs-lookup"><span data-stu-id="662f9-111">Because <xref:System.Windows.Media.VisualBrush> inherits from the <xref:System.Windows.Media.TileBrush> class, it provides several tiling modes.</span></span> <span data-ttu-id="662f9-112">Impostando il <xref:System.Windows.Media.TileBrush.TileMode%2A> proprietà di un <xref:System.Windows.Media.VisualBrush> a <xref:System.Windows.Media.TileMode.Tile> e impostando il <xref:System.Windows.Media.TileBrush.Viewport%2A> proprietà su un valore più piccola dell'area da disegnare, è possibile creare un modello affiancato.</span><span class="sxs-lookup"><span data-stu-id="662f9-112">By setting the <xref:System.Windows.Media.TileBrush.TileMode%2A> property of a <xref:System.Windows.Media.VisualBrush> to <xref:System.Windows.Media.TileMode.Tile> and by setting its <xref:System.Windows.Media.TileBrush.Viewport%2A> property to a value smaller than the area that you are painting, you can create a tiled pattern.</span></span>  
  
 <span data-ttu-id="662f9-113">Nell'esempio seguente è identico all'esempio precedente, tranne il fatto che il <xref:System.Windows.Media.VisualBrush> genera un modello dal video.</span><span class="sxs-lookup"><span data-stu-id="662f9-113">The following example is identical to the previous example, except that the <xref:System.Windows.Media.VisualBrush> generates a pattern from the video.</span></span>  
  
 [!code-csharp[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundTiledInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/visualbrush_markup_snip/CSharp/PaintWithVideoExample.cs#graphicsmmvideoastextbackgroundtiledinline)]
 [!code-vb[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundTiledInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/visualbrush_markup_snip/visualbasic/paintwithvideoexample.vb#graphicsmmvideoastextbackgroundtiledinline)]
 [!code-xaml[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundTiledInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/visualbrush_markup_snip/XAML/PaintWithVideoExample.xaml#graphicsmmvideoastextbackgroundtiledinline)]  
  
 <span data-ttu-id="662f9-114">Per informazioni su come aggiungere un file di contenuto, ad esempio un file multimediale, per l'applicazione, vedere [WPF Application Resource, contenuto e i file di dati](../../../../docs/framework/wpf/app-development/wpf-application-resource-content-and-data-files.md).</span><span class="sxs-lookup"><span data-stu-id="662f9-114">For information about how to add a content file, such as a media file, to your application, see [WPF Application Resource, Content, and Data Files](../../../../docs/framework/wpf/app-development/wpf-application-resource-content-and-data-files.md).</span></span> <span data-ttu-id="662f9-115">Quando si aggiunge un file multimediale, è necessario aggiungerlo come un file di contenuto, non come un file di risorse.</span><span class="sxs-lookup"><span data-stu-id="662f9-115">When you add a media file, you must add it as a content file, not as a resource file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="662f9-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="662f9-116">See also</span></span>
- <xref:System.Windows.Media.VisualBrush>
- [<span data-ttu-id="662f9-117">Disegnare con oggetti Image, Drawing e Visual</span><span class="sxs-lookup"><span data-stu-id="662f9-117">Painting with Images, Drawings, and Visuals</span></span>](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)
- [<span data-ttu-id="662f9-118">Panoramica sugli oggetti TileBrush</span><span class="sxs-lookup"><span data-stu-id="662f9-118">TileBrush Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/tilebrush-overview.md)
- [<span data-ttu-id="662f9-119">Panoramica delle funzionalità multimediali</span><span class="sxs-lookup"><span data-stu-id="662f9-119">Multimedia Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/multimedia-overview.md)
