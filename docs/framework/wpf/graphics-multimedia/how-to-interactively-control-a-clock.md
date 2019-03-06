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
ms.openlocfilehash: 6d3dbc8c39e63b46871b0cc88fbe8d5d51b63463
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57361655"
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
- [Animare una proprietà utilizzando uno storyboard](how-to-animate-a-property-by-using-a-storyboard.md)
- [Cenni preliminari sull'animazione](animation-overview.md)
