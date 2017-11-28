---
title: Risparmio energia in Windows Form
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- battery states
- power states
ms.assetid: ad04a801-5682-4d88-92c5-26eb9cdb209a
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e12f39a63a4f81e6deec4512a4e18ad2bda7e5e0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="power-management-in-windows-forms"></a><span data-ttu-id="de92d-102">Risparmio energia in Windows Form</span><span class="sxs-lookup"><span data-stu-id="de92d-102">Power Management in Windows Forms</span></span>
<span data-ttu-id="de92d-103">Le applicazioni Windows Forms possono sfruttare le funzionalità di risparmio energia nel sistema operativo Windows.</span><span class="sxs-lookup"><span data-stu-id="de92d-103">Your Windows Forms applications can take advantage of the power management features in the Windows operating system.</span></span> <span data-ttu-id="de92d-104">Le applicazioni possono monitorare lo stato di alimentazione di un computer e intraprendere l'azione quando si verifica un cambiamento di stato.</span><span class="sxs-lookup"><span data-stu-id="de92d-104">Your applications can monitor the power status of a computer and take action when a status change occurs.</span></span> <span data-ttu-id="de92d-105">Ad esempio, se l'applicazione è in esecuzione su un computer portatile, è consigliabile disabilitare determinate funzionalità dell'applicazione quando scende di carica della batteria del computer in un determinato livello.</span><span class="sxs-lookup"><span data-stu-id="de92d-105">For example, if your application is running on a portable computer, you might want to disable certain features in your application when the computer's battery charge falls under a certain level.</span></span>  
  
 <span data-ttu-id="de92d-106">Il [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] fornisce un <xref:Microsoft.Win32.SystemEvents.PowerModeChanged> evento che si verifica ogni volta che viene apportata una modifica dello stato di alimentazione, ad esempio quando un utente sospende o riprende il sistema operativo, o quando lo stato dell'alimentazione CA o lo stato della batteria cambia.</span><span class="sxs-lookup"><span data-stu-id="de92d-106">The [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] provides a <xref:Microsoft.Win32.SystemEvents.PowerModeChanged> event that occurs whenever there is a change in power status, such as when a user suspends or resumes the operating system, or when the AC power status or battery status changes.</span></span> <span data-ttu-id="de92d-107">Il <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A> proprietà del <xref:System.Windows.Forms.SystemInformation> classe può essere utilizzato per eseguire query per lo stato corrente, come illustrato nell'esempio di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="de92d-107">The <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A> property of the <xref:System.Windows.Forms.SystemInformation> class can be used to query for the current status, as shown in the following code example.</span></span>  
  
 [!code-csharp[PowerMode#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/powermode/cs/form1.cs#1)]
 [!code-vb[PowerMode#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/powermode/vb/form1.vb#1)]  
  
 <span data-ttu-id="de92d-108">Oltre il <xref:System.Windows.Forms.BatteryChargeStatus> enumerazioni, le <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A> proprietà contiene anche le enumerazioni per determinare la capacità della batteria (<xref:System.Windows.Forms.PowerStatus.BatteryFullLifetime%2A>) e percentuale di carica batteria (<xref:System.Windows.Forms.PowerStatus.BatteryLifePercent%2A>, <xref:System.Windows.Forms.PowerStatus.BatteryLifeRemaining%2A>).</span><span class="sxs-lookup"><span data-stu-id="de92d-108">Besides the <xref:System.Windows.Forms.BatteryChargeStatus> enumerations, the <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A> property also contains enumerations for determining battery capacity (<xref:System.Windows.Forms.PowerStatus.BatteryFullLifetime%2A>) and battery charge percentage (<xref:System.Windows.Forms.PowerStatus.BatteryLifePercent%2A>, <xref:System.Windows.Forms.PowerStatus.BatteryLifeRemaining%2A>).</span></span>  
  
 <span data-ttu-id="de92d-109">È possibile utilizzare il <xref:System.Windows.Forms.Application.SetSuspendState%2A> metodo il <xref:System.Windows.Forms.Application> per impostare un computer in modalità di sospensione.</span><span class="sxs-lookup"><span data-stu-id="de92d-109">You can use the <xref:System.Windows.Forms.Application.SetSuspendState%2A> method of the <xref:System.Windows.Forms.Application> to put a computer into hibernation or suspend mode.</span></span> <span data-ttu-id="de92d-110">Se il `force` argomento è impostato su `false`, il sistema operativo verrà trasmesso un evento a tutte le applicazioni che richiede l'autorizzazione di sospensione.</span><span class="sxs-lookup"><span data-stu-id="de92d-110">If the `force` argument is set to `false`, the operating system will broadcast an event to all applications requesting permission to suspend.</span></span> <span data-ttu-id="de92d-111">Se il `disableWakeEvent` argomento è impostato su `true`, il sistema operativo Disabilita tutti gli eventi di riattivazione.</span><span class="sxs-lookup"><span data-stu-id="de92d-111">If the `disableWakeEvent` argument is set to `true`, the operating system disables all wake events.</span></span>  
  
 <span data-ttu-id="de92d-112">Esempio di codice riportato di seguito viene illustrato come inserire un computer in sospensione.</span><span class="sxs-lookup"><span data-stu-id="de92d-112">The following code example demonstrates how to put a computer into hibernation.</span></span>  
  
 [!code-csharp[PowerMode#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/powermode/cs/form1.cs#2)]
 [!code-vb[PowerMode#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/powermode/vb/form1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="de92d-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="de92d-113">See Also</span></span>  
 <xref:Microsoft.Win32.SystemEvents.PowerModeChanged>  
 <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A>  
 <xref:System.Windows.Forms.Application.SetSuspendState%2A>  
 <xref:Microsoft.Win32.SystemEvents.SessionSwitch>
