---
title: Distribuzione di servizi
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ac361bfb-017d-4da9-a2d7-fc0fb72d65bb
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6e32570b381d6cab4326a13246dfe053b5032589
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="deploying-services"></a><span data-ttu-id="e1eb9-102">Distribuzione di servizi</span><span class="sxs-lookup"><span data-stu-id="e1eb9-102">Deploying Services</span></span>
<span data-ttu-id="e1eb9-103">In questo argomento viene illustrato come distribuire un'applicazione [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] in un ambiente di runtime.</span><span class="sxs-lookup"><span data-stu-id="e1eb9-103">This topic describes how you can deploy a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] application to a run-time environment.</span></span>  
  
## <a name="choosing-the-hosting-environment-for-your-application"></a><span data-ttu-id="e1eb9-104">Scelta dell'ambiente di hosting per l'applicazione</span><span class="sxs-lookup"><span data-stu-id="e1eb9-104">Choosing the Hosting Environment for Your Application</span></span>  
 <span data-ttu-id="e1eb9-105">I servizi [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] sono progettati per essere eseguiti in qualsiasi processo di Windows che supporta codice gestito.</span><span class="sxs-lookup"><span data-stu-id="e1eb9-105">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services are designed to run in any Windows process that supports managed code.</span></span> <span data-ttu-id="e1eb9-106">Per diventare attivo, un servizio deve essere ospitato all'interno di un ambiente di runtime che lo crea e ne controlla il contesto e la durata.</span><span class="sxs-lookup"><span data-stu-id="e1eb9-106">To become active, a service must be hosted within a run-time environment that creates it and controls its context and lifetime.</span></span> <span data-ttu-id="e1eb9-107">Le opzioni di hosting vanno dall'esecuzione in una semplice applicazione console ad ambienti server come un servizio Windows, Internet Information Services (IIS) o all'interno di un processo di lavoro gestito da Windows Activation Service (WAS).</span><span class="sxs-lookup"><span data-stu-id="e1eb9-107">Hosting options range from running inside the simplest console application to server environments like a Windows service, Internet Information Services (IIS), or within a worker process managed by the Windows Activation Service (WAS).</span></span> <span data-ttu-id="e1eb9-108">Per esaminare le diverse opzioni di hosting per il [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] applicazione, vedere [servizi di Hosting](../../../../docs/framework/wcf/hosting-services.md).</span><span class="sxs-lookup"><span data-stu-id="e1eb9-108">To review the different hosting options for your [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] application, see [Hosting Services](../../../../docs/framework/wcf/hosting-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1eb9-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e1eb9-109">See Also</span></span>  
 [<span data-ttu-id="e1eb9-110">Hosting</span><span class="sxs-lookup"><span data-stu-id="e1eb9-110">Hosting</span></span>](../../../../docs/framework/wcf/feature-details/hosting.md)  
 [<span data-ttu-id="e1eb9-111">Servizi di hosting</span><span class="sxs-lookup"><span data-stu-id="e1eb9-111">Hosting Services</span></span>](../../../../docs/framework/wcf/hosting-services.md)
