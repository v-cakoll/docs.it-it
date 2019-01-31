---
title: 'Risoluzione dei problemi: Debug dei servizi Windows'
ms.date: 03/30/2017
helpviewer_keywords:
- debugging Windows Service applications
- debugging [Visual Studio], Windows services
- troubleshooting service applications
- services, troubleshooting
- troubleshooting debugging, Windows Services
- Windows Service applications, debugging
- services, debugging
- Windows Service applications, troubleshooting
ms.assetid: cf859d4c-f04c-4cb7-81e3-bc7de8bea190
author: ghogen
ms.openlocfilehash: cdffb3a8ce9c5119a0a17a8bc7e6ca78276423f4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54745675"
---
# <a name="troubleshooting-debugging-windows-services"></a><span data-ttu-id="d8671-102">Risoluzione dei problemi: Debug dei servizi Windows</span><span class="sxs-lookup"><span data-stu-id="d8671-102">Troubleshooting: Debugging Windows Services</span></span>
<span data-ttu-id="d8671-103">Quando si esegue il debug di un'applicazione di servizio Windows, il servizio e **Windows Service Manager** interagiscono.</span><span class="sxs-lookup"><span data-stu-id="d8671-103">When you debug a Windows service application, your service and the **Windows Service Manager** interact.</span></span> <span data-ttu-id="d8671-104">**Service Manager** avvia il servizio chiamando il metodo <xref:System.ServiceProcess.ServiceBase.OnStart%2A>, quindi attende 30 secondi che il metodo <xref:System.ServiceProcess.ServiceBase.OnStart%2A> restituisca il controllo.</span><span class="sxs-lookup"><span data-stu-id="d8671-104">The **Service Manager** starts your service by calling the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method, and then waits 30 seconds for the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method to return.</span></span> <span data-ttu-id="d8671-105">Se il metodo non restituisce il controllo entro questo periodo, il gestore visualizza un errore per indicare che non è possibile avviare il servizio.</span><span class="sxs-lookup"><span data-stu-id="d8671-105">If the method does not return in this time, the manager shows an error that the service cannot be started.</span></span>  
  
 <span data-ttu-id="d8671-106">Quando si esegue il debug del metodo <xref:System.ServiceProcess.ServiceBase.OnStart%2A> come descritto in [Procedura: Eseguire il debug di applicazioni di servizio di Windows](../../../docs/framework/windows-services/how-to-debug-windows-service-applications.md), è necessario essere a conoscenza di questo periodo di 30 secondi.</span><span class="sxs-lookup"><span data-stu-id="d8671-106">When you debug the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method as described in [How to: Debug Windows Service Applications](../../../docs/framework/windows-services/how-to-debug-windows-service-applications.md), you must be aware of this 30-second period.</span></span> <span data-ttu-id="d8671-107">Se si inserisce un punto di interruzione nel metodo <xref:System.ServiceProcess.ServiceBase.OnStart%2A> e non si procede entro 30 secondi, il gestore non avvierà il servizio.</span><span class="sxs-lookup"><span data-stu-id="d8671-107">If you place a breakpoint in the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method and do not step through it in 30 seconds, the manager will not start the service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8671-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d8671-108">See also</span></span>
- [<span data-ttu-id="d8671-109">Procedura: Eseguire il debug di applicazioni di servizio di Windows</span><span class="sxs-lookup"><span data-stu-id="d8671-109">How to: Debug Windows Service Applications</span></span>](../../../docs/framework/windows-services/how-to-debug-windows-service-applications.md)
- [<span data-ttu-id="d8671-110">Introduzione alle applicazioni di servizio Windows</span><span class="sxs-lookup"><span data-stu-id="d8671-110">Introduction to Windows Service Applications</span></span>](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)
