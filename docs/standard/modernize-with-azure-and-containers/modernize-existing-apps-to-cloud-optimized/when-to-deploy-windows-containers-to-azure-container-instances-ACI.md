---
title: Quando distribuire i contenitori di Windows per Azure contenitore istanze ACI)
description: Modernizzare le applicazioni .NET esistenti con i contenitori di Windows e Cloud di Azure | Quando distribuire i contenitori di Windows per Azure contenitore istanze ACI)
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/29/2018
ms.openlocfilehash: 3dc23c96543d9611763b571105f52b150dfec06f
ms.sourcegitcommit: 88f251b08bf0718ce119f3d7302f514b74895038
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/10/2018
ms.locfileid: "33957951"
---
# <a name="when-to-deploy-windows-containers-to-azure-container-instances-aci"></a><span data-ttu-id="4ebc7-103">Quando distribuire i contenitori di Windows per Azure contenitore istanze ACI)</span><span class="sxs-lookup"><span data-stu-id="4ebc7-103">When to deploy Windows Containers to Azure Container Instances (ACI)</span></span>

<span data-ttu-id="4ebc7-104">Proposta di valore principale è che è possibile distribuire i contenitori immediatamente a tale e non è necessario mantenere tale ambiente Azure istanze di contenitori, non dovrai aggiornamento/patch il sistema operativo sulla o le macchine virtuali, tutti i che è trasparente e appena distribuire contenitori in un ambiente pronto all'uso.</span><span class="sxs-lookup"><span data-stu-id="4ebc7-104">Azure Container Instances main value proposition is that you can right away deploy containers to it and you don’t need to maintain that environment, you don’t need to upgrade/patch the underlaying operating system or VMs, all that is transparent and you just deploy containers into a ready-to-use environment.</span></span>

<span data-ttu-id="4ebc7-105">Motivi e degli scenari quando si desidera utilizzare ACI sono simili agli scenari principali quando si usano macchine virtuali di Azure con i contenitori, pertanto fondamentalmente, gli scenari principali per l'utilizzo di istanze di contenitori di Azure sono:</span><span class="sxs-lookup"><span data-stu-id="4ebc7-105">The reasons and scenarios when you would want to use ACI are similar to the main scenarios when you use Azure VMs with containers, so basically, the main scenarios for using Azure Container Instances are:</span></span>

-   <span data-ttu-id="4ebc7-106">**Scenari di sviluppo/Test**</span><span class="sxs-lookup"><span data-stu-id="4ebc7-106">**Dev/Test scenarios**</span></span>
-   <span data-ttu-id="4ebc7-107">**Automazione di attività**</span><span class="sxs-lookup"><span data-stu-id="4ebc7-107">**Task automation**</span></span>
-   <span data-ttu-id="4ebc7-108">**Agenti CI/CD-ROM**</span><span class="sxs-lookup"><span data-stu-id="4ebc7-108">**CI/CD agents**</span></span>
-   <span data-ttu-id="4ebc7-109">**Elaborazione batch di piccole e della scala**</span><span class="sxs-lookup"><span data-stu-id="4ebc7-109">**Small/scale batch processing**</span></span>
-   <span data-ttu-id="4ebc7-110">**Nelle App web semplici**</span><span class="sxs-lookup"><span data-stu-id="4ebc7-110">**Simple web apps**</span></span>

<span data-ttu-id="4ebc7-111">Lo scenario di App web semplici è uno scenario equo per ACI ma tener conto di poiché in ACI può avere solo un'istanza singolo contenitore per ogni immagine contenitore, non sarà possibile la disponibilità elevata e avere solo una scalabilità limitata.</span><span class="sxs-lookup"><span data-stu-id="4ebc7-111">The simple web apps scenario is a fair scenario for ACI but take into account that since in ACI you can only have a single container instance per container image, you won’t have high availability and only have limited scalability.</span></span>

