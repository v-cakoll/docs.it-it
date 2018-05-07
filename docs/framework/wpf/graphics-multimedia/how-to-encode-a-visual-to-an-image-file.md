---
title: 'Procedura: codificare un oggetto Visual in un file di immagine'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- image files [WPF], encoding from visuals
- encoding image formats [WPF]
- visuals [WPF], encoding to an image file
ms.assetid: 2036385b-ea47-4d54-8027-5797f52c8149
ms.openlocfilehash: a9e847a46941c37efb735d5bfd13bde2dd74271c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-encode-a-visual-to-an-image-file"></a>Procedura: codificare un oggetto Visual in un file di immagine
In questo esempio viene illustrato come codificare un <xref:System.Windows.Media.Visual> oggetto in un file di immagine utilizzando un <xref:System.Windows.Media.Imaging.RenderTargetBitmap> e <xref:System.Windows.Media.Imaging.PngBitmapEncoder>.  
  
## <a name="example"></a>Esempio  
 Il <xref:System.Windows.Media.DrawingVisual> viene creato utilizzando un <xref:System.Windows.Media.Imaging.BitmapImage> e <xref:System.Windows.Media.FormattedText> che viene eseguito il rendering di un <xref:System.Windows.Media.Imaging.RenderTargetBitmap>. La bitmap viene eseguito il rendering viene quindi utilizzata per creare un <xref:System.Windows.Media.Imaging.BitmapFrame> che viene aggiunto il <xref:System.Windows.Media.Imaging.PngBitmapEncoder> per creare un nuovo [!INCLUDE[TLA#tla_png](../../../../includes/tlasharptla-png-md.md)] file.  
  
 [!code-csharp[ImagingSnippetGallery_procedural_snip#RTBEncodeInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/CSharp/RenderTargetBitmapExample_Encode.cs#rtbencodeinline1)]
 [!code-vb[ImagingSnippetGallery_procedural_snip#RTBEncodeInline1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/VB/RenderTargetBitmapExample_Encode.vb#rtbencodeinline1)]  
  
 Oggetto <xref:System.Windows.Media.Imaging.PngBitmapEncoder> è stato utilizzato in questo esempio, ma qualsiasi della classe derivata <xref:System.Windows.Media.Imaging.BitmapEncoder> oggetti avrebbe potuto utilizzati per creare il file di immagine.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Media.DrawingContext>  
 [Cenni preliminari sulla creazione dell'immagine](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)  
 [Cenni preliminari sugli oggetti Drawing](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)  
 [Uso degli oggetti DrawingVisual](../../../../docs/framework/wpf/graphics-multimedia/using-drawingvisual-objects.md)
