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
ms.openlocfilehash: 193b6a14e404d32bb49d6e0ef3cbd513166bcce2
ms.sourcegitcommit: 43761fcee10aeefcf851ea81cea3f3c691420856
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/16/2019
ms.locfileid: "69545298"
---
# <a name="how-to-encode-a-visual-to-an-image-file"></a>Procedura: Codificare un oggetto visivo in un file di immagine
Questo esempio illustra come codificare un <xref:System.Windows.Media.Visual> oggetto in un file di immagine <xref:System.Windows.Media.Imaging.RenderTargetBitmap> usando e <xref:System.Windows.Media.Imaging.PngBitmapEncoder>.  
  
## <a name="example"></a>Esempio  
 Viene <xref:System.Windows.Media.DrawingVisual> creato utilizzando un oggetto <xref:System.Windows.Media.Imaging.BitmapImage> e <xref:System.Windows.Media.FormattedText> di cui viene eseguito il <xref:System.Windows.Media.Imaging.RenderTargetBitmap>rendering in un oggetto. La bitmap sottoposta a rendering viene quindi <xref:System.Windows.Media.Imaging.BitmapFrame> utilizzata per creare un oggetto <xref:System.Windows.Media.Imaging.PngBitmapEncoder> che viene aggiunto a per creare un nuovo file di Portable Network Graphics (png).  
  
 [!code-csharp[ImagingSnippetGallery_procedural_snip#RTBEncodeInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/CSharp/RenderTargetBitmapExample_Encode.cs#rtbencodeinline1)]
 [!code-vb[ImagingSnippetGallery_procedural_snip#RTBEncodeInline1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/VB/RenderTargetBitmapExample_Encode.vb#rtbencodeinline1)]  
  
 In <xref:System.Windows.Media.Imaging.PngBitmapEncoder> questo esempio è stato usato un oggetto, ma è <xref:System.Windows.Media.Imaging.BitmapEncoder> possibile che uno qualsiasi degli oggetti derivati sia stato usato per creare il file di immagine.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.DrawingContext>
- [Cenni preliminari sulla creazione dell'immagine](imaging-overview.md)
- [Cenni preliminari sugli oggetti Drawing](drawing-objects-overview.md)
- [Uso degli oggetti DrawingVisual](using-drawingvisual-objects.md)
