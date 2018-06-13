---
title: 'Procedura: creare un oggetto Bitmap da un oggetto Visual'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- bitmaps [WPF], rendering from visuals
- visuals [WPF], rendering to bitmaps
ms.assetid: 103fc7f5-7306-4026-9d61-2005e79959f3
ms.openlocfilehash: 4735474d00712598cb5e41fad289e8f568d83a48
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33559766"
---
# <a name="how-to-create-a-bitmap-from-a-visual"></a>Procedura: creare un oggetto Bitmap da un oggetto Visual
Questo esempio viene illustrato come creare una bitmap da un <xref:System.Windows.Media.Visual>. Oggetto <xref:System.Windows.Media.DrawingVisual> viene eseguito il rendering con <xref:System.Windows.Media.FormattedText>. Il <xref:System.Windows.Media.Visual> viene quindi eseguito il rendering di <xref:System.Windows.Media.Imaging.RenderTargetBitmap> la creazione di una bitmap del testo specificato.  
  
## <a name="example"></a>Esempio  
 [!code-csharp[ImagingSnippetGallery_procedural_snip#CreateRTBImage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/CSharp/RenderTargetBitmapExample.cs#creatertbimage)]
 [!code-vb[ImagingSnippetGallery_procedural_snip#CreateRTBImage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/VB/RenderTargetBitmapExample.vb#creatertbimage)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Media.DrawingContext>  
 [Cenni preliminari sulla creazione dell'immagine](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)  
 [Cenni preliminari sugli oggetti Drawing](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)  
 [Uso degli oggetti DrawingVisual](../../../../docs/framework/wpf/graphics-multimedia/using-drawingvisual-objects.md)
