---
title: Quando distribuire i contenitori di Windows in macchine virtuali di Azure (IaaS cloud)
description: Architettura di Microservizi .NET per le applicazioni nei contenitori .NET | Quando distribuire i contenitori di Windows in macchine virtuali di Azure (IaaS cloud)
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/26/2017
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 832faed135d5b8ec9f8ad0a6ca82b5fac0273284
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="when-to-deploy-windows-containers-to-azure-vms-iaas-cloud"></a><span data-ttu-id="57235-103">Quando distribuire i contenitori di Windows in macchine virtuali di Azure (IaaS cloud)</span><span class="sxs-lookup"><span data-stu-id="57235-103">When to deploy Windows Containers to Azure VMs (IaaS cloud)</span></span>

<span data-ttu-id="57235-104">Se l'organizzazione utilizza macchine virtuali di Azure, anche se si utilizza anche i contenitori di Windows, sono comunque trattare IaaS.</span><span class="sxs-lookup"><span data-stu-id="57235-104">If your organization is using Azure VMs, even if you are also using Windows Containers, you are still dealing with IaaS.</span></span> <span data-ttu-id="57235-105">Ciò significa che la gestione di operazioni dell'infrastruttura, patch del sistema operativo VM e la complessità dell'infrastruttura per applicazioni estremamente scalabili quando è necessario distribuire più macchine virtuali in un'infrastruttura con bilanciamento del carico.</span><span class="sxs-lookup"><span data-stu-id="57235-105">That means that dealing with infrastructure operations, VM OS patches, and infrastructure complexity for highly scalable applications when you need to deploy to multiple VMs in a load balanced infrastructure.</span></span> <span data-ttu-id="57235-106">Gli scenari principali per l'utilizzo di contenitori di Windows in una macchina virtuale di Azure sono:</span><span class="sxs-lookup"><span data-stu-id="57235-106">The main scenarios for using Windows Containers in an Azure VM are:</span></span>

-   <span data-ttu-id="57235-107">**Ambiente di sviluppo/test**: una macchina virtuale nel cloud è ideale per lo sviluppo e test nel cloud.</span><span class="sxs-lookup"><span data-stu-id="57235-107">**Dev/test environment**: A VM in the cloud is perfect for development and testing in the cloud.</span></span> <span data-ttu-id="57235-108">Rapidamente, è possibile creare o arrestare l'ambiente in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="57235-108">You can rapidly create or stop the environment depending on your needs.</span></span>

-   <span data-ttu-id="57235-109">**La scalabilità di piccola e Media deve**: In scenari in cui potrebbe essere necessario solo un paio di macchine virtuali per l'ambiente di produzione, gestisce un numero ridotto di macchine virtuali potrebbe essere conveniente fino a quando non è possibile spostare in ambienti di PaaS più avanzati, ad esempio orchestrators.</span><span class="sxs-lookup"><span data-stu-id="57235-109">**Small and medium scalability needs**: In scenarios where you might need just a couple of VMs for your production environment, managing a small number of VMs might be affordable until you can move to more advanced PaaS environments, like orchestrators.</span></span>

-   <span data-ttu-id="57235-110">**Ambiente di produzione con gli strumenti di distribuzione esistenti**: si potrebbe spostare da un ambiente locale in cui si è investito in strumenti per eseguire distribuzioni complesse per le macchine virtuali o i server bare metal (ad esempio Puppet o strumenti simili inclusi).</span><span class="sxs-lookup"><span data-stu-id="57235-110">**Production environment with existing deployment tools**: You might be moving from an on-premises environment in which you have invested in tools to make complex deployments to VMs or bare-metal servers (like Puppet or similar tools).</span></span> <span data-ttu-id="57235-111">Per spostare nel cloud con modifiche minime per le procedure di distribuzione di ambiente di produzione, si potrebbe continuare a utilizzare questi strumenti per distribuire macchine virtuali di Azure.</span><span class="sxs-lookup"><span data-stu-id="57235-111">To move to the cloud with minimal changes to production environment deployment procedures, you might continue to use those tools to deploy to Azure VMs.</span></span> <span data-ttu-id="57235-112">Tuttavia, è opportuno come utilizzare i contenitori di Windows come unità di distribuzione per migliorare l'esperienza di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="57235-112">However, you'll want to use Windows Containers as the unit of deployment to improve the deployment experience.</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="57235-113">[Precedente](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)
[Successivo](when-to-deploy-windows-containers-to-service-fabric.md)</span><span class="sxs-lookup"><span data-stu-id="57235-113">[Previous](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)
[Next](when-to-deploy-windows-containers-to-service-fabric.md)</span></span>
