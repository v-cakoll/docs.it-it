---
title: 'Procedura: Migliorare le prestazioni di Rendering memorizzando nella cache un elemento'
ms.date: 03/30/2017
helpviewer_keywords:
- rendering performance [WPF], caching an element
- BitmapCache [WPF], improving rendering performance
- CacheMode [WPF], improving rendering performance
- performance [WPF], caching an element
- UIElement [WPF], caching
ms.assetid: 4739c1fc-60ba-4c46-aba6-f6c1a2688f19
ms.openlocfilehash: b5e39541fdf031b19e9e74483c0de94295e788d7
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57375225"
---
# <a name="how-to-improve-rendering-performance-by-caching-an-element"></a>Procedura: Migliorare le prestazioni di Rendering memorizzando nella cache un elemento
Usare la <xref:System.Windows.Media.BitmapCache> classe per migliorare le prestazioni di rendering di un oggetto complesso <xref:System.Windows.UIElement>. Per memorizzare nella cache un elemento, creare una nuova istanza di <xref:System.Windows.Media.BitmapCache> classi e assegnarla alla proprietà dell'elemento <xref:System.Windows.UIElement.CacheMode%2A> proprietà. È possibile riutilizzare una <xref:System.Windows.Media.BitmapCache> in modo efficiente in un <xref:System.Windows.Media.BitmapCacheBrush>.  
  
## <a name="example"></a>Esempio  
 Esempio di codice seguente viene illustrato come creare un elemento complesso e lo memorizza nella cache come una bitmap, che migliora le prestazioni quando l'elemento viene animata. L'elemento è un'area di disegno che contiene le geometrie di forma con numero di vertici. Oggetto <xref:System.Windows.Media.BitmapCache> con l'impostazione predefinita valori viene assegnato al <xref:System.Windows.UIElement.CacheMode%2A> dell'area di disegno, e un'animazione viene illustrata la scalabilità uniforme di bitmap memorizzata nella cache.  
  
 [!code-xaml[System.Windows.Media.BitmapCache#_BitmapCacheXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/system.windows.media.bitmapcache/cs/window1.xaml#_bitmapcachexaml)]  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.Media.BitmapCache>
- <xref:System.Windows.Media.BitmapCacheBrush>
- <xref:System.Windows.UIElement.CacheMode%2A>
- [Procedura: Usare un elemento memorizzato nella cache come pennello](how-to-use-a-cached-element-as-a-brush.md)
