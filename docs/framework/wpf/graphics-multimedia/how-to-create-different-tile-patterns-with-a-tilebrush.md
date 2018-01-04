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
# <a name="how-to-create-different-tile-patterns-with-a-tilebrush"></a>Procedura: creare modelli di elementi affiancati differenti con un TileBrush
In questo esempio viene illustrato come utilizzare il <xref:System.Windows.Media.TileBrush.TileMode%2A> proprietà di un <xref:System.Windows.Media.TileBrush> per creare un modello.  
  
 Il <xref:System.Windows.Media.TileBrush.TileMode%2A> proprietà consente di specificare come il contenuto di un <xref:System.Windows.Media.TileBrush> è ripetuto, vale a dire, affiancato per riempire un'area di output. Per creare un modello, impostare il <xref:System.Windows.Media.TileBrush.TileMode%2A> a <xref:System.Windows.Media.TileMode.Tile>, <xref:System.Windows.Media.TileMode.FlipX>, <xref:System.Windows.Media.TileMode.FlipY>, o <xref:System.Windows.Media.TileMode.FlipXY>. È necessario impostare anche la <xref:System.Windows.Media.TileBrush.Viewport%2A> del <xref:System.Windows.Media.TileBrush> in modo che sia più piccola dell'area da disegnare; in caso contrario, solo un singolo riquadro verrà prodotto, indipendentemente dal quale <xref:System.Windows.Media.TileBrush.TileMode%2A> impostazione utilizzata.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente crea cinque <xref:System.Windows.Media.DrawingBrush> gli oggetti, ciascuno di essi fornisce un altro <xref:System.Windows.Media.TileBrush.TileMode%2A> impostazione e li utilizza per disegnare cinque rettangoli. Anche se in questo esempio viene utilizzato il <xref:System.Windows.Media.DrawingBrush> classe per illustrare <xref:System.Windows.Media.TileBrush.TileMode%2A> comportamento, il <xref:System.Windows.Media.TileBrush.TileMode%2A> proprietà funziona in modo identico per tutti i <xref:System.Windows.Media.TileBrush> oggetti, vale a dire per <xref:System.Windows.Media.ImageBrush>, <xref:System.Windows.Media.VisualBrush>, e <xref:System.Windows.Media.DrawingBrush>.  
  
 L'immagine seguente illustra l'output generato dall'esempio.  
  
 ![Output di esempio di affiancamento di TileBrush](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-drawingbrushtilemodeexample.png "graphicsmm_DrawingBrushTileModeExample")  
Riquadro schemi creati con la proprietà TileMode  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMDrawingBrushTileModeExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/TileModeExample.cs#graphicsmmdrawingbrushtilemodeexample)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMDrawingBrushTileModeExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/tilemodeexample.vb#graphicsmmdrawingbrushtilemodeexample)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMDrawingBrushTileModeExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/TileModeExample.xaml#graphicsmmdrawingbrushtilemodeexample)]  
  
## <a name="see-also"></a>Vedere anche  
 [Impostare la dimensione degli elementi affiancati di un TileBrush](../../../../docs/framework/wpf/graphics-multimedia/how-to-set-the-tile-size-for-a-tilebrush.md)  
 [Disegnare con oggetti Image, Drawing e Visual](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)
