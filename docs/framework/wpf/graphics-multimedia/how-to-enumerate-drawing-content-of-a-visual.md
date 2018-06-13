---
title: 'Procedura: enumerare il contenuto del disegno di un oggetto Visual'
ms.date: 03/30/2017
helpviewer_keywords:
- retrieving the DrawingGroup value of a Visual [WPF]
- enumerating the contents of a Visual [WPF]
ms.assetid: 2974ddb3-2997-4713-8fd2-e93d549c58a8
ms.openlocfilehash: 19c37ec7df3542eb46b182f4790059eb16fef90b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33559402"
---
# <a name="how-to-enumerate-drawing-content-of-a-visual"></a><span data-ttu-id="22bfc-102">Procedura: enumerare il contenuto del disegno di un oggetto Visual</span><span class="sxs-lookup"><span data-stu-id="22bfc-102">How to: Enumerate Drawing Content of a Visual</span></span>
<span data-ttu-id="22bfc-103">Il <xref:System.Windows.Media.Drawing> oggetto forniscono un modello a oggetti per l'enumerazione del contenuto di un <xref:System.Windows.Media.Visual>.</span><span class="sxs-lookup"><span data-stu-id="22bfc-103">The <xref:System.Windows.Media.Drawing> object provide an object model for enumerating the contents of a <xref:System.Windows.Media.Visual>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="22bfc-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="22bfc-104">Example</span></span>  
 <span data-ttu-id="22bfc-105">L'esempio seguente usa il <xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A> metodo per recuperare il <xref:System.Windows.Media.DrawingGroup> valore di un <xref:System.Windows.Media.Visual> e di eseguirne l'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="22bfc-105">The following example uses the <xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A> method to retrieve the <xref:System.Windows.Media.DrawingGroup> value of a <xref:System.Windows.Media.Visual> and enumerate it.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="22bfc-106">Quando si sta enumerando il contenuto dell'oggetto visivo, vengono recuperati <xref:System.Windows.Media.Drawing> oggetti e non la rappresentazione sottostante dei dati di rendering come un elenco di istruzioni di grafica vettoriale.</span><span class="sxs-lookup"><span data-stu-id="22bfc-106">When you are enumerating the contents of the visual, you are retrieving <xref:System.Windows.Media.Drawing> objects, and not the underlying representation of the render data as a vector graphics instruction list.</span></span> <span data-ttu-id="22bfc-107">Per altre informazioni, vedere [Cenni preliminari sul rendering della grafica WPF](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md).</span><span class="sxs-lookup"><span data-stu-id="22bfc-107">For more information, see [WPF Graphics Rendering Overview](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md).</span></span>  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMRetrieveDrawings](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/EnumerateDrawingsExample.xaml.cs#graphicsmmretrievedrawings)]  
  
## <a name="see-also"></a><span data-ttu-id="22bfc-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="22bfc-108">See Also</span></span>  
 <xref:System.Windows.Media.Drawing>  
 <xref:System.Windows.Media.DrawingGroup>  
 <xref:System.Windows.Media.VisualTreeHelper>  
 [<span data-ttu-id="22bfc-109">Cenni preliminari sugli oggetti Drawing</span><span class="sxs-lookup"><span data-stu-id="22bfc-109">Drawing Objects Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)  
 [<span data-ttu-id="22bfc-110">Cenni preliminari sul rendering della grafica WPF</span><span class="sxs-lookup"><span data-stu-id="22bfc-110">WPF Graphics Rendering Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md)
