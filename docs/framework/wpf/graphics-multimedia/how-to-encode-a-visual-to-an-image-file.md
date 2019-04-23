---
title: 'Procedura: Codificare un oggetto visivo in un file di immagine'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- image files [WPF], encoding from visuals
- encoding image formats [WPF]
- visuals [WPF], encoding to an image file
ms.assetid: 2036385b-ea47-4d54-8027-5797f52c8149
ms.openlocfilehash: 872c19af0cfcf4fc980643c37e9a6028457c03b3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59096784"
---
# <a name="how-to-encode-a-visual-to-an-image-file"></a><span data-ttu-id="1880d-102">Procedura: Codificare un oggetto visivo in un file di immagine</span><span class="sxs-lookup"><span data-stu-id="1880d-102">How to: Encode a Visual to an Image File</span></span>
<span data-ttu-id="1880d-103">In questo esempio illustra come codificare un <xref:System.Windows.Media.Visual> oggetto in un file di immagine usando una <xref:System.Windows.Media.Imaging.RenderTargetBitmap> e un <xref:System.Windows.Media.Imaging.PngBitmapEncoder>.</span><span class="sxs-lookup"><span data-stu-id="1880d-103">This example demonstrates how to encode a <xref:System.Windows.Media.Visual> object into an image file using a <xref:System.Windows.Media.Imaging.RenderTargetBitmap> and a <xref:System.Windows.Media.Imaging.PngBitmapEncoder>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1880d-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="1880d-104">Example</span></span>  
 <span data-ttu-id="1880d-105">Il <xref:System.Windows.Media.DrawingVisual> viene creato utilizzando una <xref:System.Windows.Media.Imaging.BitmapImage> e <xref:System.Windows.Media.FormattedText> che viene eseguito il rendering di un <xref:System.Windows.Media.Imaging.RenderTargetBitmap>.</span><span class="sxs-lookup"><span data-stu-id="1880d-105">The <xref:System.Windows.Media.DrawingVisual> is created using a <xref:System.Windows.Media.Imaging.BitmapImage> and <xref:System.Windows.Media.FormattedText> which is rendered to a <xref:System.Windows.Media.Imaging.RenderTargetBitmap>.</span></span> <span data-ttu-id="1880d-106">La bitmap viene eseguito il rendering viene quindi utilizzata per creare un <xref:System.Windows.Media.Imaging.BitmapFrame> che viene aggiunto per il <xref:System.Windows.Media.Imaging.PngBitmapEncoder> per creare un nuovo [!INCLUDE[TLA#tla_png](../../../../includes/tlasharptla-png-md.md)] file.</span><span class="sxs-lookup"><span data-stu-id="1880d-106">The rendered bitmap is then used to create a <xref:System.Windows.Media.Imaging.BitmapFrame> which is added to the <xref:System.Windows.Media.Imaging.PngBitmapEncoder> to create a new [!INCLUDE[TLA#tla_png](../../../../includes/tlasharptla-png-md.md)] file.</span></span>  
  
 [!code-csharp[ImagingSnippetGallery_procedural_snip#RTBEncodeInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/CSharp/RenderTargetBitmapExample_Encode.cs#rtbencodeinline1)]
 [!code-vb[ImagingSnippetGallery_procedural_snip#RTBEncodeInline1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/VB/RenderTargetBitmapExample_Encode.vb#rtbencodeinline1)]  
  
 <span data-ttu-id="1880d-107">Oggetto <xref:System.Windows.Media.Imaging.PngBitmapEncoder> è stato usato in questo esempio ma dei derivato <xref:System.Windows.Media.Imaging.BitmapEncoder> oggetti avrebbe potuto avere utilizzati per creare il file di immagine.</span><span class="sxs-lookup"><span data-stu-id="1880d-107">A <xref:System.Windows.Media.Imaging.PngBitmapEncoder> was used in this example but any of the derived <xref:System.Windows.Media.Imaging.BitmapEncoder> objects could have been used to create the image file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1880d-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1880d-108">See also</span></span>

- <xref:System.Windows.Media.DrawingContext>
- [<span data-ttu-id="1880d-109">Cenni preliminari sulla creazione dell'immagine</span><span class="sxs-lookup"><span data-stu-id="1880d-109">Imaging Overview</span></span>](imaging-overview.md)
- [<span data-ttu-id="1880d-110">Cenni preliminari sugli oggetti Drawing</span><span class="sxs-lookup"><span data-stu-id="1880d-110">Drawing Objects Overview</span></span>](drawing-objects-overview.md)
- [<span data-ttu-id="1880d-111">Uso degli oggetti DrawingVisual</span><span class="sxs-lookup"><span data-stu-id="1880d-111">Using DrawingVisual Objects</span></span>](using-drawingvisual-objects.md)
