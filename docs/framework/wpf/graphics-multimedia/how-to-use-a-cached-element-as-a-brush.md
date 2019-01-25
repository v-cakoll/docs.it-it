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
# <a name="how-to-use-a-cached-element-as-a-brush"></a><span data-ttu-id="e9b0e-102">Procedura: Usare un elemento memorizzato nella cache come pennello</span><span class="sxs-lookup"><span data-stu-id="e9b0e-102">How to: Use a Cached Element as a Brush</span></span>
<span data-ttu-id="e9b0e-103">Usare il <xref:System.Windows.Media.BitmapCacheBrush> classe riutilizzare un elemento memorizzato nella cache in modo efficiente.</span><span class="sxs-lookup"><span data-stu-id="e9b0e-103">Use the <xref:System.Windows.Media.BitmapCacheBrush> class to reuse a cached element efficiently.</span></span> <span data-ttu-id="e9b0e-104">Per memorizzare nella cache un elemento, creare una nuova istanza di <xref:System.Windows.Media.BitmapCache> classi e assegnarla alla proprietà dell'elemento <xref:System.Windows.UIElement.CacheMode%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="e9b0e-104">To cache an element, create a new instance of the <xref:System.Windows.Media.BitmapCache> class and assign it to the element's <xref:System.Windows.UIElement.CacheMode%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e9b0e-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="e9b0e-105">Example</span></span>  
 <span data-ttu-id="e9b0e-106">Esempio di codice seguente mostra come riutilizzare un elemento memorizzato nella cache.</span><span class="sxs-lookup"><span data-stu-id="e9b0e-106">The following code example shows how to reuse a cached element.</span></span> <span data-ttu-id="e9b0e-107">L'elemento memorizzato nella cache è un <xref:System.Windows.Controls.Image> controllo che visualizza un'immagine di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="e9b0e-107">The cached element is an <xref:System.Windows.Controls.Image> control that displays a large image.</span></span> <span data-ttu-id="e9b0e-108">Il <xref:System.Windows.Controls.Image> viene memorizzata nella cache di controllo come bitmap tramite il <xref:System.Windows.Media.BitmapCache> classe e la cache viene riutilizzato assegnandolo a un <xref:System.Windows.Media.BitmapCacheBrush>.</span><span class="sxs-lookup"><span data-stu-id="e9b0e-108">The <xref:System.Windows.Controls.Image> control is cached as a bitmap by using the <xref:System.Windows.Media.BitmapCache> class, and the cache is reused by assigning it to a <xref:System.Windows.Media.BitmapCacheBrush>.</span></span> <span data-ttu-id="e9b0e-109">Viene assegnato il pennello per lo sfondo dei pulsanti e venticinque per mostrare un efficiente riutilizzo.</span><span class="sxs-lookup"><span data-stu-id="e9b0e-109">The brush is assigned to the background of twenty-five buttons to show efficient reuse.</span></span>  
  
 [!code-xaml[System.Windows.Media.BitmapCacheBrush#_BitmapCacheBrushXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/system.windows.media.bitmapcachebrush/cs/window1.xaml#_bitmapcachebrushxaml)]  
  
## <a name="see-also"></a><span data-ttu-id="e9b0e-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e9b0e-110">See also</span></span>
- <xref:System.Windows.Media.BitmapCache>
- <xref:System.Windows.Media.BitmapCacheBrush>
- <xref:System.Windows.UIElement.CacheMode%2A>
- [<span data-ttu-id="e9b0e-111">Procedura: Migliorare le prestazioni di Rendering memorizzando nella cache un elemento</span><span class="sxs-lookup"><span data-stu-id="e9b0e-111">How to: Improve Rendering Performance by Caching an Element</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-improve-rendering-performance-by-caching-an-element.md)
