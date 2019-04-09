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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59096784"
---
# <a name="how-to-encode-a-visual-to-an-image-file"></a>Procedura: Codificare un oggetto visivo in un file di immagine
In questo esempio illustra come codificare un <xref:System.Windows.Media.Visual> oggetto in un file di immagine usando una <xref:System.Windows.Media.Imaging.RenderTargetBitmap> e un <xref:System.Windows.Media.Imaging.PngBitmapEncoder>.  
  
## <a name="example"></a>Esempio  
 Il <xref:System.Windows.Media.DrawingVisual> viene creato utilizzando una <xref:System.Windows.Media.Imaging.BitmapImage> e <xref:System.Windows.Media.FormattedText> che viene eseguito il rendering di un <xref:System.Windows.Media.Imaging.RenderTargetBitmap>. La bitmap viene eseguito il rendering viene quindi utilizzata per creare un <xref:System.Windows.Media.Imaging.BitmapFrame> che viene aggiunto per il <xref:System.Windows.Media.Imaging.PngBitmapEncoder> per creare un nuovo [!INCLUDE[TLA#tla_png](../../../../includes/tlasharptla-png-md.md)] file.  
  
 [!code-csharp[ImagingSnippetGallery_procedural_snip#RTBEncodeInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/CSharp/RenderTargetBitmapExample_Encode.cs#rtbencodeinline1)]
 [!code-vb[ImagingSnippetGallery_procedural_snip#RTBEncodeInline1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/VB/RenderTargetBitmapExample_Encode.vb#rtbencodeinline1)]  
  
 Oggetto <xref:System.Windows.Media.Imaging.PngBitmapEncoder> è stato usato in questo esempio ma dei derivato <xref:System.Windows.Media.Imaging.BitmapEncoder> oggetti avrebbe potuto avere utilizzati per creare il file di immagine.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.DrawingContext>
- [Cenni preliminari sulla creazione dell'immagine](imaging-overview.md)
- [Cenni preliminari sugli oggetti Drawing](drawing-objects-overview.md)
- [Utilizzo degli oggetti DrawingVisual](using-drawingvisual-objects.md)
