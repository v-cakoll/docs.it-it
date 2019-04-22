---
title: 'Procedura: Impostare la dimensione degli elementi affiancati di un TileBrush'
ms.date: 03/30/2017
helpviewer_keywords:
- TileBrush [WPF], size of tile properties
- Viewport property of TileBrush [WPF]
ms.assetid: 04f41090-1b46-4e36-832f-d27d28708b8c
ms.openlocfilehash: 80b5dfc668464df829db593668bea8a9a4ec09e4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58839696"
---
# <a name="how-to-set-the-tile-size-for-a-tilebrush"></a><span data-ttu-id="995ea-102">Procedura: Impostare la dimensione degli elementi affiancati di un TileBrush</span><span class="sxs-lookup"><span data-stu-id="995ea-102">How to: Set the Tile Size for a TileBrush</span></span>

<span data-ttu-id="995ea-103">In questo esempio viene illustrato come impostare la dimensione delle tessere per un <xref:System.Windows.Media.TileBrush>.</span><span class="sxs-lookup"><span data-stu-id="995ea-103">This example shows how to set the tile size for a <xref:System.Windows.Media.TileBrush>.</span></span> <span data-ttu-id="995ea-104">Per impostazione predefinita, un <xref:System.Windows.Media.TileBrush> produce una sola tessera che riempie completamente l'area da disegnare.</span><span class="sxs-lookup"><span data-stu-id="995ea-104">By default, a <xref:System.Windows.Media.TileBrush> produces a single tile that completely fills the area that you are painting.</span></span> <span data-ttu-id="995ea-105">È possibile eseguire l'override di questo comportamento impostando il <xref:System.Windows.Media.TileBrush.Viewport%2A> e <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="995ea-105">You can override this behavior by setting the <xref:System.Windows.Media.TileBrush.Viewport%2A> and <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> properties.</span></span>

<span data-ttu-id="995ea-106">Il <xref:System.Windows.Media.TileBrush.Viewport%2A> proprietà specifica la dimensione delle tessere per un <xref:System.Windows.Media.TileBrush>.</span><span class="sxs-lookup"><span data-stu-id="995ea-106">The <xref:System.Windows.Media.TileBrush.Viewport%2A> property specifies the tile size for a <xref:System.Windows.Media.TileBrush>.</span></span> <span data-ttu-id="995ea-107">Per impostazione predefinita, il valore della <xref:System.Windows.Media.TileBrush.Viewport%2A> proprietà è relativo alle dimensioni dell'area da disegnare.</span><span class="sxs-lookup"><span data-stu-id="995ea-107">By default, the value of the <xref:System.Windows.Media.TileBrush.Viewport%2A> property is relative to the size of the area being painted.</span></span> <span data-ttu-id="995ea-108">Per rendere il <xref:System.Windows.Media.TileBrush.Viewport%2A> proprietà specificare una dimensione assoluta della tessera, impostare il <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> proprietà <xref:System.Windows.Media.BrushMappingMode.Absolute>.</span><span class="sxs-lookup"><span data-stu-id="995ea-108">To make the <xref:System.Windows.Media.TileBrush.Viewport%2A> property specify an absolute tile size, set the <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> property to <xref:System.Windows.Media.BrushMappingMode.Absolute>.</span></span>

## <a name="example"></a><span data-ttu-id="995ea-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="995ea-109">Example</span></span>

<span data-ttu-id="995ea-110">L'esempio seguente usa un' <xref:System.Windows.Media.ImageBrush>, un tipo di <xref:System.Windows.Media.TileBrush>per disegnare un rettangolo con tessere.</span><span class="sxs-lookup"><span data-stu-id="995ea-110">The following example uses an <xref:System.Windows.Media.ImageBrush>, a type of <xref:System.Windows.Media.TileBrush>, to paint a rectangle with tiles.</span></span> <span data-ttu-id="995ea-111">L'esempio imposta ogni tessera portandolo al 50% x 50% dell'area di output (rettangolo).</span><span class="sxs-lookup"><span data-stu-id="995ea-111">The example sets each tile to 50 percent by 50 percent of the output area (the rectangle).</span></span> <span data-ttu-id="995ea-112">Di conseguenza, il rettangolo viene disegnato con quattro proiezioni dell'immagine.</span><span class="sxs-lookup"><span data-stu-id="995ea-112">As a result, the rectangle is painted with four projections of the image.</span></span>

<span data-ttu-id="995ea-113">Nella figura seguente mostra l'output di esempio generato:</span><span class="sxs-lookup"><span data-stu-id="995ea-113">The following illustration shows the output that the example produces:</span></span>

