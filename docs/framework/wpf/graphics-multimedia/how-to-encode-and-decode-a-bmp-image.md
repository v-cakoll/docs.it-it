---
title: "Procedura: codificare e decodificare un'immagine BMP"
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
ms.openlocfilehash: d8815a6f52a4033ec2d7dc19b0f97c5e65f1e2b4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33558846"
---
# <a name="how-to-encode-and-decode-a-bmp-image"></a><span data-ttu-id="2c40d-102">Procedura: codificare e decodificare un'immagine BMP</span><span class="sxs-lookup"><span data-stu-id="2c40d-102">How to: Encode and Decode a BMP Image</span></span>
<span data-ttu-id="2c40d-103">Nell'esempio seguente viene illustrato come decodificare e codificare un [!INCLUDE[TLA#tla_bmp](../../../../includes/tlasharptla-bmp-md.md)] immagine usando la specifica <xref:System.Windows.Media.Imaging.BmpBitmapDecoder> e <xref:System.Windows.Media.Imaging.BmpBitmapEncoder> oggetti.</span><span class="sxs-lookup"><span data-stu-id="2c40d-103">The following examples show how to decode and encode a [!INCLUDE[TLA#tla_bmp](../../../../includes/tlasharptla-bmp-md.md)] image using the specific <xref:System.Windows.Media.Imaging.BmpBitmapDecoder> and <xref:System.Windows.Media.Imaging.BmpBitmapEncoder> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2c40d-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="2c40d-104">Example</span></span>  
 <span data-ttu-id="2c40d-105">In questo esempio viene illustrato come decodificare un [!INCLUDE[TLA2#tla_bmp](../../../../includes/tla2sharptla-bmp-md.md)] immagine usando un <xref:System.Windows.Media.Imaging.BmpBitmapDecoder> da un <xref:System.Uri>.</span><span class="sxs-lookup"><span data-stu-id="2c40d-105">This example demonstrates how to decode a [!INCLUDE[TLA2#tla_bmp](../../../../includes/tla2sharptla-bmp-md.md)] image using a <xref:System.Windows.Media.Imaging.BmpBitmapDecoder> from a <xref:System.Uri>.</span></span>  
  
 [!code-cpp[BmpBitmapDecoderEncoder#5](../../../../samples/snippets/cpp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CPP/anotherfile.cpp#5)]
 [!code-csharp[BmpBitmapDecoderEncoder#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CSharp/BitmapFrame.cs#5)]
 [!code-vb[BmpBitmapDecoderEncoder#5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/VB/BitmapFrame.vb#5)]  
  
## <a name="example"></a><span data-ttu-id="2c40d-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="2c40d-106">Example</span></span>  
 <span data-ttu-id="2c40d-107">In questo esempio viene illustrato come codificare un <xref:System.Windows.Media.Imaging.BitmapSource> in un [!INCLUDE[TLA2#tla_bmp](../../../../includes/tla2sharptla-bmp-md.md)] immagine usando un <xref:System.Windows.Media.Imaging.BmpBitmapEncoder>.</span><span class="sxs-lookup"><span data-stu-id="2c40d-107">This example demonstrates how to encode a <xref:System.Windows.Media.Imaging.BitmapSource> into a [!INCLUDE[TLA2#tla_bmp](../../../../includes/tla2sharptla-bmp-md.md)] image using a <xref:System.Windows.Media.Imaging.BmpBitmapEncoder>.</span></span>  
  
 [!code-cpp[BmpBitmapDecoderEncoder#4](../../../../samples/snippets/cpp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CPP/anotherfile.cpp#4)]
 [!code-csharp[BmpBitmapDecoderEncoder#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CSharp/BitmapFrame.cs#4)]
 [!code-vb[BmpBitmapDecoderEncoder#4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/VB/BitmapFrame.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="2c40d-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2c40d-108">See Also</span></span>  
 [<span data-ttu-id="2c40d-109">Cenni preliminari sulla creazione dell'immagine</span><span class="sxs-lookup"><span data-stu-id="2c40d-109">Imaging Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)
