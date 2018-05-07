---
title: Risparmio energia in Windows Form
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- battery states
- power states
ms.assetid: ad04a801-5682-4d88-92c5-26eb9cdb209a
ms.openlocfilehash: 845cc9c910d63dfc7460bba0d5368b5b1e63efcd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="power-management-in-windows-forms"></a>Risparmio energia in Windows Form
Le applicazioni Windows Forms possono sfruttare le funzionalità di risparmio energia nel sistema operativo Windows. Le applicazioni possono monitorare lo stato di alimentazione di un computer e intraprendere l'azione quando si verifica un cambiamento di stato. Ad esempio, se l'applicazione è in esecuzione su un computer portatile, è consigliabile disabilitare determinate funzionalità dell'applicazione quando scende di carica della batteria del computer in un determinato livello.  
  
 Il [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] fornisce un <xref:Microsoft.Win32.SystemEvents.PowerModeChanged> evento che si verifica ogni volta che viene apportata una modifica dello stato di alimentazione, ad esempio quando un utente sospende o riprende il sistema operativo, o quando lo stato dell'alimentazione CA o lo stato della batteria cambia. Il <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A> proprietà del <xref:System.Windows.Forms.SystemInformation> classe può essere utilizzato per eseguire query per lo stato corrente, come illustrato nell'esempio di codice seguente.  
  
 [!code-csharp[PowerMode#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/powermode/cs/form1.cs#1)]
 [!code-vb[PowerMode#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/powermode/vb/form1.vb#1)]  
  
 Oltre il <xref:System.Windows.Forms.BatteryChargeStatus> enumerazioni, le <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A> proprietà contiene anche le enumerazioni per determinare la capacità della batteria (<xref:System.Windows.Forms.PowerStatus.BatteryFullLifetime%2A>) e percentuale di carica batteria (<xref:System.Windows.Forms.PowerStatus.BatteryLifePercent%2A>, <xref:System.Windows.Forms.PowerStatus.BatteryLifeRemaining%2A>).  
  
 È possibile utilizzare il <xref:System.Windows.Forms.Application.SetSuspendState%2A> metodo il <xref:System.Windows.Forms.Application> per impostare un computer in modalità di sospensione. Se il `force` argomento è impostato su `false`, il sistema operativo verrà trasmesso un evento a tutte le applicazioni che richiede l'autorizzazione di sospensione. Se il `disableWakeEvent` argomento è impostato su `true`, il sistema operativo Disabilita tutti gli eventi di riattivazione.  
  
 Esempio di codice riportato di seguito viene illustrato come inserire un computer in sospensione.  
  
 [!code-csharp[PowerMode#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/powermode/cs/form1.cs#2)]
 [!code-vb[PowerMode#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/powermode/vb/form1.vb#2)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:Microsoft.Win32.SystemEvents.PowerModeChanged>  
 <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A>  
 <xref:System.Windows.Forms.Application.SetSuspendState%2A>  
 <xref:Microsoft.Win32.SystemEvents.SessionSwitch>
