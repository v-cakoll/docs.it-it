---
title: 'Procedura: Creare un disegno composto'
ms.date: 03/30/2017
helpviewer_keywords:
- drawings [WPF], composite
- composite drawings [WPF]
- graphics [WPF], composite drawings
ms.assetid: 066eb0ab-5f0e-439d-85c6-dca60af269fc
ms.openlocfilehash: 0af7fbca593627ebe8cd102a02617a27eac50aa5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59132470"
---
# <a name="how-to-create-a-composite-drawing"></a><span data-ttu-id="d4ff0-102">Procedura: Creare un disegno composto</span><span class="sxs-lookup"><span data-stu-id="d4ff0-102">How to: Create a Composite Drawing</span></span>
<span data-ttu-id="d4ff0-103">In questo esempio viene illustrato come utilizzare un <xref:System.Windows.Media.DrawingGroup> per creare disegni complesse combinando più <xref:System.Windows.Media.Drawing> gli oggetti in un unico disegno composto.</span><span class="sxs-lookup"><span data-stu-id="d4ff0-103">This example shows how to use a <xref:System.Windows.Media.DrawingGroup> to create complex drawings by combining multiple <xref:System.Windows.Media.Drawing> objects into a single composite drawing.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d4ff0-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="d4ff0-104">Example</span></span>  
 <span data-ttu-id="d4ff0-105">L'esempio seguente usa un' <xref:System.Windows.Media.DrawingGroup> per creare un disegno composto dal <xref:System.Windows.Media.GeometryDrawing> e <xref:System.Windows.Media.ImageDrawing> oggetti.</span><span class="sxs-lookup"><span data-stu-id="d4ff0-105">The following example uses a <xref:System.Windows.Media.DrawingGroup> to create a composite drawing from the <xref:System.Windows.Media.GeometryDrawing> and <xref:System.Windows.Media.ImageDrawing> objects.</span></span> <span data-ttu-id="d4ff0-106">L'immagine seguente illustra l'output generato dall'esempio.</span><span class="sxs-lookup"><span data-stu-id="d4ff0-106">The following illustration shows the output that this example produces.</span></span>  
  
 <span data-ttu-id="d4ff0-107">![Oggetto DrawingGroup con più disegni](./media/graphicsmm-simple.jpg "graphicsmm_simple")</span><span class="sxs-lookup"><span data-stu-id="d4ff0-107">![A DrawingGroup with multiple drawings](./media/graphicsmm-simple.jpg "graphicsmm_simple")</span></span>  
