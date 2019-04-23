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
ms.openlocfilehash: b143106092235b42044d264189c135d2cd65426c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59153361"
---
# <a name="how-to-encode-and-decode-a-wdp-image"></a>Procedura: Codificare e decodificare un'immagine WDP
Gli esempi seguenti illustrano come decodificare e codificare un' [!INCLUDE[TLA#tla_wdp](../../../../includes/tlasharptla-wdp-md.md)] immagine usando le specifiche <xref:System.Windows.Media.Imaging.WmpBitmapDecoder> e <xref:System.Windows.Media.Imaging.WmpBitmapEncoder> oggetti.  
  
## <a name="example"></a>Esempio  
 In questo esempio viene illustrato come decodificare un' [!INCLUDE[TLA2#tla_wdp](../../../../includes/tla2sharptla-wdp-md.md)] immagine usando una <xref:System.Windows.Media.Imaging.WmpBitmapDecoder> da un <xref:System.Uri>.  
  
 [!code-cpp[WdpBitmapDecoderEncoder#1](~/samples/snippets/cpp/VS_Snippets_Wpf/WdpBitmapDecoderEncoder/CPP/WDPEncoderDecoder.cpp#1)]
 [!code-csharp[WdpBitmapDecoderEncoder#1](~/samples/snippets/csharp/VS_Snippets_Wpf/WdpBitmapDecoderEncoder/CSharp/WDPEncoderDecoder.cs#1)]
 [!code-vb[WdpBitmapDecoderEncoder#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WdpBitmapDecoderEncoder/VB/WDPEncoderDecoder.vb#1)]  
  
## <a name="example"></a>Esempio  
 In questo esempio illustra come codificare un <xref:System.Windows.Media.Imaging.BitmapSource> in un [!INCLUDE[TLA2#tla_wdp](../../../../includes/tla2sharptla-wdp-md.md)] immagine usando un <xref:System.Windows.Media.Imaging.WmpBitmapEncoder>.  
  
 [!code-cpp[WdpBitmapDecoderEncoder#4](~/samples/snippets/cpp/VS_Snippets_Wpf/WdpBitmapDecoderEncoder/CPP/WDPEncoderDecoder.cpp#4)]
 [!code-csharp[WdpBitmapDecoderEncoder#4](~/samples/snippets/csharp/VS_Snippets_Wpf/WdpBitmapDecoderEncoder/CSharp/WDPEncoderDecoder.cs#4)]
 [!code-vb[WdpBitmapDecoderEncoder#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WdpBitmapDecoderEncoder/VB/WDPEncoderDecoder.vb#4)]  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sulla creazione dell'immagine](imaging-overview.md)
