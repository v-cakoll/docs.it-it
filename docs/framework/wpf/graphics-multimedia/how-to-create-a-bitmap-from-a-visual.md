---
title: 'Procedura: Creare una bitmap da un oggetto visivo'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- bitmaps [WPF], rendering from visuals
- visuals [WPF], rendering to bitmaps
ms.assetid: 103fc7f5-7306-4026-9d61-2005e79959f3
ms.openlocfilehash: a622d99f7c477f8654526ed399f1eb37288682fe
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59189887"
---
# <a name="how-to-create-a-bitmap-from-a-visual"></a>Procedura: Creare una bitmap da un oggetto visivo
Questo esempio viene illustrato come creare una bitmap da un <xref:System.Windows.Media.Visual>. Oggetto <xref:System.Windows.Media.DrawingVisual> viene eseguito il rendering con <xref:System.Windows.Media.FormattedText>. Il <xref:System.Windows.Media.Visual> viene quindi eseguito il rendering di <xref:System.Windows.Media.Imaging.RenderTargetBitmap> crea una bitmap del testo specificato.  
  
## <a name="example"></a>Esempio  
 [!code-csharp[ImagingSnippetGallery_procedural_snip#CreateRTBImage](~/samples/snippets/csharp/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/CSharp/RenderTargetBitmapExample.cs#creatertbimage)]
 [!code-vb[ImagingSnippetGallery_procedural_snip#CreateRTBImage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/VB/RenderTargetBitmapExample.vb#creatertbimage)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.DrawingContext>
- [Cenni preliminari sulla creazione dell'immagine](imaging-overview.md)
- [Cenni preliminari sugli oggetti Drawing](drawing-objects-overview.md)
- [Utilizzo degli oggetti DrawingVisual](using-drawingvisual-objects.md)