<span data-ttu-id="d4ff0-108">Un disegno composto che viene creato usando DrawingGroup</span><span class="sxs-lookup"><span data-stu-id="d4ff0-108">A composite drawing that is created by using DrawingGroup</span></span>  
  
 <span data-ttu-id="d4ff0-109">Si noti il bordo grigio, che mostra i limiti del disegno.</span><span class="sxs-lookup"><span data-stu-id="d4ff0-109">Note the gray border, which shows the bounds of the drawing.</span></span>  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMSimpleDrawingGroupExample](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingGroupExample.cs#graphicsmmsimpledrawinggroupexample)]
 [!code-xaml[DrawingMiscSnippets_snip#GraphicsMMSimpleDrawingGroupExample](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingGroupExample.xaml#graphicsmmsimpledrawinggroupexample)]  
  
 <span data-ttu-id="d4ff0-110">È possibile usare un <xref:System.Windows.Media.DrawingGroup> per applicare una <xref:System.Windows.Media.DrawingGroup.Transform%2A>, <xref:System.Windows.Media.DrawingGroup.Opacity%2A> impostazione <xref:System.Windows.Media.DrawingGroup.OpacityMask%2A>, <xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A>, <xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>, o <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A> di disegni che contiene.</span><span class="sxs-lookup"><span data-stu-id="d4ff0-110">You can use a <xref:System.Windows.Media.DrawingGroup> to apply a <xref:System.Windows.Media.DrawingGroup.Transform%2A>, <xref:System.Windows.Media.DrawingGroup.Opacity%2A> setting, <xref:System.Windows.Media.DrawingGroup.OpacityMask%2A>, <xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A>, <xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>, or <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A> to the drawings it contains.</span></span> <span data-ttu-id="d4ff0-111">Poiché un <xref:System.Windows.Media.DrawingGroup> è anche un <xref:System.Windows.Media.Drawing>, può contenere altri <xref:System.Windows.Media.DrawingGroup> oggetti.</span><span class="sxs-lookup"><span data-stu-id="d4ff0-111">Because a <xref:System.Windows.Media.DrawingGroup> is also a <xref:System.Windows.Media.Drawing>, it can contain other <xref:System.Windows.Media.DrawingGroup> objects.</span></span>  
  
 <span data-ttu-id="d4ff0-112">Nell'esempio seguente è simile all'esempio precedente, ad eccezione del fatto che usi aggiuntivi <xref:System.Windows.Media.DrawingGroup> oggetti a cui applicare gli effetti bitmap e una maschera di opacità per alcuni dei disegni.</span><span class="sxs-lookup"><span data-stu-id="d4ff0-112">The following example is similar to the preceding example, except that it uses additional <xref:System.Windows.Media.DrawingGroup> objects to apply bitmap effects and an opacity mask to some of its drawings.</span></span> <span data-ttu-id="d4ff0-113">L'immagine seguente illustra l'output generato dall'esempio.</span><span class="sxs-lookup"><span data-stu-id="d4ff0-113">The following illustration shows the output that this example produces.</span></span>  
  
 <span data-ttu-id="d4ff0-114">![Oggetto DrawingGroup con più disegni](./media/graphicsmm-multiple.jpg "graphicsmm_multiple")</span><span class="sxs-lookup"><span data-stu-id="d4ff0-114">![A DrawingGroup with multiple drawings](./media/graphicsmm-multiple.jpg "graphicsmm_multiple")</span></span>  
<span data-ttu-id="d4ff0-115">Disegno composto con più DrawingGroup (oggetti)</span><span class="sxs-lookup"><span data-stu-id="d4ff0-115">Composite drawing that has multiple DrawingGroup objects</span></span>  
  
 <span data-ttu-id="d4ff0-116">Si noti il bordo grigio, che mostra i limiti del disegno.</span><span class="sxs-lookup"><span data-stu-id="d4ff0-116">Note the gray border, which shows the bounds of the drawing.</span></span>  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMMultipleDrawingGroupsExample](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingGroupExample.cs#graphicsmmmultipledrawinggroupsexample)]
 [!code-xaml[DrawingMiscSnippets_snip#GraphicsMMMultipleDrawingGroupsExample](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingGroupExample.xaml#graphicsmmmultipledrawinggroupsexample)]  
  
 <span data-ttu-id="d4ff0-117">Per altre informazioni sulle <xref:System.Windows.Media.Drawing> oggetti, vedere [Cenni preliminari sugli oggetti Drawing](drawing-objects-overview.md).</span><span class="sxs-lookup"><span data-stu-id="d4ff0-117">For more information about <xref:System.Windows.Media.Drawing> objects, see [Drawing Objects Overview](drawing-objects-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4ff0-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d4ff0-118">See also</span></span>

- <xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A>
- <xref:System.Windows.Media.DrawingGroup.Transform%2A>
- <xref:System.Windows.Media.DrawingGroup.OpacityMask%2A>
- <xref:System.Windows.Media.DrawingGroup.Opacity%2A>
- <xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>
- <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A>
- [<span data-ttu-id="d4ff0-119">Cenni preliminari sugli oggetti Drawing</span><span class="sxs-lookup"><span data-stu-id="d4ff0-119">Drawing Objects Overview</span></span>](drawing-objects-overview.md)
