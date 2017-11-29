---
title: 'Procedura: codificare e decodificare un''immagine GIF'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f7832e4197ef5c3a764da265a393b654db013876
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-encode-and-decode-a-gif-image"></a><span data-ttu-id="eed07-102">Procedura: codificare e decodificare un'immagine GIF</span><span class="sxs-lookup"><span data-stu-id="eed07-102">How to: Encode and Decode a GIF Image</span></span>
<span data-ttu-id="eed07-103">Nell'esempio seguente viene illustrato come decodificare e codificare un [!INCLUDE[TLA#tla_gif](../../../../includes/tlasharptla-gif-md.md)] immagine usando la specifica <xref:System.Windows.Media.Imaging.GifBitmapDecoder> e <xref:System.Windows.Media.Imaging.GifBitmapEncoder> oggetti.</span><span class="sxs-lookup"><span data-stu-id="eed07-103">The following examples show how to decode and encode a [!INCLUDE[TLA#tla_gif](../../../../includes/tlasharptla-gif-md.md)] image using the specific <xref:System.Windows.Media.Imaging.GifBitmapDecoder> and <xref:System.Windows.Media.Imaging.GifBitmapEncoder> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eed07-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="eed07-104">Example</span></span>  
 <span data-ttu-id="eed07-105">In questo esempio viene illustrato come decodificare un [!INCLUDE[TLA2#tla_gif](../../../../includes/tla2sharptla-gif-md.md)] immagine usando un <xref:System.Windows.Media.Imaging.GifBitmapDecoder> da un <xref:System.IO.FileStream>.</span><span class="sxs-lookup"><span data-stu-id="eed07-105">This example demonstrates how to decode a [!INCLUDE[TLA2#tla_gif](../../../../includes/tla2sharptla-gif-md.md)] image using a <xref:System.Windows.Media.Imaging.GifBitmapDecoder> from a <xref:System.IO.FileStream>.</span></span>  
  
 [!code-cpp[GifBitmapDecoderEncoder#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/GifBitmapDecoderEncoder/CPP/GifEncoderDecoder.cpp#1)]
 [!code-csharp[GifBitmapDecoderEncoder#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GifBitmapDecoderEncoder/CSharp/GifEncoderDecoder.cs#1)]
 [!code-vb[GifBitmapDecoderEncoder#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GifBitmapDecoderEncoder/VB/GifEncoderDecoder.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="eed07-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="eed07-106">Example</span></span>  
 <span data-ttu-id="eed07-107">In questo esempio viene illustrato come codificare un <xref:System.Windows.Media.Imaging.BitmapSource> in un [!INCLUDE[TLA2#tla_gif](../../../../includes/tla2sharptla-gif-md.md)] immagine usando un <xref:System.Windows.Media.Imaging.GifBitmapEncoder>.</span><span class="sxs-lookup"><span data-stu-id="eed07-107">This example demonstrates how to encode a <xref:System.Windows.Media.Imaging.BitmapSource> into a [!INCLUDE[TLA2#tla_gif](../../../../includes/tla2sharptla-gif-md.md)] image using a <xref:System.Windows.Media.Imaging.GifBitmapEncoder>.</span></span>  
  
 [!code-cpp[GifBitmapDecoderEncoder#4](../../../../samples/snippets/cpp/VS_Snippets_Wpf/GifBitmapDecoderEncoder/CPP/GifEncoderDecoder.cpp#4)]
 [!code-csharp[GifBitmapDecoderEncoder#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GifBitmapDecoderEncoder/CSharp/GifEncoderDecoder.cs#4)]
 [!code-vb[GifBitmapDecoderEncoder#4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GifBitmapDecoderEncoder/VB/GifEncoderDecoder.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="eed07-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="eed07-108">See Also</span></span>  
 [<span data-ttu-id="eed07-109">Cenni preliminari sulla creazione dell'immagine</span><span class="sxs-lookup"><span data-stu-id="eed07-109">Imaging Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)
