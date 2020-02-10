---
title: 'Procedura: disegnare testo in un oggetto Visual'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- typography [WPF], drawing text to visuals
- visuals [WPF], drawing text to
- text [WPF], drawing to visuals
- drawing [WPF], text to visuals
ms.assetid: fee4003c-e8a6-46ec-babd-2c7f4231a101
ms.openlocfilehash: 654bfadb42f053b6dcf353d4423bddf281d69478
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/09/2020
ms.locfileid: "77094553"
---
# <a name="how-to-draw-text-to-a-visual"></a><span data-ttu-id="fb91f-102">Procedura: disegnare testo in un oggetto Visual</span><span class="sxs-lookup"><span data-stu-id="fb91f-102">How to: Draw Text to a Visual</span></span>
<span data-ttu-id="fb91f-103">Nell'esempio seguente viene illustrato come creare testo in un <xref:System.Windows.Media.DrawingVisual> utilizzando un oggetto <xref:System.Windows.Media.DrawingContext>.</span><span class="sxs-lookup"><span data-stu-id="fb91f-103">The following example shows how to draw text to a <xref:System.Windows.Media.DrawingVisual> using a <xref:System.Windows.Media.DrawingContext> object.</span></span> <span data-ttu-id="fb91f-104">Un contesto di disegno viene restituito chiamando il metodo <xref:System.Windows.Media.DrawingVisual.RenderOpen%2A> di un oggetto <xref:System.Windows.Media.DrawingVisual>.</span><span class="sxs-lookup"><span data-stu-id="fb91f-104">A drawing context is returned by calling the <xref:System.Windows.Media.DrawingVisual.RenderOpen%2A> method of a <xref:System.Windows.Media.DrawingVisual> object.</span></span> <span data-ttu-id="fb91f-105">È possibile disegnare grafica e testo in un contesto di disegno.</span><span class="sxs-lookup"><span data-stu-id="fb91f-105">You can draw graphics and text into a drawing context.</span></span>  
  
 <span data-ttu-id="fb91f-106">Per disegnare testo nel contesto di disegno, utilizzare il metodo <xref:System.Windows.Media.DrawingContext.DrawText%2A> di un oggetto <xref:System.Windows.Media.DrawingContext>.</span><span class="sxs-lookup"><span data-stu-id="fb91f-106">To draw text into the drawing context, use the <xref:System.Windows.Media.DrawingContext.DrawText%2A> method of a <xref:System.Windows.Media.DrawingContext> object.</span></span> <span data-ttu-id="fb91f-107">Al termine della creazione del contenuto nel contesto di disegno, chiamare il metodo <xref:System.Windows.Media.DrawingContext.Close%2A> per chiudere il contesto di disegno e salvare in modo permanente il contenuto.</span><span class="sxs-lookup"><span data-stu-id="fb91f-107">When you are finished drawing content into the drawing context, call the <xref:System.Windows.Media.DrawingContext.Close%2A> method to close the drawing context and persist the content.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fb91f-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="fb91f-108">Example</span></span>  
 [!code-csharp[DrawingVisualSample#110](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#110)]
 [!code-vb[DrawingVisualSample#110](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#110)]  
  
> [!NOTE]
> <span data-ttu-id="fb91f-109">Per l'esempio di codice completo dal quale è stato estratto l'esempio di codice precedente, vedere [Hit Test Using DrawingVisuals Sample (Esempio di Hit Test mediante DrawingVisual)](https://github.com/Microsoft/WPF-Samples/tree/master/Visual%20Layer/DrawingVisual).</span><span class="sxs-lookup"><span data-stu-id="fb91f-109">For the complete code sample from which the preceding code example was extracted, see [Hit Test Using DrawingVisuals Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Visual%20Layer/DrawingVisual).</span></span>
