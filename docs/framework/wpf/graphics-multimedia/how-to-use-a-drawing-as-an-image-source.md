---
title: 'Procedura: utilizzare un disegno come origine di immagini'
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], drawings [WPF], as image sources
- image sources [WPF], drawings
- drawings [WPF], as image sources
ms.assetid: dcf71c7b-9e86-4b8e-8e39-0d0ce0389ef4
ms.openlocfilehash: 7da8a2a594b0562667aaf417d736159d98818a63
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33562290"
---
# <a name="how-to-use-a-drawing-as-an-image-source"></a><span data-ttu-id="556d3-102">Procedura: utilizzare un disegno come origine di immagini</span><span class="sxs-lookup"><span data-stu-id="556d3-102">How to: Use a Drawing as an Image Source</span></span>
<span data-ttu-id="556d3-103">In questo esempio viene illustrato come utilizzare un <xref:System.Windows.Media.Drawing> come il <xref:System.Windows.Controls.Image.Source%2A> per un <xref:System.Windows.Controls.Image> controllo.</span><span class="sxs-lookup"><span data-stu-id="556d3-103">This example shows how to use a <xref:System.Windows.Media.Drawing> as the <xref:System.Windows.Controls.Image.Source%2A> for an <xref:System.Windows.Controls.Image> control.</span></span> <span data-ttu-id="556d3-104">Per visualizzare un <xref:System.Windows.Media.Drawing> con un <xref:System.Windows.Controls.Image> controllo, utilizzare un <xref:System.Windows.Media.DrawingImage> come il <xref:System.Windows.Controls.Image> del controllo <xref:System.Windows.Controls.Image.Source%2A> e impostare il <xref:System.Windows.Media.DrawingImage> dell'oggetto <xref:System.Windows.Media.DrawingImage.Drawing%2A?displayProperty=nameWithType> proprietà per il disegno che si desidera visualizzare.</span><span class="sxs-lookup"><span data-stu-id="556d3-104">To display a <xref:System.Windows.Media.Drawing> with an <xref:System.Windows.Controls.Image> control, use a <xref:System.Windows.Media.DrawingImage> as the <xref:System.Windows.Controls.Image> control's <xref:System.Windows.Controls.Image.Source%2A> and set the <xref:System.Windows.Media.DrawingImage> object's <xref:System.Windows.Media.DrawingImage.Drawing%2A?displayProperty=nameWithType> property to the drawing you want to display.</span></span>  
  
## <a name="example"></a><span data-ttu-id="556d3-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="556d3-105">Example</span></span>  
 <span data-ttu-id="556d3-106">Nell'esempio seguente viene utilizzato un <xref:System.Windows.Media.DrawingImage> e <xref:System.Windows.Controls.Image> controllo per visualizzare un <xref:System.Windows.Media.GeometryDrawing>.</span><span class="sxs-lookup"><span data-stu-id="556d3-106">The following example uses a <xref:System.Windows.Media.DrawingImage> and an <xref:System.Windows.Controls.Image> control to display a <xref:System.Windows.Media.GeometryDrawing>.</span></span> <span data-ttu-id="556d3-107">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="556d3-107">This example produces the following output:</span></span>  
  
 <span data-ttu-id="556d3-108">![GeometryDrawing di due ellissi](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-geodraw.jpg "graphicsmm_geodraw")</span><span class="sxs-lookup"><span data-stu-id="556d3-108">![A GeometryDrawing of two ellipses](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-geodraw.jpg "graphicsmm_geodraw")</span></span>  
<span data-ttu-id="556d3-109">Oggetto DrawingImage</span><span class="sxs-lookup"><span data-stu-id="556d3-109">A DrawingImage</span></span>  
  
 [!code-csharp[DrawingMiscSnippets_snip#DrawingImageExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingImageExample.cs#drawingimageexamplewholepage)]
 [!code-xaml[DrawingMiscSnippets_snip#DrawingImageExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingImageExample.xaml#drawingimageexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="556d3-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="556d3-110">See Also</span></span>  
 <xref:System.Windows.Freezable.Freeze%2A>  
 [<span data-ttu-id="556d3-111">Disegnare un'immagine con ImageDrawing</span><span class="sxs-lookup"><span data-stu-id="556d3-111">Draw an Image Using ImageDrawing</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-draw-an-image-using-imagedrawing.md)  
 [<span data-ttu-id="556d3-112">Cenni preliminari sugli oggetti Drawing</span><span class="sxs-lookup"><span data-stu-id="556d3-112">Drawing Objects Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)  
 [<span data-ttu-id="556d3-113">Cenni preliminari sugli oggetti Freezable</span><span class="sxs-lookup"><span data-stu-id="556d3-113">Freezable Objects Overview</span></span>](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)  
 [<span data-ttu-id="556d3-114">Attributo PresentationOptions:Freeze</span><span class="sxs-lookup"><span data-stu-id="556d3-114">PresentationOptions:Freeze Attribute</span></span>](../../../../docs/framework/wpf/advanced/presentationoptions-freeze-attribute.md)
