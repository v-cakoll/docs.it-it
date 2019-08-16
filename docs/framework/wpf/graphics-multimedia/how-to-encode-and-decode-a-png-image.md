---
title: "Procedura: Codificare e decodificare un'immagine PNG"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- PNG encoding [WPF]
- decoding PNG images [WPF]
- PNG decoding [WPF]
- encoding image formats [WPF]
- decoding image formats [WPF]
- encoding PNG images [WPF]
ms.assetid: 3d31d186-af73-47f0-b5a7-c26ae46409a6
ms.openlocfilehash: 0a0a2f2625901f7ee32ba9fe70e71681a1b9ccd3
ms.sourcegitcommit: 43761fcee10aeefcf851ea81cea3f3c691420856
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/16/2019
ms.locfileid: "69545283"
---
# <a name="how-to-encode-and-decode-a-png-image"></a>Procedura: Codificare e decodificare un'immagine PNG
Gli esempi seguenti illustrano come decodificare e codificare un'immagine di Portable Network Graphics (png) <xref:System.Windows.Media.Imaging.PngBitmapDecoder> usando <xref:System.Windows.Media.Imaging.PngBitmapEncoder> gli oggetti e specifici.  
  
## <a name="example"></a>Esempio  
 Questo esempio illustra come decodificare un'immagine PNG usando un <xref:System.Windows.Media.Imaging.PngBitmapDecoder> oggetto da <xref:System.IO.FileStream>un oggetto.  
  
 [!code-cpp[PngBitmapDecoderEncoder#1](~/samples/snippets/cpp/VS_Snippets_Wpf/PngBitmapDecoderEncoder/CPP/PngEncoderDecoder.cpp#1)]
 [!code-csharp[PngBitmapDecoderEncoder#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PngBitmapDecoderEncoder/CSharp/PngEncoderDecoder.cs#1)]
 [!code-vb[PngBitmapDecoderEncoder#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PngBitmapDecoderEncoder/VB/PngEncoderDecoder.vb#1)]  
  
## <a name="example"></a>Esempio  
 Questo esempio illustra come codificare un <xref:System.Windows.Media.Imaging.BitmapSource> oggetto in un'immagine png <xref:System.Windows.Media.Imaging.PngBitmapEncoder>usando.  
  
 [!code-cpp[PngBitmapDecoderEncoder#4](~/samples/snippets/cpp/VS_Snippets_Wpf/PngBitmapDecoderEncoder/CPP/PngEncoderDecoder.cpp#4)]
 [!code-csharp[PngBitmapDecoderEncoder#4](~/samples/snippets/csharp/VS_Snippets_Wpf/PngBitmapDecoderEncoder/CSharp/PngEncoderDecoder.cs#4)]
 [!code-vb[PngBitmapDecoderEncoder#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PngBitmapDecoderEncoder/VB/PngEncoderDecoder.vb#4)]  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sulla creazione dell'immagine](imaging-overview.md)
