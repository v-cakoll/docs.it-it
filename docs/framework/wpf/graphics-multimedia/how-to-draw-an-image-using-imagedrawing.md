---
title: "Procedura: Disegnare un'immagine con ImageDrawing"
ms.date: 03/30/2017
helpviewer_keywords:
- drawing [WPF], images
- graphics [WPF], drawing images
- images [WPF], drawing
ms.assetid: df28ab41-25fb-4ab3-b51d-7f695b24f55e
ms.openlocfilehash: 9a9a7ee32104e44997e6eaada09edaac2b1d610e
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57355598"
---
# <a name="how-to-draw-an-image-using-imagedrawing"></a><span data-ttu-id="0b56a-102">Procedura: Disegnare un'immagine con ImageDrawing</span><span class="sxs-lookup"><span data-stu-id="0b56a-102">How to: Draw an Image Using ImageDrawing</span></span>
<span data-ttu-id="0b56a-103">In questo esempio viene illustrato come utilizzare un <xref:System.Windows.Media.ImageDrawing> per disegnare un'immagine.</span><span class="sxs-lookup"><span data-stu-id="0b56a-103">This example shows how to use an <xref:System.Windows.Media.ImageDrawing> to draw an image.</span></span> <span data-ttu-id="0b56a-104">Un' <xref:System.Windows.Media.ImageDrawing> consente di visualizzare un' <xref:System.Windows.Media.ImageSource> con un <xref:System.Windows.Media.DrawingBrush>, <xref:System.Windows.Media.DrawingImage>, o <xref:System.Windows.Media.Visual>.</span><span class="sxs-lookup"><span data-stu-id="0b56a-104">An <xref:System.Windows.Media.ImageDrawing> enables you display an <xref:System.Windows.Media.ImageSource> with a <xref:System.Windows.Media.DrawingBrush>, <xref:System.Windows.Media.DrawingImage>, or <xref:System.Windows.Media.Visual>.</span></span> <span data-ttu-id="0b56a-105">Per disegnare un'immagine, si crea un' <xref:System.Windows.Media.ImageDrawing> e impostare relativi <xref:System.Windows.Media.ImageDrawing.ImageSource%2A?displayProperty=nameWithType> e <xref:System.Windows.Media.ImageDrawing.Rect%2A?displayProperty=nameWithType> proprietà.</span><span class="sxs-lookup"><span data-stu-id="0b56a-105">To draw an image, you create an <xref:System.Windows.Media.ImageDrawing> and set its <xref:System.Windows.Media.ImageDrawing.ImageSource%2A?displayProperty=nameWithType> and <xref:System.Windows.Media.ImageDrawing.Rect%2A?displayProperty=nameWithType> properties.</span></span> <span data-ttu-id="0b56a-106">Il <xref:System.Windows.Media.ImageDrawing.ImageSource%2A?displayProperty=nameWithType> proprietà specifica l'immagine da disegnare e il <xref:System.Windows.Media.ImageDrawing.Rect%2A?displayProperty=nameWithType> proprietà specifica la posizione e dimensioni di ogni immagine.</span><span class="sxs-lookup"><span data-stu-id="0b56a-106">The <xref:System.Windows.Media.ImageDrawing.ImageSource%2A?displayProperty=nameWithType> property specifies the image to draw, and the <xref:System.Windows.Media.ImageDrawing.Rect%2A?displayProperty=nameWithType> property specifies the position and size of each image.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0b56a-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="0b56a-107">Example</span></span>  
 <span data-ttu-id="0b56a-108">L'esempio seguente crea un disegno composto con quattro <xref:System.Windows.Media.ImageDrawing> oggetti.</span><span class="sxs-lookup"><span data-stu-id="0b56a-108">The following example creates a composite drawing using four <xref:System.Windows.Media.ImageDrawing> objects.</span></span> <span data-ttu-id="0b56a-109">Questo esempio produce l'immagine seguente:</span><span class="sxs-lookup"><span data-stu-id="0b56a-109">This example produces the following image:</span></span>  
  
 <span data-ttu-id="0b56a-110">![Alcuni oggetti DrawingImage](./media/graphicsmm-imagedrawingexample.jpg "graphicsmm_ImageDrawingExample")</span><span class="sxs-lookup"><span data-stu-id="0b56a-110">![Several DrawingImage objects](./media/graphicsmm-imagedrawingexample.jpg "graphicsmm_ImageDrawingExample")</span></span>  
<span data-ttu-id="0b56a-111">Quattro ImageDrawing (oggetti)</span><span class="sxs-lookup"><span data-stu-id="0b56a-111">Four ImageDrawing objects</span></span>  
  
 [!code-csharp[DrawingMiscSnippets_snip#ImageDrawingExample](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/ImageDrawingExample.cs#imagedrawingexample)]
 [!code-xaml[DrawingMiscSnippets_snip#ImageDrawingExample](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/ImageDrawingExample.xaml#imagedrawingexample)]  
  
 <span data-ttu-id="0b56a-112">Per un esempio che illustra un modo semplice per visualizzare un'immagine senza utilizzare <xref:System.Windows.Media.ImageDrawing>, vedere [utilizzare l'elemento Image](../controls/how-to-use-the-image-element.md).</span><span class="sxs-lookup"><span data-stu-id="0b56a-112">For an example showing a simple way to display an image without using <xref:System.Windows.Media.ImageDrawing>, see [Use the Image Element](../controls/how-to-use-the-image-element.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b56a-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0b56a-113">See also</span></span>
- <xref:System.Windows.Freezable.Freeze%2A>
- <xref:System.Windows.Controls.Image>
- [<span data-ttu-id="0b56a-114">Cenni preliminari sugli oggetti Drawing</span><span class="sxs-lookup"><span data-stu-id="0b56a-114">Drawing Objects Overview</span></span>](drawing-objects-overview.md)
- [<span data-ttu-id="0b56a-115">Cenni preliminari sugli oggetti Freezable</span><span class="sxs-lookup"><span data-stu-id="0b56a-115">Freezable Objects Overview</span></span>](../advanced/freezable-objects-overview.md)
- [<span data-ttu-id="0b56a-116">Attributo PresentationOptions:Freeze</span><span class="sxs-lookup"><span data-stu-id="0b56a-116">PresentationOptions:Freeze Attribute</span></span>](../advanced/presentationoptions-freeze-attribute.md)
