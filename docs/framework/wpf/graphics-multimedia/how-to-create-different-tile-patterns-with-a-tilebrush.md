---
title: 'Procedura: Creare modelli di elementi affiancati differenti con un TileBrush'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TileBrush [WPF], creating tile patterns
- tile patterns [WPF], creating
- creating [WPF], tile patterns with TileBrush
ms.assetid: 5aa46632-3527-4668-9d8d-0375c8af28aa
ms.openlocfilehash: c1051b234961eee9ae740af2abac3d64c523656c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61905132"
---
# <a name="how-to-create-different-tile-patterns-with-a-tilebrush"></a><span data-ttu-id="52510-102">Procedura: Creare modelli di elementi affiancati differenti con un TileBrush</span><span class="sxs-lookup"><span data-stu-id="52510-102">How to: Create Different Tile Patterns with a TileBrush</span></span>
<span data-ttu-id="52510-103">Questo esempio illustra come usare il <xref:System.Windows.Media.TileBrush.TileMode%2A> proprietà di un <xref:System.Windows.Media.TileBrush> per creare un modello.</span><span class="sxs-lookup"><span data-stu-id="52510-103">This example shows how to use the <xref:System.Windows.Media.TileBrush.TileMode%2A> property of a <xref:System.Windows.Media.TileBrush> to create a pattern.</span></span>  
  
 <span data-ttu-id="52510-104">Il <xref:System.Windows.Media.TileBrush.TileMode%2A> proprietà consente di specificare come il contenuto di un <xref:System.Windows.Media.TileBrush> è ripetuto, vale a dire, affiancato per riempire un'area di output.</span><span class="sxs-lookup"><span data-stu-id="52510-104">The <xref:System.Windows.Media.TileBrush.TileMode%2A> property enables you to specify how the content of a <xref:System.Windows.Media.TileBrush> is repeated, that is, tiled to fill an output area.</span></span> <span data-ttu-id="52510-105">Per creare un modello, si imposta la <xref:System.Windows.Media.TileBrush.TileMode%2A> al <xref:System.Windows.Media.TileMode.Tile>, <xref:System.Windows.Media.TileMode.FlipX>, <xref:System.Windows.Media.TileMode.FlipY>, o <xref:System.Windows.Media.TileMode.FlipXY>.</span><span class="sxs-lookup"><span data-stu-id="52510-105">To create a pattern, you set the <xref:System.Windows.Media.TileBrush.TileMode%2A> to <xref:System.Windows.Media.TileMode.Tile>, <xref:System.Windows.Media.TileMode.FlipX>, <xref:System.Windows.Media.TileMode.FlipY>, or <xref:System.Windows.Media.TileMode.FlipXY>.</span></span> <span data-ttu-id="52510-106">È necessario impostare anche il <xref:System.Windows.Media.TileBrush.Viewport%2A> del <xref:System.Windows.Media.TileBrush> in modo che sia più piccola dell'area da disegnare; in caso contrario, solo un singolo riquadro viene generato, indipendentemente dal quale <xref:System.Windows.Media.TileBrush.TileMode%2A> impostazione utilizzata.</span><span class="sxs-lookup"><span data-stu-id="52510-106">You must also set the <xref:System.Windows.Media.TileBrush.Viewport%2A> of the <xref:System.Windows.Media.TileBrush> so that it is smaller than the area that you are painting; otherwise, only a single tile is produced, regardless which <xref:System.Windows.Media.TileBrush.TileMode%2A> setting you use.</span></span>  
  
## <a name="example"></a><span data-ttu-id="52510-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="52510-107">Example</span></span>  
 <span data-ttu-id="52510-108">L'esempio seguente crea cinque <xref:System.Windows.Media.DrawingBrush> gli oggetti, viene assegnata a ciascuno un diverso <xref:System.Windows.Media.TileBrush.TileMode%2A> impostazione e li utilizza per disegnare cinque rettangoli.</span><span class="sxs-lookup"><span data-stu-id="52510-108">The following example creates five <xref:System.Windows.Media.DrawingBrush> objects, gives them each a different <xref:System.Windows.Media.TileBrush.TileMode%2A> setting, and uses them to paint five rectangles.</span></span> <span data-ttu-id="52510-109">Anche se in questo esempio Usa il <xref:System.Windows.Media.DrawingBrush> classe per illustrare <xref:System.Windows.Media.TileBrush.TileMode%2A> comportamento, il <xref:System.Windows.Media.TileBrush.TileMode%2A> proprietà funziona in modo identico per tutti i i <xref:System.Windows.Media.TileBrush> oggetti, vale a dire, per <xref:System.Windows.Media.ImageBrush>, <xref:System.Windows.Media.VisualBrush>, e <xref:System.Windows.Media.DrawingBrush>.</span><span class="sxs-lookup"><span data-stu-id="52510-109">Although this example uses the <xref:System.Windows.Media.DrawingBrush> class to demonstrate <xref:System.Windows.Media.TileBrush.TileMode%2A> behavior, the <xref:System.Windows.Media.TileBrush.TileMode%2A> property works identically for all the <xref:System.Windows.Media.TileBrush> objects, that is, for <xref:System.Windows.Media.ImageBrush>, <xref:System.Windows.Media.VisualBrush>, and <xref:System.Windows.Media.DrawingBrush>.</span></span>  
  
 <span data-ttu-id="52510-110">L'immagine seguente illustra l'output generato dall'esempio.</span><span class="sxs-lookup"><span data-stu-id="52510-110">The following illustration shows the output that this example produces.</span></span>  
  
 <span data-ttu-id="52510-111">![Output di esempio di affiancamento di TileBrush](./media/graphicsmm-drawingbrushtilemodeexample.png "graphicsmm_DrawingBrushTileModeExample")</span><span class="sxs-lookup"><span data-stu-id="52510-111">![TileBrush tiling example output](./media/graphicsmm-drawingbrushtilemodeexample.png "graphicsmm_DrawingBrushTileModeExample")</span></span>  
<span data-ttu-id="52510-112">Modelli creati con la proprietà TileMode</span><span class="sxs-lookup"><span data-stu-id="52510-112">Tile patterns created with the TileMode property</span></span>  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMDrawingBrushTileModeExample](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/TileModeExample.cs#graphicsmmdrawingbrushtilemodeexample)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMDrawingBrushTileModeExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/tilemodeexample.vb#graphicsmmdrawingbrushtilemodeexample)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMDrawingBrushTileModeExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/TileModeExample.xaml#graphicsmmdrawingbrushtilemodeexample)]  
  
## <a name="see-also"></a><span data-ttu-id="52510-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="52510-113">See also</span></span>

- [<span data-ttu-id="52510-114">Impostare la dimensione degli elementi affiancati di un TileBrush</span><span class="sxs-lookup"><span data-stu-id="52510-114">Set the Tile Size for a TileBrush</span></span>](how-to-set-the-tile-size-for-a-tilebrush.md)
- [<span data-ttu-id="52510-115">Disegnare con oggetti Image, Drawing e Visual</span><span class="sxs-lookup"><span data-stu-id="52510-115">Painting with Images, Drawings, and Visuals</span></span>](painting-with-images-drawings-and-visuals.md)
