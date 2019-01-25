---
title: 'Procedura: Usare un elemento memorizzato nella cache come pennello'
ms.date: 03/30/2017
helpviewer_keywords:
- BitmapCache [WPF], using
- cached element [WPF], use as a brush
- BitmapCacheBrush [WPF], using
- CacheMode [WPF], using
ms.assetid: d36e944a-866e-4baf-98c4-fd6a75f6fdd0
ms.openlocfilehash: 7ff0e9eb131faaed3874995ee137126eac31f43d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54597931"
---
# <a name="how-to-use-a-cached-element-as-a-brush"></a>Procedura: Usare un elemento memorizzato nella cache come pennello
Usare il <xref:System.Windows.Media.BitmapCacheBrush> classe riutilizzare un elemento memorizzato nella cache in modo efficiente. Per memorizzare nella cache un elemento, creare una nuova istanza di <xref:System.Windows.Media.BitmapCache> classi e assegnarla alla proprietà dell'elemento <xref:System.Windows.UIElement.CacheMode%2A> proprietà.  
  
## <a name="example"></a>Esempio  
 Esempio di codice seguente mostra come riutilizzare un elemento memorizzato nella cache. L'elemento memorizzato nella cache è un <xref:System.Windows.Controls.Image> controllo che visualizza un'immagine di grandi dimensioni. Il <xref:System.Windows.Controls.Image> viene memorizzata nella cache di controllo come bitmap tramite il <xref:System.Windows.Media.BitmapCache> classe e la cache viene riutilizzato assegnandolo a un <xref:System.Windows.Media.BitmapCacheBrush>. Viene assegnato il pennello per lo sfondo dei pulsanti e venticinque per mostrare un efficiente riutilizzo.  
  
 [!code-xaml[System.Windows.Media.BitmapCacheBrush#_BitmapCacheBrushXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/system.windows.media.bitmapcachebrush/cs/window1.xaml#_bitmapcachebrushxaml)]  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.Media.BitmapCache>
- <xref:System.Windows.Media.BitmapCacheBrush>
- <xref:System.Windows.UIElement.CacheMode%2A>
- [Procedura: Migliorare le prestazioni di Rendering memorizzando nella cache un elemento](../../../../docs/framework/wpf/graphics-multimedia/how-to-improve-rendering-performance-by-caching-an-element.md)
