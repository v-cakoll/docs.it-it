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
# <a name="how-to-encode-and-decode-a-gif-image"></a><span data-ttu-id="fa277-102">Procedura: Codificare e decodificare un'immagine GIF</span><span class="sxs-lookup"><span data-stu-id="fa277-102">How to: Encode and Decode a GIF Image</span></span>
<span data-ttu-id="fa277-103">Gli esempi seguenti illustrano come decodificare e codificare un'immagine di Graphics Interchange Format (gif) <xref:System.Windows.Media.Imaging.GifBitmapDecoder> usando <xref:System.Windows.Media.Imaging.GifBitmapEncoder> gli oggetti e specifici.</span><span class="sxs-lookup"><span data-stu-id="fa277-103">The following examples show how to decode and encode a Graphics Interchange Format (GIF) image using the specific <xref:System.Windows.Media.Imaging.GifBitmapDecoder> and <xref:System.Windows.Media.Imaging.GifBitmapEncoder> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fa277-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="fa277-104">Example</span></span>  
 <span data-ttu-id="fa277-105">Questo esempio illustra come decodificare un'immagine gif usando un <xref:System.Windows.Media.Imaging.GifBitmapDecoder> oggetto da <xref:System.IO.FileStream>un oggetto.</span><span class="sxs-lookup"><span data-stu-id="fa277-105">This example demonstrates how to decode a GIF image using a <xref:System.Windows.Media.Imaging.GifBitmapDecoder> from a <xref:System.IO.FileStream>.</span></span>  
  
 [!code-cpp[GifBitmapDecoderEncoder#1](~/samples/snippets/cpp/VS_Snippets_Wpf/GifBitmapDecoderEncoder/CPP/GifEncoderDecoder.cpp#1)]
 [!code-csharp[GifBitmapDecoderEncoder#1](~/samples/snippets/csharp/VS_Snippets_Wpf/GifBitmapDecoderEncoder/CSharp/GifEncoderDecoder.cs#1)]
 [!code-vb[GifBitmapDecoderEncoder#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GifBitmapDecoderEncoder/VB/GifEncoderDecoder.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="fa277-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="fa277-106">Example</span></span>  
 <span data-ttu-id="fa277-107">Questo esempio illustra come codificare un <xref:System.Windows.Media.Imaging.BitmapSource> oggetto in un'immagine gif usando <xref:System.Windows.Media.Imaging.GifBitmapEncoder>un oggetto.</span><span class="sxs-lookup"><span data-stu-id="fa277-107">This example demonstrates how to encode a <xref:System.Windows.Media.Imaging.BitmapSource> into a GIF image using a <xref:System.Windows.Media.Imaging.GifBitmapEncoder>.</span></span>  
  
 [!code-cpp[GifBitmapDecoderEncoder#4](~/samples/snippets/cpp/VS_Snippets_Wpf/GifBitmapDecoderEncoder/CPP/GifEncoderDecoder.cpp#4)]
 [!code-csharp[GifBitmapDecoderEncoder#4](~/samples/snippets/csharp/VS_Snippets_Wpf/GifBitmapDecoderEncoder/CSharp/GifEncoderDecoder.cs#4)]
 [!code-vb[GifBitmapDecoderEncoder#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GifBitmapDecoderEncoder/VB/GifEncoderDecoder.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="fa277-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fa277-108">See also</span></span>

- [<span data-ttu-id="fa277-109">Cenni preliminari sulla creazione dell'immagine</span><span class="sxs-lookup"><span data-stu-id="fa277-109">Imaging Overview</span></span>](imaging-overview.md)
