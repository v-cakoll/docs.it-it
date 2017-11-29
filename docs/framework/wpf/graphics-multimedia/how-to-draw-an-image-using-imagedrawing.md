---
title: "Procedura: disegnare un’immagine con ImageDrawing"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- drawing [WPF], images
- graphics [WPF], drawing images
- images [WPF], drawing
ms.assetid: df28ab41-25fb-4ab3-b51d-7f695b24f55e
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2d975d33bb3c102e5294d78dc76d8136ab521953
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-draw-an-image-using-imagedrawing"></a><span data-ttu-id="79f5f-102">Procedura: disegnare un’immagine con ImageDrawing</span><span class="sxs-lookup"><span data-stu-id="79f5f-102">How to: Draw an Image Using ImageDrawing</span></span>
<span data-ttu-id="79f5f-103">In questo esempio viene illustrato come utilizzare un <xref:System.Windows.Media.ImageDrawing> per disegnare un'immagine.</span><span class="sxs-lookup"><span data-stu-id="79f5f-103">This example shows how to use an <xref:System.Windows.Media.ImageDrawing> to draw an image.</span></span> <span data-ttu-id="79f5f-104">Un <xref:System.Windows.Media.ImageDrawing> consente di visualizzare un <xref:System.Windows.Media.ImageSource> con un <xref:System.Windows.Media.DrawingBrush>, <xref:System.Windows.Media.DrawingImage>, o <xref:System.Windows.Media.Visual>.</span><span class="sxs-lookup"><span data-stu-id="79f5f-104">An <xref:System.Windows.Media.ImageDrawing> enables you display an <xref:System.Windows.Media.ImageSource> with a <xref:System.Windows.Media.DrawingBrush>, <xref:System.Windows.Media.DrawingImage>, or <xref:System.Windows.Media.Visual>.</span></span> <span data-ttu-id="79f5f-105">Per disegnare un'immagine, si crea un <xref:System.Windows.Media.ImageDrawing> e impostare il relativo <xref:System.Windows.Media.ImageDrawing.ImageSource%2A?displayProperty=nameWithType> e <xref:System.Windows.Media.ImageDrawing.Rect%2A?displayProperty=nameWithType> proprietà.</span><span class="sxs-lookup"><span data-stu-id="79f5f-105">To draw an image, you create an <xref:System.Windows.Media.ImageDrawing> and set its <xref:System.Windows.Media.ImageDrawing.ImageSource%2A?displayProperty=nameWithType> and <xref:System.Windows.Media.ImageDrawing.Rect%2A?displayProperty=nameWithType> properties.</span></span> <span data-ttu-id="79f5f-106">Il <xref:System.Windows.Media.ImageDrawing.ImageSource%2A?displayProperty=nameWithType> proprietà specifica l'immagine da disegnare e <xref:System.Windows.Media.ImageDrawing.Rect%2A?displayProperty=nameWithType> proprietà specifica la posizione e le dimensioni di ogni immagine.</span><span class="sxs-lookup"><span data-stu-id="79f5f-106">The <xref:System.Windows.Media.ImageDrawing.ImageSource%2A?displayProperty=nameWithType> property specifies the image to draw, and the <xref:System.Windows.Media.ImageDrawing.Rect%2A?displayProperty=nameWithType> property specifies the position and size of each image.</span></span>  
  
## <a name="example"></a><span data-ttu-id="79f5f-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="79f5f-107">Example</span></span>  
 <span data-ttu-id="79f5f-108">Nell'esempio seguente viene creato un disegno composto utilizzando quattro <xref:System.Windows.Media.ImageDrawing> oggetti.</span><span class="sxs-lookup"><span data-stu-id="79f5f-108">The following example creates a composite drawing using four <xref:System.Windows.Media.ImageDrawing> objects.</span></span> <span data-ttu-id="79f5f-109">Questo esempio produce il seguente immagine:</span><span class="sxs-lookup"><span data-stu-id="79f5f-109">This example produces the following image:</span></span>  
  
 <span data-ttu-id="79f5f-110">![Alcuni oggetti DrawingImage](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-imagedrawingexample.jpg "graphicsmm_ImageDrawingExample")</span><span class="sxs-lookup"><span data-stu-id="79f5f-110">![Several DrawingImage objects](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-imagedrawingexample.jpg "graphicsmm_ImageDrawingExample")</span></span>  
<span data-ttu-id="79f5f-111">Quattro oggetti ImageDrawing</span><span class="sxs-lookup"><span data-stu-id="79f5f-111">Four ImageDrawing objects</span></span>  
  
 [!code-csharp[DrawingMiscSnippets_snip#ImageDrawingExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/ImageDrawingExample.cs#imagedrawingexample)]
 [!code-xaml[DrawingMiscSnippets_snip#ImageDrawingExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/ImageDrawingExample.xaml#imagedrawingexample)]  
  
 <span data-ttu-id="79f5f-112">Per un esempio che illustra un modo semplice per visualizzare un'immagine senza utilizzare <xref:System.Windows.Media.ImageDrawing>, vedere [usare l'elemento immagine](../../../../docs/framework/wpf/controls/how-to-use-the-image-element.md).</span><span class="sxs-lookup"><span data-stu-id="79f5f-112">For an example showing a simple way to display an image without using <xref:System.Windows.Media.ImageDrawing>, see [Use the Image Element](../../../../docs/framework/wpf/controls/how-to-use-the-image-element.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79f5f-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="79f5f-113">See Also</span></span>  
 <xref:System.Windows.Freezable.Freeze%2A>  
 <xref:System.Windows.Controls.Image>  
 [<span data-ttu-id="79f5f-114">Cenni preliminari sugli oggetti Drawing</span><span class="sxs-lookup"><span data-stu-id="79f5f-114">Drawing Objects Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)  
 [<span data-ttu-id="79f5f-115">Cenni preliminari sugli oggetti Freezable</span><span class="sxs-lookup"><span data-stu-id="79f5f-115">Freezable Objects Overview</span></span>](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)  
 [<span data-ttu-id="79f5f-116">Attributo PresentationOptions:Freeze</span><span class="sxs-lookup"><span data-stu-id="79f5f-116">PresentationOptions:Freeze Attribute</span></span>](../../../../docs/framework/wpf/advanced/presentationoptions-freeze-attribute.md)
