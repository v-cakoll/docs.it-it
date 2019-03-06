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
# <a name="how-to-improve-rendering-performance-by-caching-an-element"></a><span data-ttu-id="41ca7-102">Procedura: Migliorare le prestazioni di Rendering memorizzando nella cache un elemento</span><span class="sxs-lookup"><span data-stu-id="41ca7-102">How to: Improve Rendering Performance by Caching an Element</span></span>
<span data-ttu-id="41ca7-103">Usare la <xref:System.Windows.Media.BitmapCache> classe per migliorare le prestazioni di rendering di un oggetto complesso <xref:System.Windows.UIElement>.</span><span class="sxs-lookup"><span data-stu-id="41ca7-103">Use the <xref:System.Windows.Media.BitmapCache> class to improve rendering performance of a complex <xref:System.Windows.UIElement>.</span></span> <span data-ttu-id="41ca7-104">Per memorizzare nella cache un elemento, creare una nuova istanza di <xref:System.Windows.Media.BitmapCache> classi e assegnarla alla proprietà dell'elemento <xref:System.Windows.UIElement.CacheMode%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="41ca7-104">To cache an element, create a new instance of the <xref:System.Windows.Media.BitmapCache> class and assign it to the element's <xref:System.Windows.UIElement.CacheMode%2A> property.</span></span> <span data-ttu-id="41ca7-105">È possibile riutilizzare una <xref:System.Windows.Media.BitmapCache> in modo efficiente in un <xref:System.Windows.Media.BitmapCacheBrush>.</span><span class="sxs-lookup"><span data-stu-id="41ca7-105">You can reuse a <xref:System.Windows.Media.BitmapCache> efficiently in a <xref:System.Windows.Media.BitmapCacheBrush>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="41ca7-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="41ca7-106">Example</span></span>  
 <span data-ttu-id="41ca7-107">Esempio di codice seguente viene illustrato come creare un elemento complesso e lo memorizza nella cache come una bitmap, che migliora le prestazioni quando l'elemento viene animata.</span><span class="sxs-lookup"><span data-stu-id="41ca7-107">The following code example shows how to create a complex element and cache it as a bitmap, which improves performance when the element is animated.</span></span> <span data-ttu-id="41ca7-108">L'elemento è un'area di disegno che contiene le geometrie di forma con numero di vertici.</span><span class="sxs-lookup"><span data-stu-id="41ca7-108">The element is a canvas that holds shape geometries with many vertices.</span></span> <span data-ttu-id="41ca7-109">Oggetto <xref:System.Windows.Media.BitmapCache> con l'impostazione predefinita valori viene assegnato al <xref:System.Windows.UIElement.CacheMode%2A> dell'area di disegno, e un'animazione viene illustrata la scalabilità uniforme di bitmap memorizzata nella cache.</span><span class="sxs-lookup"><span data-stu-id="41ca7-109">A <xref:System.Windows.Media.BitmapCache> with default values is assigned to the <xref:System.Windows.UIElement.CacheMode%2A> of the canvas, and an animation shows the smooth scaling of the cached bitmap.</span></span>  
  
 [!code-xaml[System.Windows.Media.BitmapCache#_BitmapCacheXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/system.windows.media.bitmapcache/cs/window1.xaml#_bitmapcachexaml)]  
  
## <a name="see-also"></a><span data-ttu-id="41ca7-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="41ca7-110">See also</span></span>
- <xref:System.Windows.Media.BitmapCache>
- <xref:System.Windows.Media.BitmapCacheBrush>
- <xref:System.Windows.UIElement.CacheMode%2A>
- [<span data-ttu-id="41ca7-111">Procedura: Usare un elemento memorizzato nella cache come pennello</span><span class="sxs-lookup"><span data-stu-id="41ca7-111">How to: Use a Cached Element as a Brush</span></span>](how-to-use-a-cached-element-as-a-brush.md)
