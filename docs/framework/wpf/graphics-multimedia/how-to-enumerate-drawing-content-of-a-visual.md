---
title: 'Procedura: Enumerare il contenuto del disegno di un oggetto visivo'
ms.date: 03/30/2017
helpviewer_keywords:
- retrieving the DrawingGroup value of a Visual [WPF]
- enumerating the contents of a Visual [WPF]
ms.assetid: 2974ddb3-2997-4713-8fd2-e93d549c58a8
ms.openlocfilehash: 25aa0c3706005c1e16cedd7e06914db764545ebb
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69930076"
---
# <a name="how-to-enumerate-drawing-content-of-a-visual"></a><span data-ttu-id="f1410-102">Procedura: Enumerare il contenuto del disegno di un oggetto visivo</span><span class="sxs-lookup"><span data-stu-id="f1410-102">How to: Enumerate Drawing Content of a Visual</span></span>
<span data-ttu-id="f1410-103">L' <xref:System.Windows.Media.Drawing> oggetto fornisce un modello a oggetti per l'enumerazione del contenuto di <xref:System.Windows.Media.Visual>un oggetto.</span><span class="sxs-lookup"><span data-stu-id="f1410-103">The <xref:System.Windows.Media.Drawing> object provide an object model for enumerating the contents of a <xref:System.Windows.Media.Visual>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f1410-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="f1410-104">Example</span></span>  
 <span data-ttu-id="f1410-105">Nell'esempio seguente viene usato <xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A> il metodo per recuperare <xref:System.Windows.Media.DrawingGroup> il valore di <xref:System.Windows.Media.Visual> un oggetto ed enumerarlo.</span><span class="sxs-lookup"><span data-stu-id="f1410-105">The following example uses the <xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A> method to retrieve the <xref:System.Windows.Media.DrawingGroup> value of a <xref:System.Windows.Media.Visual> and enumerate it.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f1410-106">Quando si enumera il contenuto dell'oggetto visivo, si recuperano <xref:System.Windows.Media.Drawing> gli oggetti e non la rappresentazione sottostante dei dati di rendering come elenco di istruzioni di grafica vettoriale.</span><span class="sxs-lookup"><span data-stu-id="f1410-106">When you are enumerating the contents of the visual, you are retrieving <xref:System.Windows.Media.Drawing> objects, and not the underlying representation of the render data as a vector graphics instruction list.</span></span> <span data-ttu-id="f1410-107">Per altre informazioni, vedere [Cenni preliminari sul rendering della grafica WPF](wpf-graphics-rendering-overview.md).</span><span class="sxs-lookup"><span data-stu-id="f1410-107">For more information, see [WPF Graphics Rendering Overview](wpf-graphics-rendering-overview.md).</span></span>  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMRetrieveDrawings](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/EnumerateDrawingsExample.xaml.cs#graphicsmmretrievedrawings)]  
  
## <a name="see-also"></a><span data-ttu-id="f1410-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f1410-108">See also</span></span>

- <xref:System.Windows.Media.Drawing>
- <xref:System.Windows.Media.DrawingGroup>
- <xref:System.Windows.Media.VisualTreeHelper>
- [<span data-ttu-id="f1410-109">Cenni preliminari sugli oggetti Drawing</span><span class="sxs-lookup"><span data-stu-id="f1410-109">Drawing Objects Overview</span></span>](drawing-objects-overview.md)
- [<span data-ttu-id="f1410-110">Cenni preliminari sul rendering della grafica WPF</span><span class="sxs-lookup"><span data-stu-id="f1410-110">WPF Graphics Rendering Overview</span></span>](wpf-graphics-rendering-overview.md)
