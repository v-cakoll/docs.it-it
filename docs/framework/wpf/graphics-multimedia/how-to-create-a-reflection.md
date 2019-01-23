---
title: 'Procedura: Creare una reflection'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- creating reflections [WPF]
- brushes [WPF], creating reflections
- reflections [WPF], creating
ms.assetid: 4f017e16-ab80-43c7-98df-03b6bddbb203
ms.openlocfilehash: 0fae98966481003c7906f5cbb34afaea666d583d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54559034"
---
# <a name="how-to-create-a-reflection"></a><span data-ttu-id="6e809-102">Procedura: Creare una reflection</span><span class="sxs-lookup"><span data-stu-id="6e809-102">How to: Create a Reflection</span></span>
<span data-ttu-id="6e809-103">In questo esempio viene illustrato come utilizzare un <xref:System.Windows.Media.VisualBrush> per creare una reflection.</span><span class="sxs-lookup"><span data-stu-id="6e809-103">This example shows how to use a <xref:System.Windows.Media.VisualBrush> to create a reflection.</span></span> <span data-ttu-id="6e809-104">Poiché un <xref:System.Windows.Media.VisualBrush> può visualizzare un oggetto visivo esistente, è possibile usare questa funzionalità per produrre effetti visivi interessanti, ad esempio reflection e ingrandimento.</span><span class="sxs-lookup"><span data-stu-id="6e809-104">Because a <xref:System.Windows.Media.VisualBrush> can display an existing visual, you can use this capability to produce interesting visual effects, such as reflections and magnification.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6e809-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="6e809-105">Example</span></span>  
 <span data-ttu-id="6e809-106">L'esempio seguente usa un' <xref:System.Windows.Media.VisualBrush> per creare un riflesso di un <xref:System.Windows.Controls.Border> che contiene diversi elementi.</span><span class="sxs-lookup"><span data-stu-id="6e809-106">The following example uses a <xref:System.Windows.Media.VisualBrush> to create a reflection of a <xref:System.Windows.Controls.Border> that contains several elements.</span></span> <span data-ttu-id="6e809-107">L'immagine seguente illustra l'output generato dall'esempio.</span><span class="sxs-lookup"><span data-stu-id="6e809-107">The following illustration shows the output that this example produces.</span></span>  
  
 <span data-ttu-id="6e809-108">![Un oggetto visivo di riflessi](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-visualbrush-reflection-small.jpg "graphicsmm_visualbrush_reflection_small")</span><span class="sxs-lookup"><span data-stu-id="6e809-108">![A reflected Visual object](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-visualbrush-reflection-small.jpg "graphicsmm_visualbrush_reflection_small")</span></span>  
<span data-ttu-id="6e809-109">Oggetto Visual riflesso</span><span class="sxs-lookup"><span data-stu-id="6e809-109">A reflected Visual object</span></span>  
  
 [!code-csharp[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/visualbrush_markup_snip/CSharp/ReflectionExample.cs#graphicsmmvisualbrushreflectionexamplewholepage)]
 [!code-vb[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/visualbrush_markup_snip/visualbasic/reflectionexample.vb#graphicsmmvisualbrushreflectionexamplewholepage)]
 [!code-xaml[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/visualbrush_markup_snip/XAML/ReflectionExample.xaml#graphicsmmvisualbrushreflectionexamplewholepage)]  
  
 <span data-ttu-id="6e809-110">Per l'esempio completo, che include esempi che illustrano come ingrandire parti dello schermo e come creare reflection, vedere [esempio VisualBrush](https://go.microsoft.com/fwlink/?LinkID=160049).</span><span class="sxs-lookup"><span data-stu-id="6e809-110">For the complete sample, which includes examples that show how to magnify parts of the screen and how to create reflections, see [VisualBrush Sample](https://go.microsoft.com/fwlink/?LinkID=160049).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e809-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6e809-111">See also</span></span>
- <xref:System.Windows.Media.VisualBrush>
- [<span data-ttu-id="6e809-112">Disegnare con oggetti Image, Drawing e Visual</span><span class="sxs-lookup"><span data-stu-id="6e809-112">Painting with Images, Drawings, and Visuals</span></span>](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)
