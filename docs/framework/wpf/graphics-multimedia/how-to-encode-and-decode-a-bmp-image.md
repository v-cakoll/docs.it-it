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
ms.openlocfilehash: b7d5ace8aead864cb69a9e696a3f1f925e232600
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59121901"
---
# <a name="how-to-encode-and-decode-a-bmp-image"></a><span data-ttu-id="5d77a-102">Procedura: Codificare e decodificare un'immagine BMP</span><span class="sxs-lookup"><span data-stu-id="5d77a-102">How to: Encode and Decode a BMP Image</span></span>
<span data-ttu-id="5d77a-103">Gli esempi seguenti illustrano come decodificare e codificare un' [!INCLUDE[TLA#tla_bmp](../../../../includes/tlasharptla-bmp-md.md)] immagine usando le specifiche <xref:System.Windows.Media.Imaging.BmpBitmapDecoder> e <xref:System.Windows.Media.Imaging.BmpBitmapEncoder> oggetti.</span><span class="sxs-lookup"><span data-stu-id="5d77a-103">The following examples show how to decode and encode a [!INCLUDE[TLA#tla_bmp](../../../../includes/tlasharptla-bmp-md.md)] image using the specific <xref:System.Windows.Media.Imaging.BmpBitmapDecoder> and <xref:System.Windows.Media.Imaging.BmpBitmapEncoder> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5d77a-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="5d77a-104">Example</span></span>  
 <span data-ttu-id="5d77a-105">In questo esempio viene illustrato come decodificare un' [!INCLUDE[TLA2#tla_bmp](../../../../includes/tla2sharptla-bmp-md.md)] immagine usando una <xref:System.Windows.Media.Imaging.BmpBitmapDecoder> da un <xref:System.Uri>.</span><span class="sxs-lookup"><span data-stu-id="5d77a-105">This example demonstrates how to decode a [!INCLUDE[TLA2#tla_bmp](../../../../includes/tla2sharptla-bmp-md.md)] image using a <xref:System.Windows.Media.Imaging.BmpBitmapDecoder> from a <xref:System.Uri>.</span></span>  
  
 [!code-cpp[BmpBitmapDecoderEncoder#5](~/samples/snippets/cpp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CPP/anotherfile.cpp#5)]
 [!code-csharp[BmpBitmapDecoderEncoder#5](~/samples/snippets/csharp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CSharp/BitmapFrame.cs#5)]
 [!code-vb[BmpBitmapDecoderEncoder#5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/VB/BitmapFrame.vb#5)]  
  
## <a name="example"></a><span data-ttu-id="5d77a-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="5d77a-106">Example</span></span>  
 <span data-ttu-id="5d77a-107">In questo esempio illustra come codificare un <xref:System.Windows.Media.Imaging.BitmapSource> in un [!INCLUDE[TLA2#tla_bmp](../../../../includes/tla2sharptla-bmp-md.md)] immagine usando un <xref:System.Windows.Media.Imaging.BmpBitmapEncoder>.</span><span class="sxs-lookup"><span data-stu-id="5d77a-107">This example demonstrates how to encode a <xref:System.Windows.Media.Imaging.BitmapSource> into a [!INCLUDE[TLA2#tla_bmp](../../../../includes/tla2sharptla-bmp-md.md)] image using a <xref:System.Windows.Media.Imaging.BmpBitmapEncoder>.</span></span>  
  
 [!code-cpp[BmpBitmapDecoderEncoder#4](~/samples/snippets/cpp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CPP/anotherfile.cpp#4)]
 [!code-csharp[BmpBitmapDecoderEncoder#4](~/samples/snippets/csharp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CSharp/BitmapFrame.cs#4)]
 [!code-vb[BmpBitmapDecoderEncoder#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/VB/BitmapFrame.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="5d77a-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5d77a-108">See also</span></span>

- [<span data-ttu-id="5d77a-109">Cenni preliminari sulla creazione dell'immagine</span><span class="sxs-lookup"><span data-stu-id="5d77a-109">Imaging Overview</span></span>](imaging-overview.md)
