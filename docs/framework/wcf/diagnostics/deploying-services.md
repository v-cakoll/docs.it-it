---
title: Distribuzione di servizi
ms.date: 03/30/2017
ms.assetid: ac361bfb-017d-4da9-a2d7-fc0fb72d65bb
ms.openlocfilehash: 17773dc7a6bbed1b88c9324d27a937166e0d9f6b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54678980"
---
# <a name="deploying-services"></a><span data-ttu-id="3e776-102">Distribuzione di servizi</span><span class="sxs-lookup"><span data-stu-id="3e776-102">Deploying Services</span></span>
<span data-ttu-id="3e776-103">Questo argomento descrive come è possibile distribuire un'applicazione Windows Communication Foundation (WCF) in un ambiente di runtime.</span><span class="sxs-lookup"><span data-stu-id="3e776-103">This topic describes how you can deploy a Windows Communication Foundation (WCF) application to a run-time environment.</span></span>  
  
## <a name="choosing-the-hosting-environment-for-your-application"></a><span data-ttu-id="3e776-104">Scelta dell'ambiente di hosting per l'applicazione</span><span class="sxs-lookup"><span data-stu-id="3e776-104">Choosing the Hosting Environment for Your Application</span></span>  
 <span data-ttu-id="3e776-105">Servizi WCF sono progettati per l'esecuzione in qualsiasi processo Windows che supporta codice gestito.</span><span class="sxs-lookup"><span data-stu-id="3e776-105">WCF services are designed to run in any Windows process that supports managed code.</span></span> <span data-ttu-id="3e776-106">Per diventare attivo, un servizio deve essere ospitato all'interno di un ambiente di runtime che lo crea e ne controlla il contesto e la durata.</span><span class="sxs-lookup"><span data-stu-id="3e776-106">To become active, a service must be hosted within a run-time environment that creates it and controls its context and lifetime.</span></span> <span data-ttu-id="3e776-107">Le opzioni di hosting vanno dall'esecuzione in una semplice applicazione console ad ambienti server come un servizio Windows, Internet Information Services (IIS) o all'interno di un processo di lavoro gestito da Windows Activation Service (WAS).</span><span class="sxs-lookup"><span data-stu-id="3e776-107">Hosting options range from running inside the simplest console application to server environments like a Windows service, Internet Information Services (IIS), or within a worker process managed by the Windows Activation Service (WAS).</span></span> <span data-ttu-id="3e776-108">Per le diverse opzioni di hosting per l'applicazione WCF, vedere [servizi di Hosting](../../../../docs/framework/wcf/hosting-services.md).</span><span class="sxs-lookup"><span data-stu-id="3e776-108">To review the different hosting options for your WCF application, see [Hosting Services](../../../../docs/framework/wcf/hosting-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e776-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3e776-109">See also</span></span>
- [<span data-ttu-id="3e776-110">Hosting</span><span class="sxs-lookup"><span data-stu-id="3e776-110">Hosting</span></span>](../../../../docs/framework/wcf/feature-details/hosting.md)
- [<span data-ttu-id="3e776-111">Servizi di hosting</span><span class="sxs-lookup"><span data-stu-id="3e776-111">Hosting Services</span></span>](../../../../docs/framework/wcf/hosting-services.md)
