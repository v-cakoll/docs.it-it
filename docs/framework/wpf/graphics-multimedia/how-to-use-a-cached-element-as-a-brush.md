---
title: 'Procedura: utilizzare un elemento memorizzato nella cache come pennello'
ms.date: 03/30/2017
helpviewer_keywords:
- BitmapCache [WPF], using
- cached element [WPF], use as a brush
- BitmapCacheBrush [WPF], using
- CacheMode [WPF], using
ms.assetid: d36e944a-866e-4baf-98c4-fd6a75f6fdd0
ms.openlocfilehash: c43c4ecbefe99d6e38766705378d85d92ecc5729
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-use-a-cached-element-as-a-brush"></a>Procedura: utilizzare un elemento memorizzato nella cache come pennello
Utilizzare la <xref:System.Windows.Media.BitmapCacheBrush> classe per riutilizzare un elemento memorizzato nella cache in modo efficiente. Per memorizzare nella cache un elemento, creare una nuova istanza di <xref:System.Windows.Media.BitmapCache> classe e assegnarla alla proprietà dell'elemento <xref:System.Windows.UIElement.CacheMode%2A> proprietà.  
  
## <a name="example"></a>Esempio  
 Esempio di codice seguente viene illustrato come riutilizzare un elemento memorizzato nella cache. L'elemento memorizzato nella cache è un <xref:System.Windows.Controls.Image> controllo che visualizza un'immagine di grandi dimensioni. Il <xref:System.Windows.Controls.Image> verrà memorizzato nella cache come bitmap utilizzando il <xref:System.Windows.Media.BitmapCache> classe e la cache viene riutilizzata assegnandola a un <xref:System.Windows.Media.BitmapCacheBrush>. Il pennello viene assegnato allo sfondo di venticinque pulsanti per visualizzare un efficiente riutilizzo.  
  
 [!code-xaml[System.Windows.Media.BitmapCacheBrush#_BitmapCacheBrushXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/system.windows.media.bitmapcachebrush/cs/window1.xaml#_bitmapcachebrushxaml)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Media.BitmapCache>  
 <xref:System.Windows.Media.BitmapCacheBrush>  
 <xref:System.Windows.UIElement.CacheMode%2A>  
 [Procedura: Migliorare le prestazioni di rendering memorizzando nella cache un elemento](../../../../docs/framework/wpf/graphics-multimedia/how-to-improve-rendering-performance-by-caching-an-element.md)
