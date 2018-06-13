---
title: Cenni preliminari sul componente Timer (Windows Form)
ms.date: 03/30/2017
f1_keywords:
- Timer
helpviewer_keywords:
- Timer component [Windows Forms], about Timer components
- timers [Windows Forms], about timers
ms.assetid: e672c05b-a8b6-4b26-9e4d-9223aa9e3873
ms.openlocfilehash: 39bc3c8cda06a62eb40b042e46cbd070a82cce01
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33535502"
---
# <a name="timer-component-overview-windows-forms"></a>Cenni preliminari sul componente Timer (Windows Form)
Il componente <xref:System.Windows.Forms.Timer> di Windows Form genera un evento a intervalli regolari. Questo componente è progettato per l'ambiente Windows Form. Per informazioni su un timer adatto a un ambiente server, vedere [Introduzione ai timer basati su server](http://msdn.microsoft.com/library/adc0bc0a-a519-4812-bafc-fb9d1a5801fc).  
  
## <a name="key-properties-methods-and-events"></a>Proprietà, metodi ed eventi principali  
 La lunghezza degli intervalli viene definita per il <xref:System.Windows.Forms.Timer.Interval%2A> proprietà il cui valore è espresso in millisecondi. Quando il componente è abilitato, il <xref:System.Windows.Forms.Timer.Tick> evento viene generato ogni intervallo. Si tratta in cui è necessario aggiungere codice da eseguire. Per ulteriori informazioni, vedere [procedura: eseguire routine a intervalli impostato con il componente Timer di Windows Form](../../../../docs/framework/winforms/controls/run-procedures-at-set-intervals-with-wf-timer-component.md). I metodi principali del <xref:System.Windows.Forms.Timer> componente sono <xref:System.Windows.Forms.Timer.Start%2A> e <xref:System.Windows.Forms.Timer.Stop%2A>, che il timer di attivare e disattivare. Quando il timer è disattivato, Ripristina; non è possibile sospendere un <xref:System.Windows.Forms.Timer> componente.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.Timer>  
 [Componente Timer](../../../../docs/framework/winforms/controls/timer-component-windows-forms.md)  
 [Limitazioni della proprietà Interval del componente Timer di Windows Form](../../../../docs/framework/winforms/controls/limitations-of-the-timer-component-interval-property.md)
