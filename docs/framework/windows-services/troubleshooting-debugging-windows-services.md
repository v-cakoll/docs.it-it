---
title: 'Risoluzione dei problemi: debug dei servizi Windows'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "8"
author: ghogen
ms.author: ghogen
manager: douge
ms.openlocfilehash: 51c28f6e9b6fa2974fb9861716b2c9fc2a38fe1a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="troubleshooting-debugging-windows-services"></a><span data-ttu-id="ab187-102">Risoluzione dei problemi: debug dei servizi Windows</span><span class="sxs-lookup"><span data-stu-id="ab187-102">Troubleshooting: Debugging Windows Services</span></span>
<span data-ttu-id="ab187-103">Quando si esegue il debug di un'applicazione di servizio Windows, il servizio e **Windows Service Manager** interagire.</span><span class="sxs-lookup"><span data-stu-id="ab187-103">When you debug a Windows service application, your service and the **Windows Service Manager** interact.</span></span> <span data-ttu-id="ab187-104">Il **Service Manager** avvia il servizio chiamando il <xref:System.ServiceProcess.ServiceBase.OnStart%2A> (metodo), quindi attende 30 secondi per il <xref:System.ServiceProcess.ServiceBase.OnStart%2A> restituzione del metodo.</span><span class="sxs-lookup"><span data-stu-id="ab187-104">The **Service Manager** starts your service by calling the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method, and then waits 30 seconds for the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method to return.</span></span> <span data-ttu-id="ab187-105">Se il metodo non restituisce in questo periodo, il gestore viene visualizzato un errore che può essere avviato il servizio.</span><span class="sxs-lookup"><span data-stu-id="ab187-105">If the method does not return in this time, the manager shows an error that the service cannot be started.</span></span>  
  
 <span data-ttu-id="ab187-106">Quando esegue il debug la <xref:System.ServiceProcess.ServiceBase.OnStart%2A> (metodo), come descritto in [procedura: eseguire il Debug di applicazioni di servizio Windows](../../../docs/framework/windows-services/how-to-debug-windows-service-applications.md), è necessario essere a conoscenza di questo periodo di 30 secondi.</span><span class="sxs-lookup"><span data-stu-id="ab187-106">When you debug the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method as described in [How to: Debug Windows Service Applications](../../../docs/framework/windows-services/how-to-debug-windows-service-applications.md), you must be aware of this 30-second period.</span></span> <span data-ttu-id="ab187-107">Se si inserisce un punto di interruzione di <xref:System.ServiceProcess.ServiceBase.OnStart%2A> metodo e non eseguire un'istruzione entro 30 secondi, il gestore non avvierà il servizio.</span><span class="sxs-lookup"><span data-stu-id="ab187-107">If you place a breakpoint in the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method and do not step through it in 30 seconds, the manager will not start the service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab187-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ab187-108">See Also</span></span>  
 [<span data-ttu-id="ab187-109">Procedura: eseguire il Debug di applicazioni di servizio Windows</span><span class="sxs-lookup"><span data-stu-id="ab187-109">How to: Debug Windows Service Applications</span></span>](../../../docs/framework/windows-services/how-to-debug-windows-service-applications.md)  
 [<span data-ttu-id="ab187-110">Introduzione alle applicazioni di servizio Windows</span><span class="sxs-lookup"><span data-stu-id="ab187-110">Introduction to Windows Service Applications</span></span>](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)
