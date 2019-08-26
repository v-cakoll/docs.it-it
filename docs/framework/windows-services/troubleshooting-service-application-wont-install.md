---
title: "Risoluzione dei problemi: Impossibile installare l'applicazione di servizio"
ms.date: 03/30/2017
helpviewer_keywords:
- troubleshooting service applications
- services, troubleshooting
- services, debugging
- Windows NT services, troubleshooting
- troubleshooting NT services
- Windows Service applications, troubleshooting
ms.assetid: 45c48e2e-b97d-44bc-8896-14f328e0ce33
author: ghogen
ms.openlocfilehash: d04a0ddcef9ff7c31abd422f7f9fba34e804d2b1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69935418"
---
# <a name="troubleshooting-service-application-wont-install"></a><span data-ttu-id="353cc-102">Risoluzione dei problemi: Impossibile installare l'applicazione di servizio</span><span class="sxs-lookup"><span data-stu-id="353cc-102">Troubleshooting: Service Application Won't Install</span></span>
<span data-ttu-id="353cc-103">Se l'applicazione di servizio non viene installata correttamente, verificare che la proprietà <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> per la classe del servizio sia impostata sullo stesso valore indicato nel programma di installazione per il servizio.</span><span class="sxs-lookup"><span data-stu-id="353cc-103">If your service application will not install correctly, check to make sure that the <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> property for the service class is set to the same value as is shown in the installer for that service.</span></span> <span data-ttu-id="353cc-104">Il valore deve essere uguale in entrambe le istanze per ottenere la corretta installazione del servizio.</span><span class="sxs-lookup"><span data-stu-id="353cc-104">The value must be the same in both instances in order for your service to install correctly.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="353cc-105">È anche possibile esaminare i log di installazione per ottenere informazioni sul processo di installazione.</span><span class="sxs-lookup"><span data-stu-id="353cc-105">You can also look at the installation logs to get feedback on the installation process.</span></span>  
  
 <span data-ttu-id="353cc-106">Controllare inoltre se esiste un altro servizio con lo stesso nome già installato.</span><span class="sxs-lookup"><span data-stu-id="353cc-106">You should also check to determine whether you have another service with the same name already installed.</span></span> <span data-ttu-id="353cc-107">I nomi di servizio devono essere univoci per l'esito positivo dell'installazione.</span><span class="sxs-lookup"><span data-stu-id="353cc-107">Service names must be unique for installation to succeed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="353cc-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="353cc-108">See also</span></span>

- [<span data-ttu-id="353cc-109">Introduzione alle applicazioni di servizio Windows</span><span class="sxs-lookup"><span data-stu-id="353cc-109">Introduction to Windows Service Applications</span></span>](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)
