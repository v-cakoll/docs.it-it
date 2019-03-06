---
title: 'Procedura: Disegnare testo in un oggetto Visual'
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
ms.openlocfilehash: 1ea31540ad59ab419e209e4133bcb88640cc01fe
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57368907"
---
# <a name="how-to-draw-text-to-a-visual"></a><span data-ttu-id="cf7c3-102">Procedura: Disegnare testo in un oggetto Visual</span><span class="sxs-lookup"><span data-stu-id="cf7c3-102">How to: Draw Text to a Visual</span></span>
<span data-ttu-id="cf7c3-103">Nell'esempio seguente illustra come disegnare testo in un <xref:System.Windows.Media.DrawingVisual> usando un <xref:System.Windows.Media.DrawingContext> oggetto.</span><span class="sxs-lookup"><span data-stu-id="cf7c3-103">The following example shows how to draw text to a <xref:System.Windows.Media.DrawingVisual> using a <xref:System.Windows.Media.DrawingContext> object.</span></span> <span data-ttu-id="cf7c3-104">Un contesto di disegno viene restituito chiamando il <xref:System.Windows.Media.DrawingVisual.RenderOpen%2A> metodo di un <xref:System.Windows.Media.DrawingVisual> oggetto.</span><span class="sxs-lookup"><span data-stu-id="cf7c3-104">A drawing context is returned by calling the <xref:System.Windows.Media.DrawingVisual.RenderOpen%2A> method of a <xref:System.Windows.Media.DrawingVisual> object.</span></span> <span data-ttu-id="cf7c3-105">È possibile disegnare grafica e testo in un contesto di disegno.</span><span class="sxs-lookup"><span data-stu-id="cf7c3-105">You can draw graphics and text into a drawing context.</span></span>  
  
 <span data-ttu-id="cf7c3-106">Per disegnare il testo nel contesto di disegno, usare il <xref:System.Windows.Media.DrawingContext.DrawText%2A> metodo di un <xref:System.Windows.Media.DrawingContext> oggetto.</span><span class="sxs-lookup"><span data-stu-id="cf7c3-106">To draw text into the drawing context, use the <xref:System.Windows.Media.DrawingContext.DrawText%2A> method of a <xref:System.Windows.Media.DrawingContext> object.</span></span> <span data-ttu-id="cf7c3-107">Quando si è finito di disegno del contenuto nel contesto di disegno, chiamare il <xref:System.Windows.Media.DrawingContext.Close%2A> Close per chiudere il contesto di disegno e mantenere il contenuto.</span><span class="sxs-lookup"><span data-stu-id="cf7c3-107">When you are finished drawing content into the drawing context, call the <xref:System.Windows.Media.DrawingContext.Close%2A> method to close the drawing context and persist the content.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cf7c3-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="cf7c3-108">Example</span></span>  
 [!code-csharp[DrawingVisualSample#110](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#110)]
 [!code-vb[DrawingVisualSample#110](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#110)]  
  
> [!NOTE]
>  <span data-ttu-id="cf7c3-109">Per l'esempio di codice completo dal quale è stato estratto l'esempio di codice precedente, vedere [Hit Test Using DrawingVisuals Sample (Esempio di Hit Test mediante DrawingVisual)](https://go.microsoft.com/fwlink/?LinkID=159994).</span><span class="sxs-lookup"><span data-stu-id="cf7c3-109">For the complete code sample from which the preceding code example was extracted, see [Hit Test Using DrawingVisuals Sample](https://go.microsoft.com/fwlink/?LinkID=159994).</span></span>
