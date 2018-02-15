---
title: I registri, immagini e i contenitori di docker
description: Ciclo di vita delle applicazioni Docker in contenitori con piattaforma e strumenti Microsoft
keywords: Docker, microservizi, ASP.NET, contenitore
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 0cccead8833c63f19b359f830f555e7ff31daa1a
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="docker-containers-images-and-registries"></a><span data-ttu-id="99599-104">I registri, immagini e i contenitori di docker</span><span class="sxs-lookup"><span data-stu-id="99599-104">Docker containers, images, and registries</span></span>

<span data-ttu-id="99599-105">Quando si usa Docker, creerai un'app o un servizio e un pacchetto e le relative dipendenze in un'immagine contenitore.</span><span class="sxs-lookup"><span data-stu-id="99599-105">When using Docker, you create an app or service and package it and its dependencies into a container image.</span></span> <span data-ttu-id="99599-106">Un'immagine è una rappresentazione statica della app o servizio e la relativa configurazione e le dipendenze.</span><span class="sxs-lookup"><span data-stu-id="99599-106">An image is a static representation of the app or service and its configuration and dependencies.</span></span>

<span data-ttu-id="99599-107">Per eseguire l'applicazione o servizio, viene creata un'istanza di immagine dell'applicazione per creare un contenitore, che verrà eseguito nell'host Docker.</span><span class="sxs-lookup"><span data-stu-id="99599-107">To run the app or service, the app's image is instantiated to create a container, which will be running on the Docker host.</span></span> <span data-ttu-id="99599-108">I contenitori vengono inizialmente testati in un ambiente di sviluppo o un PC.</span><span class="sxs-lookup"><span data-stu-id="99599-108">Containers are initially tested in a development environment or PC.</span></span>

<span data-ttu-id="99599-109">Archiviare le immagini in un registro di sistema, che funziona come una libreria di immagini.</span><span class="sxs-lookup"><span data-stu-id="99599-109">You store images in a registry, which acts as a library of images.</span></span> <span data-ttu-id="99599-110">È necessario un registro di sistema durante la distribuzione in orchestrators di produzione.</span><span class="sxs-lookup"><span data-stu-id="99599-110">You need a registry when deploying to production orchestrators.</span></span> <span data-ttu-id="99599-111">Docker gestisce un registro di sistema pubblico tramite [Hub Docker](https://hub.docker.com/); altri fornitori offrono i registri per le diverse raccolte di immagini.</span><span class="sxs-lookup"><span data-stu-id="99599-111">Docker maintains a public registry via [Docker Hub](https://hub.docker.com/); other vendors provide registries for different collections of images.</span></span> <span data-ttu-id="99599-112">In alternativa, le aziende possono avere un privato del Registro di sistema locale per le proprie immagini Docker.</span><span class="sxs-lookup"><span data-stu-id="99599-112">Alternatively, enterprises can have a private registry on-premises for their own Docker images.</span></span>

<span data-ttu-id="99599-113">Figura 1-4 viene illustrato come le immagini e i registri in Docker correlati ad altri componenti.</span><span class="sxs-lookup"><span data-stu-id="99599-113">Figure 1-4 shows how images and registries in Docker relate to other components.</span></span> <span data-ttu-id="99599-114">Vengono inoltre mostrate le offerte del Registro di sistema più fornitori.</span><span class="sxs-lookup"><span data-stu-id="99599-114">It also shows the multiple registry offerings from vendors.</span></span>

![](./media/image4.png)

<span data-ttu-id="99599-115">Figura 1-4: tassonomia di concetti e termini di Docker</span><span class="sxs-lookup"><span data-stu-id="99599-115">Figure 1-4: Taxonomy of Docker terms and concepts</span></span>

<span data-ttu-id="99599-116">Inserendo le immagini in un registro di sistema, è possibile archiviare i bit di applicazione statico e non modificabile, incluse tutte le relative dipendenze, un livello di framework.</span><span class="sxs-lookup"><span data-stu-id="99599-116">By putting images in a registry, you can store static and immutable application bits, including all of their dependencies, at a framework level.</span></span> <span data-ttu-id="99599-117">È quindi possibile modificare la versione e distribuire le immagini in più ambienti e pertanto costituiscono un'unità di distribuzione uniforme.</span><span class="sxs-lookup"><span data-stu-id="99599-117">You then can version and deploy images in multiple environments and thus provide a consistent deployment unit.</span></span>

<span data-ttu-id="99599-118">Registri di immagine privata ospitata in locale o nel cloud, sono consigliate per le situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="99599-118">Private image registries, either hosted on-premises or in the cloud, are recommended for the following situations:</span></span>

-   <span data-ttu-id="99599-119">Le immagini non devono essere condiviso pubblicamente a causa di riservatezza.</span><span class="sxs-lookup"><span data-stu-id="99599-119">Your images must not be shared publicly due to confidentiality.</span></span>

-   <span data-ttu-id="99599-120">Si desidera la latenza di rete minime tra le immagini e l'ambiente di distribuzione scelto.</span><span class="sxs-lookup"><span data-stu-id="99599-120">You want to have minimum network latency between your images and your chosen deployment environment.</span></span> <span data-ttu-id="99599-121">Ad esempio, se l'ambiente di produzione Azure, si vorrà memorizzare le immagini nel Registro di sistema contenitore di Azure in modo che la latenza di rete sarà minima.</span><span class="sxs-lookup"><span data-stu-id="99599-121">For example, if your production environment is Azure, you probably want to store your images in Azure Container Registry so that network latency will be minimal.</span></span> <span data-ttu-id="99599-122">In modo analogo, se l'ambiente di produzione è locale, è possibile impostare un locale registro attendibile Docker disponibili all'interno della stessa rete locale.</span><span class="sxs-lookup"><span data-stu-id="99599-122">In a similar way, if your production environment is on-premises, you might want to have an on-premises Docker Trusted Registry available within the same local network.</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="99599-123">[Precedente] (docker-terminology.md) [Avanti] (Docker-applicazione-del ciclo di vita/index.md)</span><span class="sxs-lookup"><span data-stu-id="99599-123">[Previous] (docker-terminology.md) [Next] (Docker-application-lifecycle/index.md)</span></span>
