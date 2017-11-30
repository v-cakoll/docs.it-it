---
title: I registri, immagini e i contenitori di docker
description: Architettura di Microservizi .NET per le applicazioni nei contenitori .NET | I registri, immagini e i contenitori di docker
keywords: Docker, microservizi, ASP.NET, contenitore
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 224fed34f06d10760b14aa9ecbae6c0e912915cf
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="docker-containers-images-and-registries"></a><span data-ttu-id="00169-104">I registri, immagini e i contenitori di docker</span><span class="sxs-lookup"><span data-stu-id="00169-104">Docker containers, images, and registries</span></span>

<span data-ttu-id="00169-105">Quando si usa Docker, uno sviluppatore crea un'applicazione o servizio e i pacchetti e le relative dipendenze in un'immagine contenitore.</span><span class="sxs-lookup"><span data-stu-id="00169-105">When using Docker, a developer creates an app or service and packages it and its dependencies into a container image.</span></span> <span data-ttu-id="00169-106">Un'immagine è una rappresentazione statica della app o servizio e la relativa configurazione e le dipendenze.</span><span class="sxs-lookup"><span data-stu-id="00169-106">An image is a static representation of the app or service and its configuration and dependencies.</span></span>

<span data-ttu-id="00169-107">Per eseguire l'applicazione o servizio, viene creata un'istanza di immagine dell'applicazione per creare un contenitore, che verrà eseguito nell'host Docker.</span><span class="sxs-lookup"><span data-stu-id="00169-107">To run the app or service, the app’s image is instantiated to create a container, which will be running on the Docker host.</span></span> <span data-ttu-id="00169-108">I contenitori vengono inizialmente testati in un ambiente di sviluppo o un PC.</span><span class="sxs-lookup"><span data-stu-id="00169-108">Containers are initially tested in a development environment or PC.</span></span>

<span data-ttu-id="00169-109">Gli sviluppatori devono archiviare immagini in un registro di sistema, che funziona come una libreria di immagini ed è necessario per la distribuzione in orchestrators di produzione.</span><span class="sxs-lookup"><span data-stu-id="00169-109">Developers should store images in a registry, which acts as a library of images and is needed when deploying to production orchestrators.</span></span> <span data-ttu-id="00169-110">Docker gestisce un registro di sistema pubblico tramite [Hub Docker](https://hub.docker.com/); altri fornitori offrono i registri per le diverse raccolte di immagini.</span><span class="sxs-lookup"><span data-stu-id="00169-110">Docker maintains a public registry via [Docker Hub](https://hub.docker.com/); other vendors provide registries for different collections of images.</span></span> <span data-ttu-id="00169-111">In alternativa, le aziende possono avere un privato del Registro di sistema locale per le proprie immagini Docker.</span><span class="sxs-lookup"><span data-stu-id="00169-111">Alternatively, enterprises can have a private registry on-premises for their own Docker images.</span></span>

<span data-ttu-id="00169-112">Figura 2-4 viene illustrato come le immagini e i registri in Docker correlati ad altri componenti.</span><span class="sxs-lookup"><span data-stu-id="00169-112">Figure 2-4 shows how images and registries in Docker relate to other components.</span></span> <span data-ttu-id="00169-113">Vengono inoltre mostrate le offerte del Registro di sistema più fornitori.</span><span class="sxs-lookup"><span data-stu-id="00169-113">It also shows the multiple registry offerings from vendors.</span></span>

![](./media/image5.PNG)

<span data-ttu-id="00169-114">**Figura 2-4**.</span><span class="sxs-lookup"><span data-stu-id="00169-114">**Figure 2-4**.</span></span> <span data-ttu-id="00169-115">Tassonomia di concetti e termini di Docker</span><span class="sxs-lookup"><span data-stu-id="00169-115">Taxonomy of Docker terms and concepts</span></span>

<span data-ttu-id="00169-116">Inserimento di immagini in un registro di sistema consente di archiviare bit applicazione statici e non modificabile, incluse tutte le relative dipendenze a livello di framework.</span><span class="sxs-lookup"><span data-stu-id="00169-116">Putting images in a registry lets you store static and immutable application bits, including all their dependencies at a framework level.</span></span> <span data-ttu-id="00169-117">Queste immagini possono quindi essere distribuiti in più ambienti e con controllo delle versioni e pertanto fornire un'unità di distribuzione uniforme.</span><span class="sxs-lookup"><span data-stu-id="00169-117">Those images can then be versioned and deployed in multiple environments and therefore provide a consistent deployment unit.</span></span>

<span data-ttu-id="00169-118">I registri di immagine privata, ospitato in locale o nel cloud, sono consigliati quando:</span><span class="sxs-lookup"><span data-stu-id="00169-118">Private image registries, either hosted on-premises or in the cloud, are recommended when:</span></span>

-   <span data-ttu-id="00169-119">Le immagini non devono essere condiviso pubblicamente a causa di riservatezza.</span><span class="sxs-lookup"><span data-stu-id="00169-119">Your images must not be shared publicly due to confidentiality.</span></span>

-   <span data-ttu-id="00169-120">Si desidera la latenza di rete minime tra le immagini e l'ambiente di distribuzione scelto.</span><span class="sxs-lookup"><span data-stu-id="00169-120">You want to have minimum network latency between your images and your chosen deployment environment.</span></span> <span data-ttu-id="00169-121">Ad esempio, se l'ambiente di produzione è cloud di Azure, si vorrà memorizzare le immagini nel Registro di sistema contenitore di Azure in modo che la latenza di rete sarà minima.</span><span class="sxs-lookup"><span data-stu-id="00169-121">For example, if your production environment is Azure cloud, you probably want to store your images in Azure Container Registry so that network latency will be minimal.</span></span> <span data-ttu-id="00169-122">In modo analogo, se l'ambiente di produzione è locale, è possibile impostare un locale registro attendibile Docker disponibili all'interno della stessa rete locale.</span><span class="sxs-lookup"><span data-stu-id="00169-122">In a similar way, if your production environment is on-premises, you might want to have an on-premises Docker Trusted Registry available within the same local network.</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="00169-123">[Precedente] (docker-terminology.md) [Avanti] (... /NET-core-NET-Framework-Containers/index.MD)</span><span class="sxs-lookup"><span data-stu-id="00169-123">[Previous] (docker-terminology.md) [Next] (../net-core-net-framework-containers/index.md)</span></span>
