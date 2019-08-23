---
title: "Procedura: Creare e usare un'area di disegno"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], Canvas
- Canvas control [WPF], creating
- Canvas control [WPF], using
ms.assetid: 420b9487-9a15-477c-9489-a22a4dec7779
ms.openlocfilehash: edef660b2da2f09e0a6edbc0a87f0d1f26eb03da
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964226"
---
# <a name="how-to-create-and-use-a-canvas"></a><span data-ttu-id="ff87e-102">Procedura: Creare e usare un'area di disegno</span><span class="sxs-lookup"><span data-stu-id="ff87e-102">How to: Create and Use a Canvas</span></span>
<span data-ttu-id="ff87e-103">In questo esempio viene illustrato come creare e utilizzare un'istanza <xref:System.Windows.Controls.Canvas>di.</span><span class="sxs-lookup"><span data-stu-id="ff87e-103">This example shows how to create and use an instance of <xref:System.Windows.Controls.Canvas>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ff87e-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="ff87e-104">Example</span></span>  
 <span data-ttu-id="ff87e-105">Nell'esempio seguente vengono posizionati in <xref:System.Windows.Controls.TextBlock> modo esplicito due <xref:System.Windows.Controls.Canvas.SetTop%2A> elementi <xref:System.Windows.Controls.Canvas.SetLeft%2A> usando i <xref:System.Windows.Controls.Canvas>metodi e di.</span><span class="sxs-lookup"><span data-stu-id="ff87e-105">The following example explicitly positions two <xref:System.Windows.Controls.TextBlock> elements by using the <xref:System.Windows.Controls.Canvas.SetTop%2A> and <xref:System.Windows.Controls.Canvas.SetLeft%2A> methods of <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="ff87e-106">Nell'esempio viene inoltre assegnato un <xref:System.Windows.Controls.Control.Background%2A> `LightSteelBlue` colore a <xref:System.Windows.Controls.Canvas>.</span><span class="sxs-lookup"><span data-stu-id="ff87e-106">The example also assigns a <xref:System.Windows.Controls.Control.Background%2A> color of `LightSteelBlue` to the <xref:System.Windows.Controls.Canvas>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ff87e-107">Quando si utilizza [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] per posizionare <xref:System.Windows.Controls.TextBlock> gli elementi, utilizzare <xref:System.Windows.Controls.Canvas.Top%2A> le <xref:System.Windows.Controls.Canvas.Left%2A> proprietà e.</span><span class="sxs-lookup"><span data-stu-id="ff87e-107">When you use [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] to position <xref:System.Windows.Controls.TextBlock> elements, use the <xref:System.Windows.Controls.Canvas.Top%2A> and <xref:System.Windows.Controls.Canvas.Left%2A> properties.</span></span>  
  
 [!code-csharp[CanvasCode#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CanvasCode/CSharp/Canvas_Code.cs#1)]
 [!code-vb[CanvasCode#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CanvasCode/VisualBasic/canvas_vb.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="ff87e-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ff87e-108">See also</span></span>

- <xref:System.Windows.Controls.Canvas>
- <xref:System.Windows.Controls.TextBlock>
- <xref:System.Windows.Controls.Canvas.SetTop%2A>
- <xref:System.Windows.Controls.Canvas.SetLeft%2A>
- <xref:System.Windows.Controls.Canvas.Top%2A>
- <xref:System.Windows.Controls.Canvas.Left%2A>
- [<span data-ttu-id="ff87e-109">Cenni preliminari sugli elementi Panel</span><span class="sxs-lookup"><span data-stu-id="ff87e-109">Panels Overview</span></span>](panels-overview.md)
- [<span data-ttu-id="ff87e-110">Procedure relative alle proprietà</span><span class="sxs-lookup"><span data-stu-id="ff87e-110">How-to Topics</span></span>](canvas-how-to-topics.md)
