---
title: 'Procedura: Cercare un orologio in modalità sincrona'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- clocks [WPF], seeking synchronously
- seeking clocks synchronously [WPF]
ms.assetid: e5b7529b-b7d0-40d2-9e1d-fa4b5e736e96
ms.openlocfilehash: 9b6b1f5523effc56ccd9ddaa4f478e1d3a20ada8
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57355993"
---
# <a name="how-to-seek-a-clock-synchronously"></a><span data-ttu-id="9d167-102">Procedura: Cercare un orologio in modalità sincrona</span><span class="sxs-lookup"><span data-stu-id="9d167-102">How to: Seek a Clock Synchronously</span></span>
<span data-ttu-id="9d167-103">Usare il <xref:System.Windows.Media.Animation.ClockController.SeekAlignedToLastTick%2A> metodo per cercare un orologio in un punto specifico in modo sincrono.</span><span class="sxs-lookup"><span data-stu-id="9d167-103">Use the <xref:System.Windows.Media.Animation.ClockController.SeekAlignedToLastTick%2A> method to seek a clock to a specific point synchronously.</span></span> <span data-ttu-id="9d167-104">L'esempio seguente illustra entrambi i <xref:System.Windows.Media.Animation.ClockController.Seek%2A> e <xref:System.Windows.Media.Animation.ClockController.SeekAlignedToLastTick%2A> metodi di un <xref:System.Windows.Media.Animation.ClockController>.</span><span class="sxs-lookup"><span data-stu-id="9d167-104">The following example demonstrates both the <xref:System.Windows.Media.Animation.ClockController.Seek%2A> and <xref:System.Windows.Media.Animation.ClockController.SeekAlignedToLastTick%2A> methods of a <xref:System.Windows.Media.Animation.ClockController>.</span></span>  
  
 <span data-ttu-id="9d167-105">In questo esempio viene illustrato come cercare un <xref:System.Windows.Media.Animation.Clock>; per un esempio che illustra come cercare uno storyboard, vedere [cercare in modo sincrono un Storyboard](how-to-seek-a-storyboard-synchronously.md) .</span><span class="sxs-lookup"><span data-stu-id="9d167-105">This example shows how to seek a <xref:System.Windows.Media.Animation.Clock>; for an example showing how to seek a storyboard, see [Seek a Storyboard Synchronously](how-to-seek-a-storyboard-synchronously.md) .</span></span>  
  
## <a name="example"></a><span data-ttu-id="9d167-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="9d167-106">Example</span></span>  
 [!code-csharp[ClockController_procedural_snip#ClockControllerSeekExample](~/samples/snippets/csharp/VS_Snippets_Wpf/ClockController_procedural_snip/CSharp/SeekAlignedToLastTickExample.cs#clockcontrollerseekexample)]
 [!code-vb[ClockController_procedural_snip#ClockControllerSeekExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ClockController_procedural_snip/visualbasic/seekalignedtolasttickexample.vb#clockcontrollerseekexample)]
