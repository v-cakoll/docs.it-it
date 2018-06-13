---
title: "Procedura: codificare e decodificare un'immagine PNG"
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
ms.openlocfilehash: a22b0eae323c12f99ad5447eb27423bc0e5f9277
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33558839"
---
# <a name="how-to-encode-and-decode-a-png-image"></a><span data-ttu-id="c5f13-102">Procedura: codificare e decodificare un'immagine PNG</span><span class="sxs-lookup"><span data-stu-id="c5f13-102">How to: Encode and Decode a PNG Image</span></span>
<span data-ttu-id="c5f13-103">Nell'esempio seguente viene illustrato come decodificare e codificare un [!INCLUDE[TLA#tla_png](../../../../includes/tlasharptla-png-md.md)] immagine usando la specifica <xref:System.Windows.Media.Imaging.PngBitmapDecoder> e <xref:System.Windows.Media.Imaging.PngBitmapEncoder> oggetti.</span><span class="sxs-lookup"><span data-stu-id="c5f13-103">The following examples show how to decode and encode a [!INCLUDE[TLA#tla_png](../../../../includes/tlasharptla-png-md.md)] image using the specific <xref:System.Windows.Media.Imaging.PngBitmapDecoder> and <xref:System.Windows.Media.Imaging.PngBitmapEncoder> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c5f13-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="c5f13-104">Example</span></span>  
 <span data-ttu-id="c5f13-105">In questo esempio viene illustrato come decodificare un [!INCLUDE[TLA2#tla_png](../../../../includes/tla2sharptla-png-md.md)] immagine usando un <xref:System.Windows.Media.Imaging.PngBitmapDecoder> da un <xref:System.IO.FileStream>.</span><span class="sxs-lookup"><span data-stu-id="c5f13-105">This example demonstrates how to decode a [!INCLUDE[TLA2#tla_png](../../../../includes/tla2sharptla-png-md.md)] image using a <xref:System.Windows.Media.Imaging.PngBitmapDecoder> from a <xref:System.IO.FileStream>.</span></span>  
  
 [!code-cpp[PngBitmapDecoderEncoder#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/PngBitmapDecoderEncoder/CPP/PngEncoderDecoder.cpp#1)]
 [!code-csharp[PngBitmapDecoderEncoder#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PngBitmapDecoderEncoder/CSharp/PngEncoderDecoder.cs#1)]
 [!code-vb[PngBitmapDecoderEncoder#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PngBitmapDecoderEncoder/VB/PngEncoderDecoder.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="c5f13-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="c5f13-106">Example</span></span>  
 <span data-ttu-id="c5f13-107">In questo esempio viene illustrato come codificare un <xref:System.Windows.Media.Imaging.BitmapSource> in un [!INCLUDE[TLA2#tla_png](../../../../includes/tla2sharptla-png-md.md)] immagine usando un <xref:System.Windows.Media.Imaging.PngBitmapEncoder>.</span><span class="sxs-lookup"><span data-stu-id="c5f13-107">This example demonstrates how to encode a <xref:System.Windows.Media.Imaging.BitmapSource> into a [!INCLUDE[TLA2#tla_png](../../../../includes/tla2sharptla-png-md.md)] image using a <xref:System.Windows.Media.Imaging.PngBitmapEncoder>.</span></span>  
  
 [!code-cpp[PngBitmapDecoderEncoder#4](../../../../samples/snippets/cpp/VS_Snippets_Wpf/PngBitmapDecoderEncoder/CPP/PngEncoderDecoder.cpp#4)]
 [!code-csharp[PngBitmapDecoderEncoder#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PngBitmapDecoderEncoder/CSharp/PngEncoderDecoder.cs#4)]
 [!code-vb[PngBitmapDecoderEncoder#4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PngBitmapDecoderEncoder/VB/PngEncoderDecoder.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="c5f13-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c5f13-108">See Also</span></span>  
 [<span data-ttu-id="c5f13-109">Cenni preliminari sulla creazione dell'immagine</span><span class="sxs-lookup"><span data-stu-id="c5f13-109">Imaging Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)
