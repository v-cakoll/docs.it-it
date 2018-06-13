---
title: 'Procedura: migliorare le prestazioni di rendering memorizzando nella cache un elemento'
ms.date: 03/30/2017
helpviewer_keywords:
- rendering performance [WPF], caching an element
- BitmapCache [WPF], improving rendering performance
- CacheMode [WPF], improving rendering performance
- performance [WPF], caching an element
- UIElement [WPF], caching
ms.assetid: 4739c1fc-60ba-4c46-aba6-f6c1a2688f19
ms.openlocfilehash: a92909c623db0c10e3434677b4275fa82b787fa7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33559298"
---
# <a name="how-to-improve-rendering-performance-by-caching-an-element"></a>Procedura: migliorare le prestazioni di rendering memorizzando nella cache un elemento
Utilizzare il <xref:System.Windows.Media.BitmapCache> classe per migliorare le prestazioni di rendering di un oggetto complesso <xref:System.Windows.UIElement>. Per memorizzare nella cache un elemento, creare una nuova istanza di <xref:System.Windows.Media.BitmapCache> classe e assegnarla alla proprietà dell'elemento <xref:System.Windows.UIElement.CacheMode%2A> proprietà. È possibile riutilizzare un <xref:System.Windows.Media.BitmapCache> in modo efficiente in un <xref:System.Windows.Media.BitmapCacheBrush>.  
  
## <a name="example"></a>Esempio  
 Esempio di codice seguente viene illustrato come creare un elemento complesso e memorizzarlo nella cache come una bitmap, che migliora le prestazioni quando l'elemento viene animata. L'elemento è un'area di disegno che contiene le geometrie di forma con una quantità eccessiva di vertici. Oggetto <xref:System.Windows.Media.BitmapCache> predefinito viene assegnato valori al <xref:System.Windows.UIElement.CacheMode%2A> dell'area di disegno, e un'animazione viene illustrato il ridimensionamento uniforme della bitmap memorizzata nella cache.  
  
 [!code-xaml[System.Windows.Media.BitmapCache#_BitmapCacheXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/system.windows.media.bitmapcache/cs/window1.xaml#_bitmapcachexaml)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Media.BitmapCache>  
 <xref:System.Windows.Media.BitmapCacheBrush>  
 <xref:System.Windows.UIElement.CacheMode%2A>  
 [Procedura: Usare un elemento memorizzato nella cache come pennello](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-a-cached-element-as-a-brush.md)
