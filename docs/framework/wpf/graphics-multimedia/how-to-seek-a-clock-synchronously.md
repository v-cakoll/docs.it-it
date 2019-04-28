---
title: 'Procedura: Cercare un oggetto Clock in modalità sincrona'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- clocks [WPF], seeking synchronously
- seeking clocks synchronously [WPF]
ms.assetid: e5b7529b-b7d0-40d2-9e1d-fa4b5e736e96
ms.openlocfilehash: 9b6b1f5523effc56ccd9ddaa4f478e1d3a20ada8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61651259"
---
# <a name="how-to-seek-a-clock-synchronously"></a>Procedura: Cercare un oggetto Clock in modalità sincrona
Usare il <xref:System.Windows.Media.Animation.ClockController.SeekAlignedToLastTick%2A> metodo per cercare un orologio in un punto specifico in modo sincrono. L'esempio seguente illustra entrambi i <xref:System.Windows.Media.Animation.ClockController.Seek%2A> e <xref:System.Windows.Media.Animation.ClockController.SeekAlignedToLastTick%2A> metodi di un <xref:System.Windows.Media.Animation.ClockController>.  
  
 In questo esempio viene illustrato come cercare un <xref:System.Windows.Media.Animation.Clock>; per un esempio che illustra come cercare uno storyboard, vedere [cercare in modo sincrono un Storyboard](how-to-seek-a-storyboard-synchronously.md) .  
  
## <a name="example"></a>Esempio  
 [!code-csharp[ClockController_procedural_snip#ClockControllerSeekExample](~/samples/snippets/csharp/VS_Snippets_Wpf/ClockController_procedural_snip/CSharp/SeekAlignedToLastTickExample.cs#clockcontrollerseekexample)]
 [!code-vb[ClockController_procedural_snip#ClockControllerSeekExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ClockController_procedural_snip/visualbasic/seekalignedtolasttickexample.vb#clockcontrollerseekexample)]
