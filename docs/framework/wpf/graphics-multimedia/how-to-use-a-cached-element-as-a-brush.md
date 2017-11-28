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
ms.openlocfilehash: 4d0f0c60e9df6a1ec816b1f9cf5769c93b382ae5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-a-cached-element-as-a-brush"></a><span data-ttu-id="78317-102">Procedura: utilizzare un elemento memorizzato nella cache come pennello</span><span class="sxs-lookup"><span data-stu-id="78317-102">How to: Use a Cached Element as a Brush</span></span>
<span data-ttu-id="78317-103">Utilizzare la <xref:System.Windows.Media.BitmapCacheBrush> classe per riutilizzare un elemento memorizzato nella cache in modo efficiente.</span><span class="sxs-lookup"><span data-stu-id="78317-103">Use the <xref:System.Windows.Media.BitmapCacheBrush> class to reuse a cached element efficiently.</span></span> <span data-ttu-id="78317-104">Per memorizzare nella cache un elemento, creare una nuova istanza di <xref:System.Windows.Media.BitmapCache> classe e assegnarla alla proprietà dell'elemento <xref:System.Windows.UIElement.CacheMode%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="78317-104">To cache an element, create a new instance of the <xref:System.Windows.Media.BitmapCache> class and assign it to the element's <xref:System.Windows.UIElement.CacheMode%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="78317-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="78317-105">Example</span></span>  
 <span data-ttu-id="78317-106">Esempio di codice seguente viene illustrato come riutilizzare un elemento memorizzato nella cache.</span><span class="sxs-lookup"><span data-stu-id="78317-106">The following code example shows how to reuse a cached element.</span></span> <span data-ttu-id="78317-107">L'elemento memorizzato nella cache è un <xref:System.Windows.Controls.Image> controllo che visualizza un'immagine di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="78317-107">The cached element is an <xref:System.Windows.Controls.Image> control that displays a large image.</span></span> <span data-ttu-id="78317-108">Il <xref:System.Windows.Controls.Image> verrà memorizzato nella cache come bitmap utilizzando il <xref:System.Windows.Media.BitmapCache> classe e la cache viene riutilizzata assegnandola a un <xref:System.Windows.Media.BitmapCacheBrush>.</span><span class="sxs-lookup"><span data-stu-id="78317-108">The <xref:System.Windows.Controls.Image> control is cached as a bitmap by using the <xref:System.Windows.Media.BitmapCache> class, and the cache is reused by assigning it to a <xref:System.Windows.Media.BitmapCacheBrush>.</span></span> <span data-ttu-id="78317-109">Il pennello viene assegnato allo sfondo di venticinque pulsanti per visualizzare un efficiente riutilizzo.</span><span class="sxs-lookup"><span data-stu-id="78317-109">The brush is assigned to the background of twenty-five buttons to show efficient reuse.</span></span>  
  
 [!code-xaml[System.Windows.Media.BitmapCacheBrush#_BitmapCacheBrushXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/system.windows.media.bitmapcachebrush/cs/window1.xaml#_bitmapcachebrushxaml)]  
  
## <a name="see-also"></a><span data-ttu-id="78317-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="78317-110">See Also</span></span>  
 <xref:System.Windows.Media.BitmapCache>  
 <xref:System.Windows.Media.BitmapCacheBrush>  
 <xref:System.Windows.UIElement.CacheMode%2A>  
 [<span data-ttu-id="78317-111">Procedura: Migliorare le prestazioni di rendering memorizzando nella cache un elemento</span><span class="sxs-lookup"><span data-stu-id="78317-111">How to: Improve Rendering Performance by Caching an Element</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-improve-rendering-performance-by-caching-an-element.md)
