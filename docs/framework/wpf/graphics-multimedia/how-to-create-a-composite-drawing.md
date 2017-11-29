---
title: 'Procedura: creare un disegno composto'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- drawings [WPF], composite
- composite drawings [WPF]
- graphics [WPF], composite drawings
ms.assetid: 066eb0ab-5f0e-439d-85c6-dca60af269fc
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7789f9aa94db32d3dc61ccf01ef9ddfe1e777a37
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-composite-drawing"></a><span data-ttu-id="e5051-102">Procedura: creare un disegno composto</span><span class="sxs-lookup"><span data-stu-id="e5051-102">How to: Create a Composite Drawing</span></span>
<span data-ttu-id="e5051-103">In questo esempio viene illustrato come utilizzare un <xref:System.Windows.Media.DrawingGroup> per creare disegni complessi combinando più <xref:System.Windows.Media.Drawing> oggetti in un unico disegno composto.</span><span class="sxs-lookup"><span data-stu-id="e5051-103">This example shows how to use a <xref:System.Windows.Media.DrawingGroup> to create complex drawings by combining multiple <xref:System.Windows.Media.Drawing> objects into a single composite drawing.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e5051-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="e5051-104">Example</span></span>  
 <span data-ttu-id="e5051-105">Nell'esempio seguente viene utilizzato un <xref:System.Windows.Media.DrawingGroup> per creare un disegno composto dal <xref:System.Windows.Media.GeometryDrawing> e <xref:System.Windows.Media.ImageDrawing> oggetti.</span><span class="sxs-lookup"><span data-stu-id="e5051-105">The following example uses a <xref:System.Windows.Media.DrawingGroup> to create a composite drawing from the <xref:System.Windows.Media.GeometryDrawing> and <xref:System.Windows.Media.ImageDrawing> objects.</span></span> <span data-ttu-id="e5051-106">L'immagine seguente illustra l'output generato dall'esempio.</span><span class="sxs-lookup"><span data-stu-id="e5051-106">The following illustration shows the output that this example produces.</span></span>  
  
 <span data-ttu-id="e5051-107">![DrawingGroup con più disegni](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-simple.jpg "graphicsmm_simple")</span><span class="sxs-lookup"><span data-stu-id="e5051-107">![A DrawingGroup with multiple drawings](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-simple.jpg "graphicsmm_simple")</span></span>  
<span data-ttu-id="e5051-108">Un disegno composto creato utilizzando DrawingGroup</span><span class="sxs-lookup"><span data-stu-id="e5051-108">A composite drawing that is created by using DrawingGroup</span></span>  
  
 <span data-ttu-id="e5051-109">Si noti il bordo grigio, che indica i limiti del disegno.</span><span class="sxs-lookup"><span data-stu-id="e5051-109">Note the gray border, which shows the bounds of the drawing.</span></span>  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMSimpleDrawingGroupExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingGroupExample.cs#graphicsmmsimpledrawinggroupexample)]
 [!code-xaml[DrawingMiscSnippets_snip#GraphicsMMSimpleDrawingGroupExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingGroupExample.xaml#graphicsmmsimpledrawinggroupexample)]  
  
 <span data-ttu-id="e5051-110">È possibile utilizzare un <xref:System.Windows.Media.DrawingGroup> per applicare un <xref:System.Windows.Media.DrawingGroup.Transform%2A>, <xref:System.Windows.Media.DrawingGroup.Opacity%2A> impostazione <xref:System.Windows.Media.DrawingGroup.OpacityMask%2A>, <xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A>, <xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>, o <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A> di disegni che contiene.</span><span class="sxs-lookup"><span data-stu-id="e5051-110">You can use a <xref:System.Windows.Media.DrawingGroup> to apply a <xref:System.Windows.Media.DrawingGroup.Transform%2A>, <xref:System.Windows.Media.DrawingGroup.Opacity%2A> setting, <xref:System.Windows.Media.DrawingGroup.OpacityMask%2A>, <xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A>, <xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>, or <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A> to the drawings it contains.</span></span> <span data-ttu-id="e5051-111">Poiché un <xref:System.Windows.Media.DrawingGroup> è anche un <xref:System.Windows.Media.Drawing>, può contenere altri <xref:System.Windows.Media.DrawingGroup> oggetti.</span><span class="sxs-lookup"><span data-stu-id="e5051-111">Because a <xref:System.Windows.Media.DrawingGroup> is also a <xref:System.Windows.Media.Drawing>, it can contain other <xref:System.Windows.Media.DrawingGroup> objects.</span></span>  
  
 <span data-ttu-id="e5051-112">Nell'esempio seguente è simile all'esempio precedente, ad eccezione del fatto che vengono utilizzati altri <xref:System.Windows.Media.DrawingGroup> oggetti a cui applicare gli effetti bitmap e una maschera di opacità per alcuni dei disegni.</span><span class="sxs-lookup"><span data-stu-id="e5051-112">The following example is similar to the preceding example, except that it uses additional <xref:System.Windows.Media.DrawingGroup> objects to apply bitmap effects and an opacity mask to some of its drawings.</span></span> <span data-ttu-id="e5051-113">L'immagine seguente illustra l'output generato dall'esempio.</span><span class="sxs-lookup"><span data-stu-id="e5051-113">The following illustration shows the output that this example produces.</span></span>  
  
 <span data-ttu-id="e5051-114">![DrawingGroup con più disegni](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-multiple.jpg "graphicsmm_multiple")</span><span class="sxs-lookup"><span data-stu-id="e5051-114">![A DrawingGroup with multiple drawings](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-multiple.jpg "graphicsmm_multiple")</span></span>  
<span data-ttu-id="e5051-115">Disegno composto con più oggetti DrawingGroup</span><span class="sxs-lookup"><span data-stu-id="e5051-115">Composite drawing that has multiple DrawingGroup objects</span></span>  
  
 <span data-ttu-id="e5051-116">Si noti il bordo grigio, che indica i limiti del disegno.</span><span class="sxs-lookup"><span data-stu-id="e5051-116">Note the gray border, which shows the bounds of the drawing.</span></span>  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMMultipleDrawingGroupsExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingGroupExample.cs#graphicsmmmultipledrawinggroupsexample)]
 [!code-xaml[DrawingMiscSnippets_snip#GraphicsMMMultipleDrawingGroupsExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingGroupExample.xaml#graphicsmmmultipledrawinggroupsexample)]  
  
 <span data-ttu-id="e5051-117">Per ulteriori informazioni su <xref:System.Windows.Media.Drawing> degli oggetti, vedere [panoramica sugli oggetti disegno](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md).</span><span class="sxs-lookup"><span data-stu-id="e5051-117">For more information about <xref:System.Windows.Media.Drawing> objects, see [Drawing Objects Overview](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5051-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e5051-118">See Also</span></span>  
 <xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A>  
 <xref:System.Windows.Media.DrawingGroup.Transform%2A>  
 <xref:System.Windows.Media.DrawingGroup.OpacityMask%2A>  
 <xref:System.Windows.Media.DrawingGroup.Opacity%2A>  
 <xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>  
 <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A>  
 [<span data-ttu-id="e5051-119">Cenni preliminari sugli oggetti Drawing</span><span class="sxs-lookup"><span data-stu-id="e5051-119">Drawing Objects Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)