![Un rettangolo con quattro gratta dimostrazione affiancamento con un pennello immagine.](./media/how-to-set-the-tile-size-for-a-tilebrush/rectangle-tile-image-brush.png)

[!code-csharp[UsingImageBrush_snip#RelativeTileSizeExample](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/TileSizeExample.cs#relativetilesizeexample)]

<span data-ttu-id="995ea-115">L'esempio successivo crea un <xref:System.Windows.Media.ImageBrush>, imposta relativo <xref:System.Windows.Media.TileBrush.Viewport%2A> a `0,0,25,25` e la relativa <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> a <xref:System.Windows.Media.BrushMappingMode.Absolute>e lo usa per disegnare un altro rettangolo.</span><span class="sxs-lookup"><span data-stu-id="995ea-115">The next example creates an <xref:System.Windows.Media.ImageBrush>, sets its <xref:System.Windows.Media.TileBrush.Viewport%2A> to `0,0,25,25` and its <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> to <xref:System.Windows.Media.BrushMappingMode.Absolute>, and uses it to paint another rectangle.</span></span> <span data-ttu-id="995ea-116">Di conseguenza, il pennello genera tessere con una larghezza pari a 25 pixel e un'altezza pari a 25 pixel.</span><span class="sxs-lookup"><span data-stu-id="995ea-116">As a result, the brush produces tiles that have a width of 25  pixels and a height of 25 pixels .</span></span>

<span data-ttu-id="995ea-117">Nella figura seguente mostra l'output di esempio generato:</span><span class="sxs-lookup"><span data-stu-id="995ea-117">The following illustration shows the output that the example produces:</span></span>

![Un rettangolo con cerchiato-gratta dimostrazione di un oggetto TileBrush affiancato con un Viewport.](./media/how-to-set-the-tile-size-for-a-tilebrush/25-x-25-viewport-tilebrush.png)

[!code-csharp[UsingImageBrush_snip#AbsoluteTileSizeExample](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/TileSizeExample.cs#absolutetilesizeexample)]

<span data-ttu-id="995ea-119">Gli esempi precedenti fanno parte di un esempio più esaustivo.</span><span class="sxs-lookup"><span data-stu-id="995ea-119">The preceding examples are part of a larger sample.</span></span> <span data-ttu-id="995ea-120">Per l'esempio completo, vedere [esempio ImageBrush](https://go.microsoft.com/fwlink/?LinkID=160005).</span><span class="sxs-lookup"><span data-stu-id="995ea-120">For the complete sample, see [ImageBrush Sample](https://go.microsoft.com/fwlink/?LinkID=160005).</span></span>

<span data-ttu-id="995ea-121">Sebbene questo esempio Usa la <xref:System.Windows.Media.ImageBrush> (classe), il <xref:System.Windows.Media.TileBrush.Viewport%2A> e <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> le proprietà si comportano in modo identico per gli altri <xref:System.Windows.Media.TileBrush> oggetti, vale a dire, per <xref:System.Windows.Media.DrawingBrush> e <xref:System.Windows.Media.VisualBrush>.</span><span class="sxs-lookup"><span data-stu-id="995ea-121">Although this example uses the <xref:System.Windows.Media.ImageBrush> class, the <xref:System.Windows.Media.TileBrush.Viewport%2A> and <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> properties behave identically for the other <xref:System.Windows.Media.TileBrush> objects, that is, for <xref:System.Windows.Media.DrawingBrush> and <xref:System.Windows.Media.VisualBrush>.</span></span> <span data-ttu-id="995ea-122">Per altre informazioni sulle <xref:System.Windows.Media.ImageBrush> e l'altra <xref:System.Windows.Media.TileBrush> oggetti, vedere [disegnare con immagini, disegni e oggetti visivi](painting-with-images-drawings-and-visuals.md).</span><span class="sxs-lookup"><span data-stu-id="995ea-122">For more information about <xref:System.Windows.Media.ImageBrush> and the other <xref:System.Windows.Media.TileBrush> objects, see [Painting with Images, Drawings, and Visuals](painting-with-images-drawings-and-visuals.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="995ea-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="995ea-123">See also</span></span>

- <xref:System.Windows.Media.TileBrush>
- [<span data-ttu-id="995ea-124">Disegnare con oggetti Image, Drawing e Visual</span><span class="sxs-lookup"><span data-stu-id="995ea-124">Painting with Images, Drawings, and Visuals</span></span>](painting-with-images-drawings-and-visuals.md)
- [<span data-ttu-id="995ea-125">Creare modelli di elementi affiancati differenti con un TileBrush</span><span class="sxs-lookup"><span data-stu-id="995ea-125">Create Different Tile Patterns with a TileBrush</span></span>](how-to-create-different-tile-patterns-with-a-tilebrush.md)
