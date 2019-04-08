---
title: Distribuzione di servizi
ms.date: 03/30/2017
ms.assetid: ac361bfb-017d-4da9-a2d7-fc0fb72d65bb
ms.openlocfilehash: 2c3cd17b597fafcd02b9155089bc583fafbc9dea
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59085760"
---
# <a name="deploying-services"></a><span data-ttu-id="bf280-102">Distribuzione di servizi</span><span class="sxs-lookup"><span data-stu-id="bf280-102">Deploying Services</span></span>
<span data-ttu-id="bf280-103">Questo argomento descrive come è possibile distribuire un'applicazione Windows Communication Foundation (WCF) in un ambiente di runtime.</span><span class="sxs-lookup"><span data-stu-id="bf280-103">This topic describes how you can deploy a Windows Communication Foundation (WCF) application to a run-time environment.</span></span>  
  
## <a name="choosing-the-hosting-environment-for-your-application"></a><span data-ttu-id="bf280-104">Scelta dell'ambiente di hosting per l'applicazione</span><span class="sxs-lookup"><span data-stu-id="bf280-104">Choosing the Hosting Environment for Your Application</span></span>  
 <span data-ttu-id="bf280-105">Servizi WCF sono progettati per l'esecuzione in qualsiasi processo Windows che supporta codice gestito.</span><span class="sxs-lookup"><span data-stu-id="bf280-105">WCF services are designed to run in any Windows process that supports managed code.</span></span> <span data-ttu-id="bf280-106">Per diventare attivo, un servizio deve essere ospitato all'interno di un ambiente di runtime che lo crea e ne controlla il contesto e la durata.</span><span class="sxs-lookup"><span data-stu-id="bf280-106">To become active, a service must be hosted within a run-time environment that creates it and controls its context and lifetime.</span></span> <span data-ttu-id="bf280-107">Le opzioni di hosting vanno dall'esecuzione in una semplice applicazione console ad ambienti server come un servizio Windows, Internet Information Services (IIS) o all'interno di un processo di lavoro gestito da Windows Activation Service (WAS).</span><span class="sxs-lookup"><span data-stu-id="bf280-107">Hosting options range from running inside the simplest console application to server environments like a Windows service, Internet Information Services (IIS), or within a worker process managed by the Windows Activation Service (WAS).</span></span> <span data-ttu-id="bf280-108">Per le diverse opzioni di hosting per l'applicazione WCF, vedere [servizi di Hosting](../../../../docs/framework/wcf/hosting-services.md).</span><span class="sxs-lookup"><span data-stu-id="bf280-108">To review the different hosting options for your WCF application, see [Hosting Services](../../../../docs/framework/wcf/hosting-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf280-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bf280-109">See also</span></span>

- [<span data-ttu-id="bf280-110">Hosting</span><span class="sxs-lookup"><span data-stu-id="bf280-110">Hosting</span></span>](../../../../docs/framework/wcf/feature-details/hosting.md)
- [<span data-ttu-id="bf280-111">Servizi host</span><span class="sxs-lookup"><span data-stu-id="bf280-111">Hosting Services</span></span>](../../../../docs/framework/wcf/hosting-services.md)
