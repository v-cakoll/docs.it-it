---
title: Quando distribuire i contenitori di Windows in istanze di contenitore di Azure (ACI)
description: Modernizzare le applicazioni .NET esistenti con il cloud di Azure e i contenitori di Windows | Quando distribuire i contenitori di Windows in istanze di contenitore di Azure (ACI)
ms.date: 04/29/2018
ms.openlocfilehash: 3b6ae1ced9c4e01f5ab400e2575947a396064ebd
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2019
ms.locfileid: "69577934"
---
# <a name="when-to-deploy-windows-containers-to-azure-container-instances-aci"></a><span data-ttu-id="bfd4b-103">Quando distribuire i contenitori di Windows in istanze di contenitore di Azure (ACI)</span><span class="sxs-lookup"><span data-stu-id="bfd4b-103">When to deploy Windows Containers to Azure Container Instances (ACI)</span></span>

<span data-ttu-id="bfd4b-104">Istanze di contenitore di Azure la proposta di valore principale è che è possibile distribuire immediatamente i contenitori e non è necessario mantenere tale ambiente, non è necessario aggiornare/applicare patch al sistema operativo o alle macchine virtuali sottostanti, tutto trasparente ed è sufficiente distribuire i contenitori in un ambiente pronto per l'uso.</span><span class="sxs-lookup"><span data-stu-id="bfd4b-104">Azure Container Instances main value proposition is that you can right away deploy containers to it and you don’t need to maintain that environment, you don’t need to upgrade/patch the underlying operating system or VMs, all that is transparent and you just deploy containers into a ready-to-use environment.</span></span>

<span data-ttu-id="bfd4b-105">I motivi e gli scenari in cui si vuole usare ACI sono simili agli scenari principali quando si usano macchine virtuali di Azure con contenitori, quindi fondamentalmente gli scenari principali per l'uso di istanze di contenitore di Azure sono:</span><span class="sxs-lookup"><span data-stu-id="bfd4b-105">The reasons and scenarios when you would want to use ACI are similar to the main scenarios when you use Azure VMs with containers, so basically, the main scenarios for using Azure Container Instances are:</span></span>

- <span data-ttu-id="bfd4b-106">**Scenari di sviluppo/test**</span><span class="sxs-lookup"><span data-stu-id="bfd4b-106">**Dev/Test scenarios**</span></span>
- <span data-ttu-id="bfd4b-107">**Automazione delle attività**</span><span class="sxs-lookup"><span data-stu-id="bfd4b-107">**Task automation**</span></span>
- <span data-ttu-id="bfd4b-108">**Agenti CI/CD**</span><span class="sxs-lookup"><span data-stu-id="bfd4b-108">**CI/CD agents**</span></span>
- <span data-ttu-id="bfd4b-109">**Elaborazione batch ridotta/scalabile**</span><span class="sxs-lookup"><span data-stu-id="bfd4b-109">**Small/scale batch processing**</span></span>
- <span data-ttu-id="bfd4b-110">**App Web semplici**</span><span class="sxs-lookup"><span data-stu-id="bfd4b-110">**Simple web apps**</span></span>

<span data-ttu-id="bfd4b-111">Lo scenario di app Web semplici è uno scenario equo per ACI, ma tenere presente che, poiché in ACI è possibile avere una sola istanza di contenitore per ogni immagine del contenitore, non si avrà una disponibilità elevata e si avrà solo una scalabilità limitata.</span><span class="sxs-lookup"><span data-stu-id="bfd4b-111">The simple web apps scenario is a fair scenario for ACI but take into account that since in ACI you can only have a single container instance per container image, you won’t have high availability and only have limited scalability.</span></span>

<span data-ttu-id="bfd4b-112">Tuttavia, anche quando ACI viene considerato infrastruttura perché fornisce solo istanze di contenitore singolo, si verifica un enorme vantaggio rispetto alle normali macchine virtuali di Azure con Windows Server.</span><span class="sxs-lookup"><span data-stu-id="bfd4b-112">However, even when ACI is considered infrastructure because it just provides single container instances, there is a huge benefit compared to regular Azure VMs with Windows Server.</span></span> <span data-ttu-id="bfd4b-113">Con ACI è sufficiente distribuire i contenitori in un ambiente autogestito ed è sufficiente pagare per questi contenitori.</span><span class="sxs-lookup"><span data-stu-id="bfd4b-113">With ACI, you just deploy the containers into a self-maintained environment and you just pay for those containers.</span></span> <span data-ttu-id="bfd4b-114">Non è necessario gestire/aggiornare/applicare patch alle macchine virtuali, quindi è una piattaforma molto migliore per la maggior parte degli scenari in cui è possibile usare macchine virtuali con i contenitori.</span><span class="sxs-lookup"><span data-stu-id="bfd4b-114">You don’t need to maintain/update/patch VMs, so it is a much better platform for most scenarios where you might be using VMs with containers.</span></span> <span data-ttu-id="bfd4b-115">L'uso di ACI è semplice, ma è sufficiente distribuire un contenitore. non è necessario creare un ambiente di macchina virtuale in cui si distribuiscono semplicemente i contenitori.</span><span class="sxs-lookup"><span data-stu-id="bfd4b-115">Using ACI is straight forward, you just deploy a container, there’s no need to create a VM environment you just deploy containers.</span></span>

<span data-ttu-id="bfd4b-116">I principali vantaggi delle istanze di contenitore di Azure sono:</span><span class="sxs-lookup"><span data-stu-id="bfd4b-116">The main benefits of Azure Container Instances (ACI) are:</span></span>

- <span data-ttu-id="bfd4b-117">Esegui contenitori senza gestire i server</span><span class="sxs-lookup"><span data-stu-id="bfd4b-117">Run containers without managing servers</span></span>
- <span data-ttu-id="bfd4b-118">Aumento della flessibilità con i contenitori su richiesta</span><span class="sxs-lookup"><span data-stu-id="bfd4b-118">Increase agility with containers on demand</span></span>
- <span data-ttu-id="bfd4b-119">Distribuisci i contenitori nel cloud con semplicità e velocità senza precedenti, con un unico comando.</span><span class="sxs-lookup"><span data-stu-id="bfd4b-119">Deploy containers to the cloud with unprecedented simplicity and speed—with a single command.</span></span>
- <span data-ttu-id="bfd4b-120">Proteggere le applicazioni con isolamento hypervisor</span><span class="sxs-lookup"><span data-stu-id="bfd4b-120">Secure applications with hypervisor isolation</span></span>

<span data-ttu-id="bfd4b-121">In breve, con ACI è possibile sviluppare rapidamente app senza dover gestire macchine virtuali o dover apprendere nuovi strumenti.</span><span class="sxs-lookup"><span data-stu-id="bfd4b-121">In short, with ACI you can develop apps fast without managing virtual machines or having to learn new tools.</span></span> <span data-ttu-id="bfd4b-122">Si tratta solo dell'applicazione, in un contenitore, in esecuzione nel cloud.</span><span class="sxs-lookup"><span data-stu-id="bfd4b-122">It's just your application, in a container, running in the cloud.</span></span>

> [!div class="step-by-step"]
> <span data-ttu-id="bfd4b-123">[Precedente](when-to-deploy-windows-containers-to-azure-vms-iaas-cloud.md)
> [Successivo](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)</span><span class="sxs-lookup"><span data-stu-id="bfd4b-123">[Previous](when-to-deploy-windows-containers-to-azure-vms-iaas-cloud.md)
[Next](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)</span></span>
