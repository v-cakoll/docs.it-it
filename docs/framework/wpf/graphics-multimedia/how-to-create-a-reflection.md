---
title: 'Procedura: creare una reflection'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- creating reflections [WPF]
- brushes [WPF], creating reflections
- reflections [WPF], creating
ms.assetid: 4f017e16-ab80-43c7-98df-03b6bddbb203
ms.openlocfilehash: c791dbbe02faaba790c650d482db092702730fa6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33560576"
---
# <a name="how-to-create-a-reflection"></a><span data-ttu-id="0a43a-102">Procedura: creare una reflection</span><span class="sxs-lookup"><span data-stu-id="0a43a-102">How to: Create a Reflection</span></span>
<span data-ttu-id="0a43a-103">In questo esempio viene illustrato come utilizzare un <xref:System.Windows.Media.VisualBrush> per creare una reflection.</span><span class="sxs-lookup"><span data-stu-id="0a43a-103">This example shows how to use a <xref:System.Windows.Media.VisualBrush> to create a reflection.</span></span> <span data-ttu-id="0a43a-104">Poiché un <xref:System.Windows.Media.VisualBrush> può visualizzare un elemento visivo esistente, è possibile utilizzare questa funzionalità per produrre effetti visivi interessanti, ad esempio reflection e ingrandimento.</span><span class="sxs-lookup"><span data-stu-id="0a43a-104">Because a <xref:System.Windows.Media.VisualBrush> can display an existing visual, you can use this capability to produce interesting visual effects, such as reflections and magnification.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0a43a-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="0a43a-105">Example</span></span>  
 <span data-ttu-id="0a43a-106">Nell'esempio seguente viene utilizzato un <xref:System.Windows.Media.VisualBrush> per creare un riflesso di un <xref:System.Windows.Controls.Border> che contiene diversi elementi.</span><span class="sxs-lookup"><span data-stu-id="0a43a-106">The following example uses a <xref:System.Windows.Media.VisualBrush> to create a reflection of a <xref:System.Windows.Controls.Border> that contains several elements.</span></span> <span data-ttu-id="0a43a-107">L'immagine seguente illustra l'output generato dall'esempio.</span><span class="sxs-lookup"><span data-stu-id="0a43a-107">The following illustration shows the output that this example produces.</span></span>  
  
 <span data-ttu-id="0a43a-108">![Oggetto riflesse oggetto visivo](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-visualbrush-reflection-small.jpg "graphicsmm_visualbrush_reflection_small")</span><span class="sxs-lookup"><span data-stu-id="0a43a-108">![A reflected Visual object](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-visualbrush-reflection-small.jpg "graphicsmm_visualbrush_reflection_small")</span></span>  
<span data-ttu-id="0a43a-109">Oggetto Visual riflesso</span><span class="sxs-lookup"><span data-stu-id="0a43a-109">A reflected Visual object</span></span>  
  
 [!code-csharp[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/visualbrush_markup_snip/CSharp/ReflectionExample.cs#graphicsmmvisualbrushreflectionexamplewholepage)]
 [!code-vb[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/visualbrush_markup_snip/visualbasic/reflectionexample.vb#graphicsmmvisualbrushreflectionexamplewholepage)]
 [!code-xaml[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/visualbrush_markup_snip/XAML/ReflectionExample.xaml#graphicsmmvisualbrushreflectionexamplewholepage)]  
  
 <span data-ttu-id="0a43a-110">Per un esempio completo che include esempi che illustrano come ingrandire parti dello schermo e come creare i riflessi, vedere [esempio VisualBrush](http://go.microsoft.com/fwlink/?LinkID=160049).</span><span class="sxs-lookup"><span data-stu-id="0a43a-110">For the complete sample, which includes examples that show how to magnify parts of the screen and how to create reflections, see [VisualBrush Sample](http://go.microsoft.com/fwlink/?LinkID=160049).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a43a-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0a43a-111">See Also</span></span>  
 <xref:System.Windows.Media.VisualBrush>  
 [<span data-ttu-id="0a43a-112">Disegnare con oggetti Image, Drawing e Visual</span><span class="sxs-lookup"><span data-stu-id="0a43a-112">Painting with Images, Drawings, and Visuals</span></span>](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)
