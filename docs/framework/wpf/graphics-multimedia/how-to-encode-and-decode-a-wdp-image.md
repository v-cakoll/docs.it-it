---
title: "Procedura: Codificare e decodificare un'immagine WDP"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- WDP encoding [WPF]
- WDP decoding [WPF]
- encoding image formats [WPF]
- decoding WDP images [WPF]
- decoding image formats [WPF]
- encoding WDP images [WPF]
ms.assetid: 911777d1-516b-49db-a87b-b54e31b18532
ms.openlocfilehash: a9a65c0505b5fd6ad4aac31108a01d5f83f8fe91
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57356923"
---
# <a name="how-to-encode-and-decode-a-wdp-image"></a><span data-ttu-id="a89ae-102">Procedura: Codificare e decodificare un'immagine WDP</span><span class="sxs-lookup"><span data-stu-id="a89ae-102">How to: Encode and Decode a WDP Image</span></span>
<span data-ttu-id="a89ae-103">Gli esempi seguenti illustrano come decodificare e codificare un' [!INCLUDE[TLA#tla_wdp](../../../../includes/tlasharptla-wdp-md.md)] immagine usando le specifiche <xref:System.Windows.Media.Imaging.WmpBitmapDecoder> e <xref:System.Windows.Media.Imaging.WmpBitmapEncoder> oggetti.</span><span class="sxs-lookup"><span data-stu-id="a89ae-103">The following examples show how to decode and encode a [!INCLUDE[TLA#tla_wdp](../../../../includes/tlasharptla-wdp-md.md)] image using the specific <xref:System.Windows.Media.Imaging.WmpBitmapDecoder> and <xref:System.Windows.Media.Imaging.WmpBitmapEncoder> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a89ae-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="a89ae-104">Example</span></span>  
 <span data-ttu-id="a89ae-105">In questo esempio viene illustrato come decodificare un' [!INCLUDE[TLA2#tla_wdp](../../../../includes/tla2sharptla-wdp-md.md)] immagine usando una <xref:System.Windows.Media.Imaging.WmpBitmapDecoder> da un <xref:System.Uri>.</span><span class="sxs-lookup"><span data-stu-id="a89ae-105">This example demonstrates how to decode a [!INCLUDE[TLA2#tla_wdp](../../../../includes/tla2sharptla-wdp-md.md)] image using a <xref:System.Windows.Media.Imaging.WmpBitmapDecoder> from a <xref:System.Uri>.</span></span>  
  
 [!code-cpp[WdpBitmapDecoderEncoder#1](~/samples/snippets/cpp/VS_Snippets_Wpf/WdpBitmapDecoderEncoder/CPP/WDPEncoderDecoder.cpp#1)]
 [!code-csharp[WdpBitmapDecoderEncoder#1](~/samples/snippets/csharp/VS_Snippets_Wpf/WdpBitmapDecoderEncoder/CSharp/WDPEncoderDecoder.cs#1)]
 [!code-vb[WdpBitmapDecoderEncoder#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WdpBitmapDecoderEncoder/VB/WDPEncoderDecoder.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="a89ae-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="a89ae-106">Example</span></span>  
 <span data-ttu-id="a89ae-107">In questo esempio illustra come codificare un <xref:System.Windows.Media.Imaging.BitmapSource> in un [!INCLUDE[TLA2#tla_wdp](../../../../includes/tla2sharptla-wdp-md.md)] immagine usando un <xref:System.Windows.Media.Imaging.WmpBitmapEncoder>.</span><span class="sxs-lookup"><span data-stu-id="a89ae-107">This example demonstrates how to encode a <xref:System.Windows.Media.Imaging.BitmapSource> into a [!INCLUDE[TLA2#tla_wdp](../../../../includes/tla2sharptla-wdp-md.md)] image using a <xref:System.Windows.Media.Imaging.WmpBitmapEncoder>.</span></span>  
  
 [!code-cpp[WdpBitmapDecoderEncoder#4](~/samples/snippets/cpp/VS_Snippets_Wpf/WdpBitmapDecoderEncoder/CPP/WDPEncoderDecoder.cpp#4)]
 [!code-csharp[WdpBitmapDecoderEncoder#4](~/samples/snippets/csharp/VS_Snippets_Wpf/WdpBitmapDecoderEncoder/CSharp/WDPEncoderDecoder.cs#4)]
 [!code-vb[WdpBitmapDecoderEncoder#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WdpBitmapDecoderEncoder/VB/WDPEncoderDecoder.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="a89ae-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a89ae-108">See also</span></span>
- [<span data-ttu-id="a89ae-109">Cenni preliminari sulla creazione dell'immagine</span><span class="sxs-lookup"><span data-stu-id="a89ae-109">Imaging Overview</span></span>](imaging-overview.md)
