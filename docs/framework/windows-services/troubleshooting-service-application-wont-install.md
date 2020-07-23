---
title: "Risoluzione dei problemi: Impossibile installare l'applicazione di servizio"
description: Eseguire la risoluzione dei problemi se l'applicazione di servizio non verrà installata. Verificare che la proprietà ServiceName per la classe del servizio sia impostata correttamente.
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
ms.openlocfilehash: 4a57fb6975a6ded48abf7c8fd7eacec16e4f94d8
ms.sourcegitcommit: 40de8df14289e1e05b40d6e5c1daabd3c286d70c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/22/2020
ms.locfileid: "86925527"
---
# <a name="troubleshooting-service-application-wont-install"></a><span data-ttu-id="2e1ec-104">Risoluzione dei problemi: Impossibile installare l'applicazione di servizio</span><span class="sxs-lookup"><span data-stu-id="2e1ec-104">Troubleshooting: Service Application Won't Install</span></span>
<span data-ttu-id="2e1ec-105">Se l'applicazione di servizio non viene installata correttamente, verificare che la proprietà <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> per la classe del servizio sia impostata sullo stesso valore indicato nel programma di installazione per il servizio.</span><span class="sxs-lookup"><span data-stu-id="2e1ec-105">If your service application will not install correctly, check to make sure that the <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> property for the service class is set to the same value as is shown in the installer for that service.</span></span> <span data-ttu-id="2e1ec-106">Il valore deve essere uguale in entrambe le istanze per ottenere la corretta installazione del servizio.</span><span class="sxs-lookup"><span data-stu-id="2e1ec-106">The value must be the same in both instances in order for your service to install correctly.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2e1ec-107">È anche possibile esaminare i log di installazione per ottenere informazioni sul processo di installazione.</span><span class="sxs-lookup"><span data-stu-id="2e1ec-107">You can also look at the installation logs to get feedback on the installation process.</span></span>  
  
 <span data-ttu-id="2e1ec-108">Controllare inoltre se esiste un altro servizio con lo stesso nome già installato.</span><span class="sxs-lookup"><span data-stu-id="2e1ec-108">You should also check to determine whether you have another service with the same name already installed.</span></span> <span data-ttu-id="2e1ec-109">I nomi di servizio devono essere univoci per l'esito positivo dell'installazione.</span><span class="sxs-lookup"><span data-stu-id="2e1ec-109">Service names must be unique for installation to succeed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e1ec-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2e1ec-110">See also</span></span>

- [<span data-ttu-id="2e1ec-111">Introduzione alle applicazioni di servizio Windows</span><span class="sxs-lookup"><span data-stu-id="2e1ec-111">Introduction to Windows Service Applications</span></span>](introduction-to-windows-service-applications.md)
