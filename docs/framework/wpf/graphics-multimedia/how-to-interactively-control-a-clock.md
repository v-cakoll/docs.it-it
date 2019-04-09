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
ms.openlocfilehash: 05989b6a03e03fb5723a70c9c36d5e32f9117049
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59186589"
---
# <a name="how-to-interactively-control-a-clock"></a>Procedura: Controllare in modo interattivo un oggetto Clock
Oggetto <xref:System.Windows.Media.Animation.Clock> dell'oggetto <xref:System.Windows.Media.Animation.ClockController> proprietà consente in modo interattivo avviare, sospendere, riprendere, seek, spostare l'orologio per periodo di riempimento e arrestare l'orologio. È possibile controllare in modo interattivo solo il clock radice di un albero di temporizzazione.  
  
> [!NOTE]
>  Esistono altri modi per in modo interattivo le animazioni di controllo che non richiedono di lavorare direttamente con gli orologi: è anche possibile usare gli storyboard. Gli storyboard sono supportati nel markup e nel codice. Per un esempio, vedere [animare una proprietà utilizzando uno Storyboard](how-to-animate-a-property-by-using-a-storyboard.md) o nella [Cenni preliminari sull'animazione](animation-overview.md).  
  
 Nell'esempio seguente, diversi pulsanti consentono di controllare in modo interattivo un orologio dell'animazione.  
  
## <a name="example"></a>Esempio  
 [!code-csharp[timingbehaviors_procedural_snip#GraphicsMMClockControllerExample](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/ClockControllerExample.cs#graphicsmmclockcontrollerexample)]
 [!code-vb[timingbehaviors_procedural_snip#GraphicsMMClockControllerExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/clockcontrollerexample.vb#graphicsmmclockcontrollerexample)]  
  
## <a name="see-also"></a>Vedere anche

- [Aggiungere un'animazione a una proprietà usando uno storyboard](how-to-animate-a-property-by-using-a-storyboard.md)
- [Cenni preliminari sull'animazione](animation-overview.md)
