---
title: Distribuzione di servizi
ms.date: 03/30/2017
ms.assetid: ac361bfb-017d-4da9-a2d7-fc0fb72d65bb
ms.openlocfilehash: 684b781c568518cfb321d8021e4f7062e855e6aa
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798136"
---
# <a name="deploying-services"></a><span data-ttu-id="5c4d0-102">Distribuzione di servizi</span><span class="sxs-lookup"><span data-stu-id="5c4d0-102">Deploying Services</span></span>
<span data-ttu-id="5c4d0-103">In questo argomento viene descritto come distribuire un'applicazione Windows Communication Foundation (WCF) in un ambiente di Runtime.</span><span class="sxs-lookup"><span data-stu-id="5c4d0-103">This topic describes how you can deploy a Windows Communication Foundation (WCF) application to a run-time environment.</span></span>  
  
## <a name="choosing-the-hosting-environment-for-your-application"></a><span data-ttu-id="5c4d0-104">Scelta dell'ambiente di hosting per l'applicazione</span><span class="sxs-lookup"><span data-stu-id="5c4d0-104">Choosing the Hosting Environment for Your Application</span></span>  
 <span data-ttu-id="5c4d0-105">I servizi WCF sono progettati per essere eseguiti in qualsiasi processo di Windows che supporta il codice gestito.</span><span class="sxs-lookup"><span data-stu-id="5c4d0-105">WCF services are designed to run in any Windows process that supports managed code.</span></span> <span data-ttu-id="5c4d0-106">Per diventare attivo, un servizio deve essere ospitato all'interno di un ambiente di runtime che lo crea e ne controlla il contesto e la durata.</span><span class="sxs-lookup"><span data-stu-id="5c4d0-106">To become active, a service must be hosted within a run-time environment that creates it and controls its context and lifetime.</span></span> <span data-ttu-id="5c4d0-107">Le opzioni di hosting vanno dall'esecuzione in una semplice applicazione console ad ambienti server come un servizio Windows, Internet Information Services (IIS) o all'interno di un processo di lavoro gestito da Windows Activation Service (WAS).</span><span class="sxs-lookup"><span data-stu-id="5c4d0-107">Hosting options range from running inside the simplest console application to server environments like a Windows service, Internet Information Services (IIS), or within a worker process managed by the Windows Activation Service (WAS).</span></span> <span data-ttu-id="5c4d0-108">Per esaminare le diverse opzioni di hosting per l'applicazione WCF, vedere [servizi di hosting](../hosting-services.md).</span><span class="sxs-lookup"><span data-stu-id="5c4d0-108">To review the different hosting options for your WCF application, see [Hosting Services](../hosting-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c4d0-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5c4d0-109">See also</span></span>

- [<span data-ttu-id="5c4d0-110">Hosting</span><span class="sxs-lookup"><span data-stu-id="5c4d0-110">Hosting</span></span>](../feature-details/hosting.md)
- [<span data-ttu-id="5c4d0-111">Servizi di hosting</span><span class="sxs-lookup"><span data-stu-id="5c4d0-111">Hosting Services</span></span>](../hosting-services.md)
