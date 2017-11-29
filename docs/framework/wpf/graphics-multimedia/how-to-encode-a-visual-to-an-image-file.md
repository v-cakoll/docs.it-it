---
title: 'Procedura: codificare un oggetto Visual in un file di immagine'
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
- image files [WPF], encoding from visuals
- encoding image formats [WPF]
- visuals [WPF], encoding to an image file
ms.assetid: 2036385b-ea47-4d54-8027-5797f52c8149
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0a1ff9de1f5ddfdabbf7af7fef5f78046c14f8ca
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-encode-a-visual-to-an-image-file"></a><span data-ttu-id="6ec81-102">Procedura: codificare un oggetto Visual in un file di immagine</span><span class="sxs-lookup"><span data-stu-id="6ec81-102">How to: Encode a Visual to an Image File</span></span>
<span data-ttu-id="6ec81-103">In questo esempio viene illustrato come codificare un <xref:System.Windows.Media.Visual> oggetto in un file di immagine utilizzando un <xref:System.Windows.Media.Imaging.RenderTargetBitmap> e <xref:System.Windows.Media.Imaging.PngBitmapEncoder>.</span><span class="sxs-lookup"><span data-stu-id="6ec81-103">This example demonstrates how to encode a <xref:System.Windows.Media.Visual> object into an image file using a <xref:System.Windows.Media.Imaging.RenderTargetBitmap> and a <xref:System.Windows.Media.Imaging.PngBitmapEncoder>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6ec81-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="6ec81-104">Example</span></span>  
 <span data-ttu-id="6ec81-105">Il <xref:System.Windows.Media.DrawingVisual> viene creato utilizzando un <xref:System.Windows.Media.Imaging.BitmapImage> e <xref:System.Windows.Media.FormattedText> che viene eseguito il rendering di un <xref:System.Windows.Media.Imaging.RenderTargetBitmap>.</span><span class="sxs-lookup"><span data-stu-id="6ec81-105">The <xref:System.Windows.Media.DrawingVisual> is created using a <xref:System.Windows.Media.Imaging.BitmapImage> and <xref:System.Windows.Media.FormattedText> which is rendered to a <xref:System.Windows.Media.Imaging.RenderTargetBitmap>.</span></span> <span data-ttu-id="6ec81-106">La bitmap viene eseguito il rendering viene quindi utilizzata per creare un <xref:System.Windows.Media.Imaging.BitmapFrame> che viene aggiunto il <xref:System.Windows.Media.Imaging.PngBitmapEncoder> per creare un nuovo [!INCLUDE[TLA#tla_png](../../../../includes/tlasharptla-png-md.md)] file.</span><span class="sxs-lookup"><span data-stu-id="6ec81-106">The rendered bitmap is then used to create a <xref:System.Windows.Media.Imaging.BitmapFrame> which is added to the <xref:System.Windows.Media.Imaging.PngBitmapEncoder> to create a new [!INCLUDE[TLA#tla_png](../../../../includes/tlasharptla-png-md.md)] file.</span></span>  
  
 [!code-csharp[ImagingSnippetGallery_procedural_snip#RTBEncodeInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/CSharp/RenderTargetBitmapExample_Encode.cs#rtbencodeinline1)]
 [!code-vb[ImagingSnippetGallery_procedural_snip#RTBEncodeInline1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/VB/RenderTargetBitmapExample_Encode.vb#rtbencodeinline1)]  
  
 <span data-ttu-id="6ec81-107">Oggetto <xref:System.Windows.Media.Imaging.PngBitmapEncoder> è stato utilizzato in questo esempio, ma qualsiasi della classe derivata <xref:System.Windows.Media.Imaging.BitmapEncoder> oggetti avrebbe potuto utilizzati per creare il file di immagine.</span><span class="sxs-lookup"><span data-stu-id="6ec81-107">A <xref:System.Windows.Media.Imaging.PngBitmapEncoder> was used in this example but any of the derived <xref:System.Windows.Media.Imaging.BitmapEncoder> objects could have been used to create the image file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ec81-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6ec81-108">See Also</span></span>  
 <xref:System.Windows.Media.DrawingContext>  
 [<span data-ttu-id="6ec81-109">Cenni preliminari sulla creazione dell'immagine</span><span class="sxs-lookup"><span data-stu-id="6ec81-109">Imaging Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)  
 [<span data-ttu-id="6ec81-110">Cenni preliminari sugli oggetti Drawing</span><span class="sxs-lookup"><span data-stu-id="6ec81-110">Drawing Objects Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)  
 [<span data-ttu-id="6ec81-111">Uso degli oggetti DrawingVisual</span><span class="sxs-lookup"><span data-stu-id="6ec81-111">Using DrawingVisual Objects</span></span>](../../../../docs/framework/wpf/graphics-multimedia/using-drawingvisual-objects.md)
