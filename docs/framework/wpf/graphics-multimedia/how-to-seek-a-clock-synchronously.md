---
title: 'Procedura: cercare un orologio in modalità sincrona'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- clocks [WPF], seeking synchronously
- seeking clocks synchronously [WPF]
ms.assetid: e5b7529b-b7d0-40d2-9e1d-fa4b5e736e96
ms.openlocfilehash: d8e7b0f4bfa3a59814d87bfb6d7e8b40bd80f6e3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-seek-a-clock-synchronously"></a>Procedura: cercare un orologio in modalità sincrona
Utilizzare il <xref:System.Windows.Media.Animation.ClockController.SeekAlignedToLastTick%2A> metodo per la ricerca di un orologio in un punto specifico in modo sincrono. Nell'esempio riportato di seguito viene illustrato il <xref:System.Windows.Media.Animation.ClockController.Seek%2A> e <xref:System.Windows.Media.Animation.ClockController.SeekAlignedToLastTick%2A> metodi di un <xref:System.Windows.Media.Animation.ClockController>.  
  
 In questo esempio viene illustrato come cercare un <xref:System.Windows.Media.Animation.Clock>; per un esempio che illustra come cercare uno storyboard, vedere [cercare in modo sincrono un Storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-seek-a-storyboard-synchronously.md) .  
  
## <a name="example"></a>Esempio  
 [!code-csharp[ClockController_procedural_snip#ClockControllerSeekExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ClockController_procedural_snip/CSharp/SeekAlignedToLastTickExample.cs#clockcontrollerseekexample)]
 [!code-vb[ClockController_procedural_snip#ClockControllerSeekExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ClockController_procedural_snip/visualbasic/seekalignedtolasttickexample.vb#clockcontrollerseekexample)]
