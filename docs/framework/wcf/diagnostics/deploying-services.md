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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 75069b00fa07078ff0eb2d49e64f046d5415d154
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="deploying-services"></a><span data-ttu-id="fd972-102">Distribuzione di servizi</span><span class="sxs-lookup"><span data-stu-id="fd972-102">Deploying Services</span></span>
<span data-ttu-id="fd972-103">In questo argomento viene illustrato come distribuire un'applicazione [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] in un ambiente di runtime.</span><span class="sxs-lookup"><span data-stu-id="fd972-103">This topic describes how you can deploy a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] application to a run-time environment.</span></span>  
  
## <a name="choosing-the-hosting-environment-for-your-application"></a><span data-ttu-id="fd972-104">Scelta dell'ambiente di hosting per l'applicazione</span><span class="sxs-lookup"><span data-stu-id="fd972-104">Choosing the Hosting Environment for Your Application</span></span>  
 <span data-ttu-id="fd972-105">I servizi [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] sono progettati per essere eseguiti in qualsiasi processo di Windows che supporta codice gestito.</span><span class="sxs-lookup"><span data-stu-id="fd972-105">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services are designed to run in any Windows process that supports managed code.</span></span> <span data-ttu-id="fd972-106">Per diventare attivo, un servizio deve essere ospitato all'interno di un ambiente di runtime che lo crea e ne controlla il contesto e la durata.</span><span class="sxs-lookup"><span data-stu-id="fd972-106">To become active, a service must be hosted within a run-time environment that creates it and controls its context and lifetime.</span></span> <span data-ttu-id="fd972-107">Le opzioni di hosting vanno dall'esecuzione in una semplice applicazione console ad ambienti server come un servizio Windows, Internet Information Services (IIS) o all'interno di un processo di lavoro gestito da Windows Activation Service (WAS).</span><span class="sxs-lookup"><span data-stu-id="fd972-107">Hosting options range from running inside the simplest console application to server environments like a Windows service, Internet Information Services (IIS), or within a worker process managed by the Windows Activation Service (WAS).</span></span> <span data-ttu-id="fd972-108">Per esaminare le diverse opzioni di hosting per il [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] applicazione, vedere [servizi di Hosting](../../../../docs/framework/wcf/hosting-services.md).</span><span class="sxs-lookup"><span data-stu-id="fd972-108">To review the different hosting options for your [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] application, see [Hosting Services](../../../../docs/framework/wcf/hosting-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd972-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fd972-109">See Also</span></span>  
 [<span data-ttu-id="fd972-110">Hosting</span><span class="sxs-lookup"><span data-stu-id="fd972-110">Hosting</span></span>](../../../../docs/framework/wcf/feature-details/hosting.md)  
 [<span data-ttu-id="fd972-111">Servizi di hosting</span><span class="sxs-lookup"><span data-stu-id="fd972-111">Hosting Services</span></span>](../../../../docs/framework/wcf/hosting-services.md)
