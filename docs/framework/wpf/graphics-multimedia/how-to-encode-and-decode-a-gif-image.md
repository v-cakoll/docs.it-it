---
title: "Procedura: Codificare e decodificare un'immagine GIF"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- encoding GIF images [WPF]
- encoding image formats [WPF]
- decoding GIF images [WPF]
- decoding image formats [WPF]
- GIF decoding [WPF]
- GIF encoding [WPF]
ms.assetid: 9cdd9ec7-71eb-444b-b9e3-991958461163
ms.openlocfilehash: ec509a03d95e5f72af0b1f362e253799b07edc1f
ms.sourcegitcommit: 3eeea78f52ca771087a6736c23f74600cc662658
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/31/2019
ms.locfileid: "68671686"
---
# <a name="how-to-encode-and-decode-a-gif-image"></a>Procedura: Codificare e decodificare un'immagine GIF
Gli esempi seguenti illustrano come decodificare e codificare un'immagine di Graphics Interchange Format (gif) <xref:System.Windows.Media.Imaging.GifBitmapDecoder> usando <xref:System.Windows.Media.Imaging.GifBitmapEncoder> gli oggetti e specifici.  
  
## <a name="example"></a>Esempio  
 Questo esempio illustra come decodificare un'immagine gif usando un <xref:System.Windows.Media.Imaging.GifBitmapDecoder> oggetto da <xref:System.IO.FileStream>un oggetto.  
  
 [!code-cpp[GifBitmapDecoderEncoder#1](~/samples/snippets/cpp/VS_Snippets_Wpf/GifBitmapDecoderEncoder/CPP/GifEncoderDecoder.cpp#1)]
 [!code-csharp[GifBitmapDecoderEncoder#1](~/samples/snippets/csharp/VS_Snippets_Wpf/GifBitmapDecoderEncoder/CSharp/GifEncoderDecoder.cs#1)]
 [!code-vb[GifBitmapDecoderEncoder#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GifBitmapDecoderEncoder/VB/GifEncoderDecoder.vb#1)]  
  
## <a name="example"></a>Esempio  
 Questo esempio illustra come codificare un <xref:System.Windows.Media.Imaging.BitmapSource> oggetto in un'immagine gif usando <xref:System.Windows.Media.Imaging.GifBitmapEncoder>un oggetto.  
  
 [!code-cpp[GifBitmapDecoderEncoder#4](~/samples/snippets/cpp/VS_Snippets_Wpf/GifBitmapDecoderEncoder/CPP/GifEncoderDecoder.cpp#4)]
 [!code-csharp[GifBitmapDecoderEncoder#4](~/samples/snippets/csharp/VS_Snippets_Wpf/GifBitmapDecoderEncoder/CSharp/GifEncoderDecoder.cs#4)]
 [!code-vb[GifBitmapDecoderEncoder#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GifBitmapDecoderEncoder/VB/GifEncoderDecoder.vb#4)]  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sulla creazione dell'immagine](imaging-overview.md)
