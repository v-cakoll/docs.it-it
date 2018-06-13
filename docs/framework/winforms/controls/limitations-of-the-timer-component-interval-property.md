---
title: Limitazioni del componente Timer di Windows Form&#39;proprietà Interval s
ms.date: 03/30/2017
helpviewer_keywords:
- timers [Windows Forms], event intervals
- Interval property [Windows Forms], limitations
- timers [Windows Forms], Windows-based
- Timer component [Windows Forms], limitations of Interval property
ms.assetid: 7e5fb513-77e7-4046-a8e8-aab94e61ca0f
ms.openlocfilehash: 4808d115ff842c6c0e6b036da9fe20bb1b48f8a7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33536026"
---
# <a name="limitations-of-the-windows-forms-timer-component39s-interval-property"></a>Limitazioni del componente Timer di Windows Form&#39;proprietà Interval s
Windows Form <xref:System.Windows.Forms.Timer> componente dispone di un <xref:System.Windows.Forms.Timer.Interval%2A> proprietà che specifica il numero di millisecondi che intercorre tra un evento timer e quello successivo. A meno che il componente è disabilitato, un timer continuerà a ricevere il <xref:System.Windows.Forms.Timer.Tick> evento quasi uguale a intervalli di tempo.  
  
 Questo componente è progettato per l'ambiente Windows Form. Per informazioni su un timer adatto a un ambiente server, vedere [Introduzione ai timer basati su server](http://msdn.microsoft.com/library/adc0bc0a-a519-4812-bafc-fb9d1a5801fc).  
  
## <a name="the-interval-property"></a>La proprietà Interval  
 Il <xref:System.Windows.Forms.Timer.Interval%2A> proprietà presenta alcune limitazioni da prendere in considerazione quando si programma un <xref:System.Windows.Forms.Timer> componente:  
  
-   Se l'applicazione o un'altra applicazione in esecuzione nel sistema, ad esempio cicli lunghi, calcoli, unità, rete o accesso alle porte, l'applicazione potrebbe non ricevere gli eventi del timer più spesso come il <xref:System.Windows.Forms.Timer.Interval%2A> proprietà specifica.  
  
-   L'intervallo non è garantita l'esattezza ora. Per garantire l'accuratezza, il timer deve controllare l'orologio di sistema in base alle esigenze, anziché tentare di tenere traccia del tempo accumulato internamente.  
  
-   La precisione del <xref:System.Windows.Forms.Timer.Interval%2A> proprietà è espresso in millisecondi. Alcuni computer forniscono un contatore ad alta risoluzione con risoluzione superiore a millisecondi. La disponibilità di tale contatore dipende dall'hardware del processore del computer. Per altre informazioni, vedere l'articolo 172338, "Modalità per utilizzare QueryPerformanceCounter a tempo codice," nella Microsoft Knowledge Base al http://support.microsoft.com.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.Timer>  
 [Componente Timer](../../../../docs/framework/winforms/controls/timer-component-windows-forms.md)  
 [Panoramica sul componente Timer](../../../../docs/framework/winforms/controls/timer-component-overview-windows-forms.md)
