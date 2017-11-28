---
title: 'Procedura: controllare in modo interattivo un oggetto Clock'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controlling clocks interactively [WPF]
- clocks [WPF], controlling interactively
ms.assetid: d0b520e0-2f18-4cef-977f-2909e709548a
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: debe65ef1587171dc2f324a19da4b43e7274c438
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-interactively-control-a-clock"></a>Procedura: controllare in modo interattivo un oggetto Clock
Oggetto <xref:System.Windows.Media.Animation.Clock> dell'oggetto <xref:System.Windows.Media.Animation.ClockController> proprietà consente di in modo interattivo avviare, sospendere, riprendere, ricerca, spostare l'orologio al periodo di riempimento e arrestare l'orologio. È possibile controllare in modo interattivo solo il clock radice di un struttura ad albero di temporizzazione.  
  
> [!NOTE]
>  Esistono altri modi per in modo interattivo le animazioni di controllo che non richiedono di utilizzare direttamente i clock: è anche possibile usare gli storyboard. Gli storyboard sono supportati nel markup e codice. Per un esempio, vedere [animazione di una proprietà utilizzando uno Storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md) o [panoramica dell'animazione](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  
  
 Nell'esempio seguente, molti pulsanti consentono di controllare in modo interattivo un orologio dell'animazione.  
  
## <a name="example"></a>Esempio  
 [!code-csharp[timingbehaviors_procedural_snip#GraphicsMMClockControllerExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/ClockControllerExample.cs#graphicsmmclockcontrollerexample)]
 [!code-vb[timingbehaviors_procedural_snip#GraphicsMMClockControllerExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/clockcontrollerexample.vb#graphicsmmclockcontrollerexample)]  
  
## <a name="see-also"></a>Vedere anche  
 [Animare una proprietà utilizzando uno storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md)  
 [Cenni preliminari sull'animazione](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)