<span data-ttu-id="4ebc7-112">Tuttavia, anche quando ACI è considerato infrastruttura in quanto fornisce solo le istanze singolo contenitore, è un enorme vantaggio rispetto alle normali macchine virtuali di Azure con Windows Server.</span><span class="sxs-lookup"><span data-stu-id="4ebc7-112">However, even when ACI is considered infrastructure because it just provides single container instances, there is a huge benefit compared to regular Azure VMs with Windows Server.</span></span> <span data-ttu-id="4ebc7-113">Con ACI, distribuire solo i contenitori in un ambiente di self-gestito e si paga solo per i contenitori.</span><span class="sxs-lookup"><span data-stu-id="4ebc7-113">With ACI, you just deploy the containers into a self-maintained environment and you just pay for those containers.</span></span> <span data-ttu-id="4ebc7-114">Non è necessario mantenere/aggiornamento/patch macchine virtuali, pertanto è una piattaforma molto migliorata per la maggior parte degli scenari in cui è possibile utilizzare le macchine virtuali con i contenitori.</span><span class="sxs-lookup"><span data-stu-id="4ebc7-114">You don’t need to maintain/update/patch VMs, so it is a much better platform for most scenarios where you might be using VMs with containers.</span></span> <span data-ttu-id="4ebc7-115">Utilizzando ACI è semplice, è sufficiente distribuire un contenitore, non è necessario creare un ambiente di VM distribuire solo i contenitori.</span><span class="sxs-lookup"><span data-stu-id="4ebc7-115">Using ACI is straight forward, you just deploy a container, there’s no need to create a VM environment you just deploy containers.</span></span>

<span data-ttu-id="4ebc7-116">I principali vantaggi di Azure contenitore istanze ACI () sono:</span><span class="sxs-lookup"><span data-stu-id="4ebc7-116">The main benefits of Azure Container Instances (ACI) are:</span></span>

-   <span data-ttu-id="4ebc7-117">Eseguire i contenitori di senza dover gestire i server</span><span class="sxs-lookup"><span data-stu-id="4ebc7-117">Run containers without managing servers</span></span>
-   <span data-ttu-id="4ebc7-118">Aumentare la flessibilità con i contenitori su richiesta</span><span class="sxs-lookup"><span data-stu-id="4ebc7-118">Increase agility with containers on demand</span></span>
-   <span data-ttu-id="4ebc7-119">Distribuzione di contenitori sul cloud con semplicità senza precedenti e la velocità, con un unico comando.</span><span class="sxs-lookup"><span data-stu-id="4ebc7-119">Deploy containers to the cloud with unprecedented simplicity and speed—with a single command.</span></span> 
-   <span data-ttu-id="4ebc7-120">Proteggere le applicazioni con isolamento hypervisor</span><span class="sxs-lookup"><span data-stu-id="4ebc7-120">Secure applications with hypervisor isolation</span></span>

<span data-ttu-id="4ebc7-121">In breve, con ACI è possibile sviluppare applicazioni fast senza gestire macchine virtuali o dover apprendere nuovi strumenti.</span><span class="sxs-lookup"><span data-stu-id="4ebc7-121">In short, with ACI you can develop apps fast without managing virtual machines or having to learn new tools.</span></span> <span data-ttu-id="4ebc7-122">È semplicemente l'applicazione, in un contenitore, in esecuzione nel cloud.</span><span class="sxs-lookup"><span data-stu-id="4ebc7-122">It's just your application, in a container, running in the cloud.</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="4ebc7-123">[Precedente](when-to-deploy-windows-containers-to-azure-vms-iaas-cloud.md)
[Successivo](when-to-deploy-windows-containers-to-service-fabric.md)</span><span class="sxs-lookup"><span data-stu-id="4ebc7-123">[Previous](when-to-deploy-windows-containers-to-azure-vms-iaas-cloud.md)
[Next](when-to-deploy-windows-containers-to-service-fabric.md)</span></span>
