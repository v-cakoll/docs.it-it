---
title: Risparmio energia
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- battery states
- power states
ms.assetid: ad04a801-5682-4d88-92c5-26eb9cdb209a
ms.openlocfilehash: 9ac39df43a08f62e50116c61c4bdeda4cd1c8281
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746858"
---
# <a name="power-management-in-windows-forms"></a>Risparmio energia in Windows Form
Le applicazioni Windows Forms possono sfruttare le funzionalità di risparmio energia del sistema operativo Windows. Le applicazioni possono monitorare lo stato di alimentazione di un computer e intervenire quando si verifica una modifica dello stato. Se, ad esempio, l'applicazione è in esecuzione in un computer portatile, potrebbe essere necessario disabilitare determinate funzionalità nell'applicazione quando il costo della batteria del computer rientra in un determinato livello.  
  
 Il .NET Framework fornisce un evento di <xref:Microsoft.Win32.SystemEvents.PowerModeChanged> che si verifica ogni volta che viene apportata una modifica allo stato di alimentazione, ad esempio quando un utente sospende o riprende il sistema operativo oppure quando lo stato dell'alimentazione CA o lo stato della batteria cambia. La proprietà <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A> della classe <xref:System.Windows.Forms.SystemInformation> può essere utilizzata per eseguire una query per lo stato corrente, come illustrato nell'esempio di codice seguente.  
  
 [!code-csharp[PowerMode#1](~/samples/snippets/csharp/VS_Snippets_Winforms/powermode/cs/form1.cs#1)]
 [!code-vb[PowerMode#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/powermode/vb/form1.vb#1)]  
  
 Oltre alle enumerazioni di <xref:System.Windows.Forms.BatteryChargeStatus>, la proprietà <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A> contiene anche enumerazioni per determinare la capacità della batteria (<xref:System.Windows.Forms.PowerStatus.BatteryFullLifetime%2A>) e la percentuale di carica della batteria (<xref:System.Windows.Forms.PowerStatus.BatteryLifePercent%2A>, <xref:System.Windows.Forms.PowerStatus.BatteryLifeRemaining%2A>).  
  
 È possibile usare il metodo <xref:System.Windows.Forms.Application.SetSuspendState%2A> della <xref:System.Windows.Forms.Application> per attivare la modalità di sospensione o sospensione del computer. Se l'argomento `force` è impostato su `false`, il sistema operativo trasmette un evento a tutte le applicazioni che richiedono le autorizzazioni di sospensione. Se l'argomento `disableWakeEvent` è impostato su `true`, il sistema operativo Disabilita tutti gli eventi di riattivazione.  
  
 Nell'esempio di codice riportato di seguito viene illustrato come attivare la modalità di ibernazione di un computer.  
  
 [!code-csharp[PowerMode#2](~/samples/snippets/csharp/VS_Snippets_Winforms/powermode/cs/form1.cs#2)]
 [!code-vb[PowerMode#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/powermode/vb/form1.vb#2)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:Microsoft.Win32.SystemEvents.PowerModeChanged>
- <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A>
- <xref:System.Windows.Forms.Application.SetSuspendState%2A>
- <xref:Microsoft.Win32.SystemEvents.SessionSwitch>
