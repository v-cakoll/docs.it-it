---
title: 'Procedura: impostare la dimensione degli elementi affiancati di un TileBrush'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- TileBrush [WPF], size of tilepropertys
- Viewport property of TileBrush [WPF]
ms.assetid: 04f41090-1b46-4e36-832f-d27d28708b8c
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1e9b746fe66635054dbd35463f727d28a8abd3d0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-set-the-tile-size-for-a-tilebrush"></a><span data-ttu-id="84849-102">Procedura: impostare la dimensione degli elementi affiancati di un TileBrush</span><span class="sxs-lookup"><span data-stu-id="84849-102">How to: Set the Tile Size for a TileBrush</span></span>
<span data-ttu-id="84849-103">In questo esempio viene illustrato come impostare la dimensione dei riquadri per un <xref:System.Windows.Media.TileBrush>.</span><span class="sxs-lookup"><span data-stu-id="84849-103">This example shows how to set the tile size for a <xref:System.Windows.Media.TileBrush>.</span></span> <span data-ttu-id="84849-104">Per impostazione predefinita, un <xref:System.Windows.Media.TileBrush> produce un singolo riquadro che riempie completamente l'area da disegnare.</span><span class="sxs-lookup"><span data-stu-id="84849-104">By default, a <xref:System.Windows.Media.TileBrush> produces a single tile that completely fills the area that you are painting.</span></span> <span data-ttu-id="84849-105">È possibile eseguire l'override di questo comportamento impostando la <xref:System.Windows.Media.TileBrush.Viewport%2A> e <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="84849-105">You can override this behavior by setting the <xref:System.Windows.Media.TileBrush.Viewport%2A> and <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> properties.</span></span>  
  
 <span data-ttu-id="84849-106">Il <xref:System.Windows.Media.TileBrush.Viewport%2A> proprietà specifica la dimensione dei riquadri per un <xref:System.Windows.Media.TileBrush>.</span><span class="sxs-lookup"><span data-stu-id="84849-106">The <xref:System.Windows.Media.TileBrush.Viewport%2A> property specifies the tile size for a <xref:System.Windows.Media.TileBrush>.</span></span> <span data-ttu-id="84849-107">Per impostazione predefinita, il valore di <xref:System.Windows.Media.TileBrush.Viewport%2A> proprietà è relativo alle dimensioni dell'area da disegnare.</span><span class="sxs-lookup"><span data-stu-id="84849-107">By default, the value of the <xref:System.Windows.Media.TileBrush.Viewport%2A> property is relative to the size of the area being painted.</span></span> <span data-ttu-id="84849-108">Per rendere il <xref:System.Windows.Media.TileBrush.Viewport%2A> proprietà specificare una dimensione assoluta della tessera, impostare il <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> proprietà <xref:System.Windows.Media.BrushMappingMode.Absolute>.</span><span class="sxs-lookup"><span data-stu-id="84849-108">To make the <xref:System.Windows.Media.TileBrush.Viewport%2A> property specify an absolute tile size, set the <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> property to <xref:System.Windows.Media.BrushMappingMode.Absolute>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="84849-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="84849-109">Example</span></span>  
 <span data-ttu-id="84849-110">Nell'esempio seguente viene utilizzato un <xref:System.Windows.Media.ImageBrush>, un tipo di <xref:System.Windows.Media.TileBrush>per disegnare un rettangolo con i riquadri.</span><span class="sxs-lookup"><span data-stu-id="84849-110">The following example uses an <xref:System.Windows.Media.ImageBrush>, a type of <xref:System.Windows.Media.TileBrush>, to paint a rectangle with tiles.</span></span> <span data-ttu-id="84849-111">L'esempio imposta ogni tessera su un valore pari a 50% x 50% dell'area di output (rettangolo).</span><span class="sxs-lookup"><span data-stu-id="84849-111">The example sets each tile to  50 percent by 50 percent of the output area (the rectangle).</span></span> <span data-ttu-id="84849-112">Di conseguenza, il rettangolo viene disegnato con quattro proiezioni dell'immagine.</span><span class="sxs-lookup"><span data-stu-id="84849-112">As a result, the rectangle is painted with four projections of the image.</span></span>  
  
 <span data-ttu-id="84849-113">L'immagine seguente illustra l'output generato dall'esempio.</span><span class="sxs-lookup"><span data-stu-id="84849-113">The following illustration shows the output that the example produces.</span></span>
  
 <span data-ttu-id="84849-114">![Esempio di affiancamento con un tratto con immagine](../../../../docs/framework/wpf/graphics-multimedia/media/0.png "0")</span><span class="sxs-lookup"><span data-stu-id="84849-114">![Example of tiling with an image brush](../../../../docs/framework/wpf/graphics-multimedia/media/0.png "0")</span></span>  
  
 [!code-csharp[UsingImageBrush_snip#RelativeTileSizeExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/TileSizeExample.cs#relativetilesizeexample)]  
  
 <span data-ttu-id="84849-115">Nell'esempio successivo viene creato un <xref:System.Windows.Media.ImageBrush>, imposta il relativo <xref:System.Windows.Media.TileBrush.Viewport%2A> per `0,0,25,25` e il relativo <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> per <xref:System.Windows.Media.BrushMappingMode.Absolute>che viene utilizzato per disegnare il rettangolo di un altro.</span><span class="sxs-lookup"><span data-stu-id="84849-115">The next example creates an <xref:System.Windows.Media.ImageBrush>, sets its <xref:System.Windows.Media.TileBrush.Viewport%2A> to `0,0,25,25` and its <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> to <xref:System.Windows.Media.BrushMappingMode.Absolute>, and uses it to paint another rectangle.</span></span> <span data-ttu-id="84849-116">Di conseguenza, il pennello genera tessere con una larghezza pari a 25 pixel e un'altezza pari a 25 pixel.</span><span class="sxs-lookup"><span data-stu-id="84849-116">As a result, the brush produces tiles that have a width of 25  pixels and a height of 25 pixels .</span></span>  
  
 <span data-ttu-id="84849-117">L'immagine seguente illustra l'output generato dall'esempio.</span><span class="sxs-lookup"><span data-stu-id="84849-117">The following illustration shows the output that the example produces.</span></span>  
  
 <span data-ttu-id="84849-118">![TileBrush affiancato con un viewport di 0,0,0.25,0.25](../../../../docs/framework/wpf/graphics-multimedia/media/25x25viewport.png "25x25viewport")</span><span class="sxs-lookup"><span data-stu-id="84849-118">![A tiled TileBrush with a Viewport of 0,0,0.25,0.25](../../../../docs/framework/wpf/graphics-multimedia/media/25x25viewport.png "25x25viewport")</span></span>  
  
 [!code-csharp[UsingImageBrush_snip#AbsoluteTileSizeExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/TileSizeExample.cs#absolutetilesizeexample)]  
  
 <span data-ttu-id="84849-119">Gli esempi precedenti fanno parte di un esempio più esaustivo.</span><span class="sxs-lookup"><span data-stu-id="84849-119">The preceding examples are part of a larger sample.</span></span> <span data-ttu-id="84849-120">Per l'esempio completo, vedere [esempio ImageBrush](http://go.microsoft.com/fwlink/?LinkID=160005).</span><span class="sxs-lookup"><span data-stu-id="84849-120">For the complete sample, see [ImageBrush Sample](http://go.microsoft.com/fwlink/?LinkID=160005).</span></span>  
  
 <span data-ttu-id="84849-121">Sebbene questo esempio viene utilizzato il <xref:System.Windows.Media.ImageBrush> (classe), il <xref:System.Windows.Media.TileBrush.Viewport%2A> e <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> si comportano in modo identico per l'altro <xref:System.Windows.Media.TileBrush> oggetti, vale a dire per <xref:System.Windows.Media.DrawingBrush> e <xref:System.Windows.Media.VisualBrush>.</span><span class="sxs-lookup"><span data-stu-id="84849-121">Although this example uses the <xref:System.Windows.Media.ImageBrush> class, the <xref:System.Windows.Media.TileBrush.Viewport%2A> and <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> properties behave identically for the other <xref:System.Windows.Media.TileBrush> objects, that is, for <xref:System.Windows.Media.DrawingBrush> and <xref:System.Windows.Media.VisualBrush>.</span></span> <span data-ttu-id="84849-122">Per ulteriori informazioni su <xref:System.Windows.Media.ImageBrush> e l'altro <xref:System.Windows.Media.TileBrush> degli oggetti, vedere [il disegno di immagini, disegni e oggetti visivi](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md).</span><span class="sxs-lookup"><span data-stu-id="84849-122">For more information about <xref:System.Windows.Media.ImageBrush> and the other <xref:System.Windows.Media.TileBrush> objects, see [Painting with Images, Drawings, and Visuals](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84849-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="84849-123">See Also</span></span>  
 <xref:System.Windows.Media.TileBrush>  
 [<span data-ttu-id="84849-124">Disegnare con oggetti Image, Drawing e Visual</span><span class="sxs-lookup"><span data-stu-id="84849-124">Painting with Images, Drawings, and Visuals</span></span>](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)  
 [<span data-ttu-id="84849-125">Creare modelli di elementi affiancati differenti con un TileBrush</span><span class="sxs-lookup"><span data-stu-id="84849-125">Create Different Tile Patterns with a TileBrush</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-different-tile-patterns-with-a-tilebrush.md)
