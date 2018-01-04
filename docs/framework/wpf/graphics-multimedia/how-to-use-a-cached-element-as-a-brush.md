---
title: 'Procedura: utilizzare un elemento memorizzato nella cache come pennello'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BitmapCache [WPF], using
- cached element [WPF], use as a brush
- BitmapCacheBrush [WPF], using
- CacheMode [WPF], using
ms.assetid: d36e944a-866e-4baf-98c4-fd6a75f6fdd0
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f463c15855e267a4c246625a8d06e627852f48a9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
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
