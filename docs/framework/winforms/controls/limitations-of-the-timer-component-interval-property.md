---
title: "Limitazioni del componente Timer di Windows Form &#39; proprietà Interval s"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- timers [Windows Forms], event intervals
- Interval property [Windows Forms], limitations
- timers [Windows Forms], Windows-based
- Timer component [Windows Forms], limitations of Interval property
ms.assetid: 7e5fb513-77e7-4046-a8e8-aab94e61ca0f
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ec53957a61806239fdd41761de6e172681b7497b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="limitations-of-the-windows-forms-timer-component39s-interval-property"></a>Limitazioni del componente Timer di Windows Form &#39; proprietà Interval s
Windows Form <xref:System.Windows.Forms.Timer> componente dispone di un <xref:System.Windows.Forms.Timer.Interval%2A> proprietà che specifica il numero di millisecondi che intercorre tra un evento timer e quello successivo. A meno che il componente è disabilitato, un timer continuerà a ricevere il <xref:System.Windows.Forms.Timer.Tick> evento quasi uguale a intervalli di tempo.  
  
 Questo componente è progettato per l'ambiente Windows Form. Per informazioni su un timer adatto a un ambiente server, vedere [Introduzione ai timer basati su server](http://msdn.microsoft.com/en-us/adc0bc0a-a519-4812-bafc-fb9d1a5801fc).  
  
## <a name="the-interval-property"></a>La proprietà Interval  
 Il <xref:System.Windows.Forms.Timer.Interval%2A> proprietà presenta alcune limitazioni da prendere in considerazione quando si programma un <xref:System.Windows.Forms.Timer> componente:  
  
-   Se l'applicazione o un'altra applicazione in esecuzione nel sistema, ad esempio cicli lunghi, calcoli, unità, rete o accesso alle porte, l'applicazione potrebbe non ricevere gli eventi del timer più spesso come il <xref:System.Windows.Forms.Timer.Interval%2A> proprietà specifica.  
  
-   L'intervallo non è garantita l'esattezza ora. Per garantire l'accuratezza, il timer deve controllare l'orologio di sistema in base alle esigenze, anziché tentare di tenere traccia del tempo accumulato internamente.  
  
-   La precisione del <xref:System.Windows.Forms.Timer.Interval%2A> proprietà è espresso in millisecondi. Alcuni computer forniscono un contatore ad alta risoluzione con risoluzione superiore a millisecondi. La disponibilità di tale contatore dipende dall'hardware del processore del computer. Per ulteriori informazioni, vedere l'articolo 172338, "Come a utilizzare QueryPerformanceCounter per codice Time" in http://support.microsoft.com nella Microsoft Knowledge Base.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.Timer>  
 [Componente Timer](../../../../docs/framework/winforms/controls/timer-component-windows-forms.md)  
 [Panoramica sul componente Timer](../../../../docs/framework/winforms/controls/timer-component-overview-windows-forms.md)
