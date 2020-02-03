---
title: Cenni preliminari sul componente Timer
ms.date: 03/30/2017
f1_keywords:
- Timer
helpviewer_keywords:
- Timer component [Windows Forms], about Timer components
- timers [Windows Forms], about timers
ms.assetid: e672c05b-a8b6-4b26-9e4d-9223aa9e3873
ms.openlocfilehash: 83b52d395cdc3e3357bcf83517eab258a5c8ae08
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742776"
---
# <a name="timer-component-overview-windows-forms"></a>Panoramica del componente Timer (Windows Form)
Il componente <xref:System.Windows.Forms.Timer> di Windows Form genera un evento a intervalli regolari. Questo componente è progettato per l'ambiente Windows Form. Per informazioni su un timer adatto a un ambiente server, vedere [Introduzione ai timer basati su server](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90)).  
  
## <a name="key-properties-methods-and-events"></a>Proprietà, metodi ed eventi chiave  
 La lunghezza degli intervalli è definita dalla proprietà <xref:System.Windows.Forms.Timer.Interval%2A>, il cui valore è in millisecondi. Quando il componente è abilitato, l'evento <xref:System.Windows.Forms.Timer.Tick> viene generato ogni intervallo. Qui è possibile aggiungere il codice da eseguire. Per altre informazioni, vedere [procedura: eseguire routine a intervalli prestabiliti con il componente Timer Windows Forms](run-procedures-at-set-intervals-with-wf-timer-component.md). I metodi principali del componente <xref:System.Windows.Forms.Timer> sono <xref:System.Windows.Forms.Timer.Start%2A> e <xref:System.Windows.Forms.Timer.Stop%2A>, che attivano e disattivano il timer. Quando il timer viene disattivato, viene reimpostato; non è possibile sospendere un componente <xref:System.Windows.Forms.Timer>.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.Timer>
- [Componente Timer](timer-component-windows-forms.md)
- [Limitazioni della proprietà Interval del componente Timer di Windows Form](limitations-of-the-timer-component-interval-property.md)
