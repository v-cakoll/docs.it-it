---
title: 'Procedura: Usare un disegno come origine di immagini'
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], drawings [WPF], as image sources
- image sources [WPF], drawings
- drawings [WPF], as image sources
ms.assetid: dcf71c7b-9e86-4b8e-8e39-0d0ce0389ef4
ms.openlocfilehash: d4b91a6495e1c54400d5fbfe43b6311d908565a7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59097860"
---
# <a name="how-to-use-a-drawing-as-an-image-source"></a><span data-ttu-id="30955-102">Procedura: Usare un disegno come origine di immagini</span><span class="sxs-lookup"><span data-stu-id="30955-102">How to: Use a Drawing as an Image Source</span></span>
<span data-ttu-id="30955-103">In questo esempio viene illustrato come utilizzare un <xref:System.Windows.Media.Drawing> come il <xref:System.Windows.Controls.Image.Source%2A> per un <xref:System.Windows.Controls.Image> controllo.</span><span class="sxs-lookup"><span data-stu-id="30955-103">This example shows how to use a <xref:System.Windows.Media.Drawing> as the <xref:System.Windows.Controls.Image.Source%2A> for an <xref:System.Windows.Controls.Image> control.</span></span> <span data-ttu-id="30955-104">Per visualizzare un <xref:System.Windows.Media.Drawing> con un <xref:System.Windows.Controls.Image> controllare, utilizzare un <xref:System.Windows.Media.DrawingImage> come il <xref:System.Windows.Controls.Image> del controllo <xref:System.Windows.Controls.Image.Source%2A> e impostare il <xref:System.Windows.Media.DrawingImage> dell'oggetto <xref:System.Windows.Media.DrawingImage.Drawing%2A?displayProperty=nameWithType> proprietà per il disegno che si desidera visualizzare.</span><span class="sxs-lookup"><span data-stu-id="30955-104">To display a <xref:System.Windows.Media.Drawing> with an <xref:System.Windows.Controls.Image> control, use a <xref:System.Windows.Media.DrawingImage> as the <xref:System.Windows.Controls.Image> control's <xref:System.Windows.Controls.Image.Source%2A> and set the <xref:System.Windows.Media.DrawingImage> object's <xref:System.Windows.Media.DrawingImage.Drawing%2A?displayProperty=nameWithType> property to the drawing you want to display.</span></span>  
  
## <a name="example"></a><span data-ttu-id="30955-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="30955-105">Example</span></span>  
 <span data-ttu-id="30955-106">L'esempio seguente usa un' <xref:System.Windows.Media.DrawingImage> e un' <xref:System.Windows.Controls.Image> controllo per visualizzare un <xref:System.Windows.Media.GeometryDrawing>.</span><span class="sxs-lookup"><span data-stu-id="30955-106">The following example uses a <xref:System.Windows.Media.DrawingImage> and an <xref:System.Windows.Controls.Image> control to display a <xref:System.Windows.Media.GeometryDrawing>.</span></span> <span data-ttu-id="30955-107">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="30955-107">This example produces the following output:</span></span>  
  
 <span data-ttu-id="30955-108">![Un oggetto GeometryDrawing di due ellissi](./media/graphicsmm-geodraw.jpg "graphicsmm_geodraw")</span><span class="sxs-lookup"><span data-stu-id="30955-108">![A GeometryDrawing of two ellipses](./media/graphicsmm-geodraw.jpg "graphicsmm_geodraw")</span></span>  
<span data-ttu-id="30955-109">Oggetto DrawingImage</span><span class="sxs-lookup"><span data-stu-id="30955-109">A DrawingImage</span></span>  
  
 [!code-csharp[DrawingMiscSnippets_snip#DrawingImageExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingImageExample.cs#drawingimageexamplewholepage)]
 [!code-xaml[DrawingMiscSnippets_snip#DrawingImageExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingImageExample.xaml#drawingimageexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="30955-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="30955-110">See also</span></span>

- <xref:System.Windows.Freezable.Freeze%2A>
- [<span data-ttu-id="30955-111">Disegnare un'immagine con ImageDrawing</span><span class="sxs-lookup"><span data-stu-id="30955-111">Draw an Image Using ImageDrawing</span></span>](how-to-draw-an-image-using-imagedrawing.md)
- [<span data-ttu-id="30955-112">Cenni preliminari sugli oggetti Drawing</span><span class="sxs-lookup"><span data-stu-id="30955-112">Drawing Objects Overview</span></span>](drawing-objects-overview.md)
- [<span data-ttu-id="30955-113">Cenni preliminari sugli oggetti Freezable</span><span class="sxs-lookup"><span data-stu-id="30955-113">Freezable Objects Overview</span></span>](../advanced/freezable-objects-overview.md)
- [<span data-ttu-id="30955-114">Attributo PresentationOptions:Freeze</span><span class="sxs-lookup"><span data-stu-id="30955-114">PresentationOptions:Freeze Attribute</span></span>](../advanced/presentationoptions-freeze-attribute.md)
