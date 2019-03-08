---
title: Casi in cui distribuire i contenitori di Windows per istanze di contenitore di Azure (ACI)
description: Modernizzare le applicazioni .NET esistenti con contenitori Windows e il Cloud di Azure | Casi in cui distribuire i contenitori di Windows per istanze di contenitore di Azure (ACI)
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/29/2018
ms.openlocfilehash: 03ee7c8b65e1a92dcc7fd40b44e9ba081f571487
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/08/2019
ms.locfileid: "57674406"
---
# <a name="when-to-deploy-windows-containers-to-azure-container-instances-aci"></a><span data-ttu-id="44023-103">Casi in cui distribuire i contenitori di Windows per istanze di contenitore di Azure (ACI)</span><span class="sxs-lookup"><span data-stu-id="44023-103">When to deploy Windows Containers to Azure Container Instances (ACI)</span></span>

<span data-ttu-id="44023-104">Proposta di valore principale è che è possibile distribuire i contenitori sin da subito ad esso e non è necessario gestire quell'ambiente istanze di contenitore di Azure, non devi aggiornamento/patch del sistema operativo o le macchine virtuali, tutto questo è trasparente sottostante ed è stato distribuito contenitori in un ambiente pronto da usare.</span><span class="sxs-lookup"><span data-stu-id="44023-104">Azure Container Instances main value proposition is that you can right away deploy containers to it and you don’t need to maintain that environment, you don’t need to upgrade/patch the underlying operating system or VMs, all that is transparent and you just deploy containers into a ready-to-use environment.</span></span>

<span data-ttu-id="44023-105">I motivi e gli scenari quando si vuole usare ACI sono simili agli scenari principali quando si usano macchine virtuali di Azure con i contenitori, essenzialmente, gli scenari principali per l'uso di istanze di contenitore di Azure:</span><span class="sxs-lookup"><span data-stu-id="44023-105">The reasons and scenarios when you would want to use ACI are similar to the main scenarios when you use Azure VMs with containers, so basically, the main scenarios for using Azure Container Instances are:</span></span>

- <span data-ttu-id="44023-106">**Scenari di sviluppo/Test**</span><span class="sxs-lookup"><span data-stu-id="44023-106">**Dev/Test scenarios**</span></span>
- <span data-ttu-id="44023-107">**Automazione delle attività**</span><span class="sxs-lookup"><span data-stu-id="44023-107">**Task automation**</span></span>
- <span data-ttu-id="44023-108">**Agenti di integrazione continua/recapito Continuo**</span><span class="sxs-lookup"><span data-stu-id="44023-108">**CI/CD agents**</span></span>
- <span data-ttu-id="44023-109">**Elaborazione batch di piccole dimensioni e della scala**</span><span class="sxs-lookup"><span data-stu-id="44023-109">**Small/scale batch processing**</span></span>
- <span data-ttu-id="44023-110">**App web semplice**</span><span class="sxs-lookup"><span data-stu-id="44023-110">**Simple web apps**</span></span>

<span data-ttu-id="44023-111">Lo scenario di App web semplice è uno scenario equo per ACI ma prendere in considerazione che poiché in ACI può avere solo un'istanza di contenitore singolo per ogni immagine del contenitore, si verificherà la disponibilità elevata e dispone solo di una scalabilità limitata.</span><span class="sxs-lookup"><span data-stu-id="44023-111">The simple web apps scenario is a fair scenario for ACI but take into account that since in ACI you can only have a single container instance per container image, you won’t have high availability and only have limited scalability.</span></span>

<span data-ttu-id="44023-112">Tuttavia, anche quando ACI è considerata infrastruttura perché fornisce solo le istanze di contenitore singolo, vi è un enorme vantaggio rispetto alle normali macchine virtuali di Azure con Windows Server.</span><span class="sxs-lookup"><span data-stu-id="44023-112">However, even when ACI is considered infrastructure because it just provides single container instances, there is a huge benefit compared to regular Azure VMs with Windows Server.</span></span> <span data-ttu-id="44023-113">Con ACI, sufficiente distribuire i contenitori in un ambiente autonoma e paghi solo per i contenitori.</span><span class="sxs-lookup"><span data-stu-id="44023-113">With ACI, you just deploy the containers into a self-maintained environment and you just pay for those containers.</span></span> <span data-ttu-id="44023-114">Non è necessario mantenere/aggiornamento/patch le macchine virtuali, pertanto è una piattaforma molto migliorata per la maggior parte degli scenari in cui è possibile utilizzare le macchine virtuali con i contenitori.</span><span class="sxs-lookup"><span data-stu-id="44023-114">You don’t need to maintain/update/patch VMs, so it is a much better platform for most scenarios where you might be using VMs with containers.</span></span> <span data-ttu-id="44023-115">Usando ACI è molto semplice, sufficiente distribuire un contenitore, non è necessario creare un ambiente di macchine Virtuali sufficiente distribuire i contenitori.</span><span class="sxs-lookup"><span data-stu-id="44023-115">Using ACI is straight forward, you just deploy a container, there’s no need to create a VM environment you just deploy containers.</span></span>

<span data-ttu-id="44023-116">I vantaggi principali di istanze di contenitore di Azure (ACI) sono:</span><span class="sxs-lookup"><span data-stu-id="44023-116">The main benefits of Azure Container Instances (ACI) are:</span></span>

- <span data-ttu-id="44023-117">Esegui i contenitori senza gestire server</span><span class="sxs-lookup"><span data-stu-id="44023-117">Run containers without managing servers</span></span>
- <span data-ttu-id="44023-118">Aumenta la flessibilità con contenitori on demand</span><span class="sxs-lookup"><span data-stu-id="44023-118">Increase agility with containers on demand</span></span>
- <span data-ttu-id="44023-119">Distribuire contenitori nel cloud con semplicità senza precedenti e velocità, con un unico comando.</span><span class="sxs-lookup"><span data-stu-id="44023-119">Deploy containers to the cloud with unprecedented simplicity and speed—with a single command.</span></span>
- <span data-ttu-id="44023-120">Proteggere le applicazioni con isolamento con hypervisor</span><span class="sxs-lookup"><span data-stu-id="44023-120">Secure applications with hypervisor isolation</span></span>

<span data-ttu-id="44023-121">In breve, con ACI è possibile sviluppare App rapidamente senza la gestione delle macchine virtuali o che sia necessario imparare nuovi strumenti.</span><span class="sxs-lookup"><span data-stu-id="44023-121">In short, with ACI you can develop apps fast without managing virtual machines or having to learn new tools.</span></span> <span data-ttu-id="44023-122">È solo la tua applicazione, in un contenitore, in esecuzione nel cloud.</span><span class="sxs-lookup"><span data-stu-id="44023-122">It's just your application, in a container, running in the cloud.</span></span>

> [!div class="step-by-step"]
> <span data-ttu-id="44023-123">[Precedente](when-to-deploy-windows-containers-to-azure-vms-iaas-cloud.md)
> [Successivo](when-to-deploy-windows-containers-to-service-fabric.md)</span><span class="sxs-lookup"><span data-stu-id="44023-123">[Previous](when-to-deploy-windows-containers-to-azure-vms-iaas-cloud.md)
[Next](when-to-deploy-windows-containers-to-service-fabric.md)</span></span>
