---
title: "Risoluzione dei problemi: Opportunità vinte applicazione di servizio &#39; installare t"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- troubleshooting service applications
- services, troubleshooting
- services, debugging
- Windows NT services, troubleshooting
- troubleshooting NT services
- Windows Service applications, troubleshooting
ms.assetid: 45c48e2e-b97d-44bc-8896-14f328e0ce33
caps.latest.revision: "8"
author: ghogen
ms.author: ghogen
manager: douge
ms.openlocfilehash: 82eb870761a7865385631cd9961ce99e0b0d3502
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="troubleshooting-service-application-won39t-install"></a><span data-ttu-id="04291-102">Risoluzione dei problemi: Opportunità vinte applicazione di servizio &#39; installare t</span><span class="sxs-lookup"><span data-stu-id="04291-102">Troubleshooting: Service Application Won&#39;t Install</span></span>
<span data-ttu-id="04291-103">Se l'applicazione di servizio non verrà installato correttamente, verificare che il <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> proprietà per la classe del servizio è impostata sullo stesso valore, come illustrato nel programma di installazione per il servizio.</span><span class="sxs-lookup"><span data-stu-id="04291-103">If your service application will not install correctly, check to make sure that the <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> property for the service class is set to the same value as is shown in the installer for that service.</span></span> <span data-ttu-id="04291-104">Il valore deve essere la stessa in entrambe le istanze del servizio installare correttamente.</span><span class="sxs-lookup"><span data-stu-id="04291-104">The value must be the same in both instances in order for your service to install correctly.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="04291-105">È anche possibile esaminare i registri di installazione per ottenere informazioni sul processo di installazione.</span><span class="sxs-lookup"><span data-stu-id="04291-105">You can also look at the installation logs to get feedback on the installation process.</span></span>  
  
 <span data-ttu-id="04291-106">Controllare inoltre per determinare se si dispone di un altro servizio con lo stesso nome già installato.</span><span class="sxs-lookup"><span data-stu-id="04291-106">You should also check to determine whether you have another service with the same name already installed.</span></span> <span data-ttu-id="04291-107">I nomi di servizio devono essere univoci per l'installazione abbia esito positivo.</span><span class="sxs-lookup"><span data-stu-id="04291-107">Service names must be unique for installation to succeed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04291-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="04291-108">See Also</span></span>  
 [<span data-ttu-id="04291-109">Introduzione alle applicazioni di servizio Windows</span><span class="sxs-lookup"><span data-stu-id="04291-109">Introduction to Windows Service Applications</span></span>](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)
