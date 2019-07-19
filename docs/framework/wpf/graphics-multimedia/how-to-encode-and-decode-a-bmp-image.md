---
title: "Procedura: Codificare e decodificare un'immagine BMP"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- encoding BMP images [WPF]
- BMP encoding [WPF]
- decoding BMP images [WPF]
- encoding image formats [WPF]
- BMP decoding [WPF]
- decoding image formats [WPF]
ms.assetid: feb5ef27-28ac-40ab-bfc2-e0456990d32c
ms.openlocfilehash: 7d3520a1b1913fe68fedb0ea9d76cc138ed661c4
ms.sourcegitcommit: 09d699aca28ae9723399bbd9d3d44aa0cbd3848d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/19/2019
ms.locfileid: "68331722"
---
# <a name="how-to-encode-and-decode-a-bmp-image"></a>Procedura: Codificare e decodificare un'immagine BMP
Negli esempi seguenti viene illustrato come decodificare e codificare un'immagine bitmap (BMP) utilizzando <xref:System.Windows.Media.Imaging.BmpBitmapDecoder> gli <xref:System.Windows.Media.Imaging.BmpBitmapEncoder> oggetti e specifici.  
  
## <a name="example"></a>Esempio  
 Questo esempio illustra come decodificare un'immagine bmp usando un <xref:System.Windows.Media.Imaging.BmpBitmapDecoder> oggetto da <xref:System.Uri>un oggetto.  
  
 [!code-cpp[BmpBitmapDecoderEncoder#5](~/samples/snippets/cpp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CPP/anotherfile.cpp#5)]
 [!code-csharp[BmpBitmapDecoderEncoder#5](~/samples/snippets/csharp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CSharp/BitmapFrame.cs#5)]
 [!code-vb[BmpBitmapDecoderEncoder#5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/VB/BitmapFrame.vb#5)]  
  
## <a name="example"></a>Esempio  
 Questo esempio illustra come codificare un <xref:System.Windows.Media.Imaging.BitmapSource> oggetto in un'immagine bmp usando <xref:System.Windows.Media.Imaging.BmpBitmapEncoder>un oggetto.  
  
 [!code-cpp[BmpBitmapDecoderEncoder#4](~/samples/snippets/cpp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CPP/anotherfile.cpp#4)]
 [!code-csharp[BmpBitmapDecoderEncoder#4](~/samples/snippets/csharp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CSharp/BitmapFrame.cs#4)]
 [!code-vb[BmpBitmapDecoderEncoder#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/VB/BitmapFrame.vb#4)]  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sulla creazione dell'immagine](imaging-overview.md)
