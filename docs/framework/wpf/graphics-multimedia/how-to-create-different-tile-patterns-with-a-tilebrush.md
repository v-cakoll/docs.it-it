---
title: 'Procedura: creare modelli di elementi affiancati differenti con un TileBrush'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TileBrush [WPF], creating tile patterns
- tile patterns [WPF], creating
- creating [WPF], tile patterns with TileBrush
ms.assetid: 5aa46632-3527-4668-9d8d-0375c8af28aa
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 646ce5142875c95c0b1ca19643790f73f7eb83e9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-different-tile-patterns-with-a-tilebrush"></a><span data-ttu-id="6ec1a-102">Procedura: creare modelli di elementi affiancati differenti con un TileBrush</span><span class="sxs-lookup"><span data-stu-id="6ec1a-102">How to: Create Different Tile Patterns with a TileBrush</span></span>
<span data-ttu-id="6ec1a-103">In questo esempio viene illustrato come utilizzare il <xref:System.Windows.Media.TileBrush.TileMode%2A> proprietà di un <xref:System.Windows.Media.TileBrush> per creare un modello.</span><span class="sxs-lookup"><span data-stu-id="6ec1a-103">This example shows how to use the <xref:System.Windows.Media.TileBrush.TileMode%2A> property of a <xref:System.Windows.Media.TileBrush> to create a pattern.</span></span>  
  
 <span data-ttu-id="6ec1a-104">Il <xref:System.Windows.Media.TileBrush.TileMode%2A> proprietà consente di specificare come il contenuto di un <xref:System.Windows.Media.TileBrush> è ripetuto, vale a dire, affiancato per riempire un'area di output.</span><span class="sxs-lookup"><span data-stu-id="6ec1a-104">The <xref:System.Windows.Media.TileBrush.TileMode%2A> property enables you to specify how the content of a <xref:System.Windows.Media.TileBrush> is repeated, that is, tiled to fill an output area.</span></span> <span data-ttu-id="6ec1a-105">Per creare un modello, impostare il <xref:System.Windows.Media.TileBrush.TileMode%2A> a <xref:System.Windows.Media.TileMode.Tile>, <xref:System.Windows.Media.TileMode.FlipX>, <xref:System.Windows.Media.TileMode.FlipY>, o <xref:System.Windows.Media.TileMode.FlipXY>.</span><span class="sxs-lookup"><span data-stu-id="6ec1a-105">To create a pattern, you set the <xref:System.Windows.Media.TileBrush.TileMode%2A> to <xref:System.Windows.Media.TileMode.Tile>, <xref:System.Windows.Media.TileMode.FlipX>, <xref:System.Windows.Media.TileMode.FlipY>, or <xref:System.Windows.Media.TileMode.FlipXY>.</span></span> <span data-ttu-id="6ec1a-106">È necessario impostare anche la <xref:System.Windows.Media.TileBrush.Viewport%2A> del <xref:System.Windows.Media.TileBrush> in modo che sia più piccola dell'area da disegnare; in caso contrario, solo un singolo riquadro verrà prodotto, indipendentemente dal quale <xref:System.Windows.Media.TileBrush.TileMode%2A> impostazione utilizzata.</span><span class="sxs-lookup"><span data-stu-id="6ec1a-106">You must also set the <xref:System.Windows.Media.TileBrush.Viewport%2A> of the <xref:System.Windows.Media.TileBrush> so that it is smaller than the area that you are painting; otherwise, only a single tile is produced, regardless which <xref:System.Windows.Media.TileBrush.TileMode%2A> setting you use.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6ec1a-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="6ec1a-107">Example</span></span>  
 <span data-ttu-id="6ec1a-108">L'esempio seguente crea cinque <xref:System.Windows.Media.DrawingBrush> gli oggetti, ciascuno di essi fornisce un altro <xref:System.Windows.Media.TileBrush.TileMode%2A> impostazione e li utilizza per disegnare cinque rettangoli.</span><span class="sxs-lookup"><span data-stu-id="6ec1a-108">The following example creates five <xref:System.Windows.Media.DrawingBrush> objects, gives them each a different <xref:System.Windows.Media.TileBrush.TileMode%2A> setting, and uses them to paint five rectangles.</span></span> <span data-ttu-id="6ec1a-109">Anche se in questo esempio viene utilizzato il <xref:System.Windows.Media.DrawingBrush> classe per illustrare <xref:System.Windows.Media.TileBrush.TileMode%2A> comportamento, il <xref:System.Windows.Media.TileBrush.TileMode%2A> proprietà funziona in modo identico per tutti i <xref:System.Windows.Media.TileBrush> oggetti, vale a dire per <xref:System.Windows.Media.ImageBrush>, <xref:System.Windows.Media.VisualBrush>, e <xref:System.Windows.Media.DrawingBrush>.</span><span class="sxs-lookup"><span data-stu-id="6ec1a-109">Although this example uses the <xref:System.Windows.Media.DrawingBrush> class to demonstrate <xref:System.Windows.Media.TileBrush.TileMode%2A> behavior, the <xref:System.Windows.Media.TileBrush.TileMode%2A> property works identically for all the <xref:System.Windows.Media.TileBrush> objects, that is, for <xref:System.Windows.Media.ImageBrush>, <xref:System.Windows.Media.VisualBrush>, and <xref:System.Windows.Media.DrawingBrush>.</span></span>  
  
 <span data-ttu-id="6ec1a-110">L'immagine seguente illustra l'output generato dall'esempio.</span><span class="sxs-lookup"><span data-stu-id="6ec1a-110">The following illustration shows the output that this example produces.</span></span>  
  
 <span data-ttu-id="6ec1a-111">![Output di esempio di affiancamento di TileBrush](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-drawingbrushtilemodeexample.png "graphicsmm_DrawingBrushTileModeExample")</span><span class="sxs-lookup"><span data-stu-id="6ec1a-111">![TileBrush tiling example output](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-drawingbrushtilemodeexample.png "graphicsmm_DrawingBrushTileModeExample")</span></span>  
<span data-ttu-id="6ec1a-112">Riquadro schemi creati con la proprietà TileMode</span><span class="sxs-lookup"><span data-stu-id="6ec1a-112">Tile patterns created with the TileMode property</span></span>  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMDrawingBrushTileModeExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/TileModeExample.cs#graphicsmmdrawingbrushtilemodeexample)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMDrawingBrushTileModeExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/tilemodeexample.vb#graphicsmmdrawingbrushtilemodeexample)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMDrawingBrushTileModeExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/TileModeExample.xaml#graphicsmmdrawingbrushtilemodeexample)]  
  
## <a name="see-also"></a><span data-ttu-id="6ec1a-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6ec1a-113">See Also</span></span>  
 [<span data-ttu-id="6ec1a-114">Impostare la dimensione degli elementi affiancati di un TileBrush</span><span class="sxs-lookup"><span data-stu-id="6ec1a-114">Set the Tile Size for a TileBrush</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-set-the-tile-size-for-a-tilebrush.md)  
 [<span data-ttu-id="6ec1a-115">Disegnare con oggetti Image, Drawing e Visual</span><span class="sxs-lookup"><span data-stu-id="6ec1a-115">Painting with Images, Drawings, and Visuals</span></span>](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)
