---
title: 'Procedura: Controllare in modo interattivo un oggetto Clock'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controlling clocks interactively [WPF]
- clocks [WPF], controlling interactively
ms.assetid: d0b520e0-2f18-4cef-977f-2909e709548a
ms.openlocfilehash: 2d18f395974750a6b85458f636a27f6101e7978f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69951342"
---
# <a name="how-to-interactively-control-a-clock"></a>Procedura: Controllare in modo interattivo un oggetto Clock
La <xref:System.Windows.Media.Animation.Clock> <xref:System.Windows.Media.Animation.ClockController> proprietà di un oggetto consente di avviare, sospendere, riprendere, cercare, far avanzare il clock al periodo di riempimento e di arrestare l'orologio in modo interattivo. Solo il clock radice di un albero temporale può essere controllato in modo interattivo.  
  
> [!NOTE]
> Esistono altri modi per controllare in modo interattivo le animazioni che non richiedono l'uso diretto degli orologi: è anche possibile usare gli storyboard. Gli storyboard sono supportati sia nel markup che nel codice. Per un esempio, vedere [animare una proprietà utilizzando uno storyboard](how-to-animate-a-property-by-using-a-storyboard.md) o [Cenni preliminari sull'animazione](animation-overview.md).  
  
 Nell'esempio seguente vengono usati diversi pulsanti per controllare in modo interattivo un clock di animazione.  
  
## <a name="example"></a>Esempio  
 [!code-csharp[timingbehaviors_procedural_snip#GraphicsMMClockControllerExample](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/ClockControllerExample.cs#graphicsmmclockcontrollerexample)]
 [!code-vb[timingbehaviors_procedural_snip#GraphicsMMClockControllerExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/clockcontrollerexample.vb#graphicsmmclockcontrollerexample)]  
  
## <a name="see-also"></a>Vedere anche

- [Animare una proprietà utilizzando uno storyboard](how-to-animate-a-property-by-using-a-storyboard.md)
- [Cenni preliminari sull'animazione](animation-overview.md)
