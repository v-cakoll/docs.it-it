---
title: Distribuzione di servizi
ms.date: 03/30/2017
ms.assetid: ac361bfb-017d-4da9-a2d7-fc0fb72d65bb
ms.openlocfilehash: 4d9efcb4da064021d93345285982c0cbd29dde2e
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2018
---
# <a name="deploying-services"></a><span data-ttu-id="6ee19-102">Distribuzione di servizi</span><span class="sxs-lookup"><span data-stu-id="6ee19-102">Deploying Services</span></span>
<span data-ttu-id="6ee19-103">In questo argomento viene descritto come è possibile distribuire un'applicazione Windows Communication Foundation (WCF) in un ambiente di runtime.</span><span class="sxs-lookup"><span data-stu-id="6ee19-103">This topic describes how you can deploy a Windows Communication Foundation (WCF) application to a run-time environment.</span></span>  
  
## <a name="choosing-the-hosting-environment-for-your-application"></a><span data-ttu-id="6ee19-104">Scelta dell'ambiente di hosting per l'applicazione</span><span class="sxs-lookup"><span data-stu-id="6ee19-104">Choosing the Hosting Environment for Your Application</span></span>  
 <span data-ttu-id="6ee19-105">Servizi WCF sono progettati per l'esecuzione in qualsiasi processo di Windows che supporta codice gestito.</span><span class="sxs-lookup"><span data-stu-id="6ee19-105">WCF services are designed to run in any Windows process that supports managed code.</span></span> <span data-ttu-id="6ee19-106">Per diventare attivo, un servizio deve essere ospitato all'interno di un ambiente di runtime che lo crea e ne controlla il contesto e la durata.</span><span class="sxs-lookup"><span data-stu-id="6ee19-106">To become active, a service must be hosted within a run-time environment that creates it and controls its context and lifetime.</span></span> <span data-ttu-id="6ee19-107">Le opzioni di hosting vanno dall'esecuzione in una semplice applicazione console ad ambienti server come un servizio Windows, Internet Information Services (IIS) o all'interno di un processo di lavoro gestito da Windows Activation Service (WAS).</span><span class="sxs-lookup"><span data-stu-id="6ee19-107">Hosting options range from running inside the simplest console application to server environments like a Windows service, Internet Information Services (IIS), or within a worker process managed by the Windows Activation Service (WAS).</span></span> <span data-ttu-id="6ee19-108">Per esaminare le diverse opzioni di hosting per l'applicazione WCF, vedere [servizi di Hosting](../../../../docs/framework/wcf/hosting-services.md).</span><span class="sxs-lookup"><span data-stu-id="6ee19-108">To review the different hosting options for your WCF application, see [Hosting Services](../../../../docs/framework/wcf/hosting-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ee19-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6ee19-109">See Also</span></span>  
 [<span data-ttu-id="6ee19-110">Hosting</span><span class="sxs-lookup"><span data-stu-id="6ee19-110">Hosting</span></span>](../../../../docs/framework/wcf/feature-details/hosting.md)  
 [<span data-ttu-id="6ee19-111">Servizi di hosting</span><span class="sxs-lookup"><span data-stu-id="6ee19-111">Hosting Services</span></span>](../../../../docs/framework/wcf/hosting-services.md)
