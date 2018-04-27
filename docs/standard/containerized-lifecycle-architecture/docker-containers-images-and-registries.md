---
title: Contenitori, immagini e registri Docker
description: Ciclo di vita delle applicazioni Docker in contenitori con piattaforma e strumenti Microsoft
ms.prod: .net
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 8ba0cd3323467e07a33ffd4083e390d57fdce7ff
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2018
---
# <a name="docker-containers-images-and-registries"></a><span data-ttu-id="5a4e6-103">Contenitori, immagini e registri Docker</span><span class="sxs-lookup"><span data-stu-id="5a4e6-103">Docker containers, images, and registries</span></span>

<span data-ttu-id="5a4e6-104">Quando si usa Docker, creerai un'app o un servizio e un pacchetto e le relative dipendenze in un'immagine contenitore.</span><span class="sxs-lookup"><span data-stu-id="5a4e6-104">When using Docker, you create an app or service and package it and its dependencies into a container image.</span></span> <span data-ttu-id="5a4e6-105">Un'immagine è una rappresentazione statica dell'app o del servizio, della relativa configurazione e delle dipendenze.</span><span class="sxs-lookup"><span data-stu-id="5a4e6-105">An image is a static representation of the app or service and its configuration and dependencies.</span></span>

<span data-ttu-id="5a4e6-106">Per eseguire l'applicazione o servizio, viene creata un'istanza di immagine dell'applicazione per creare un contenitore, che verrà eseguito nell'host Docker.</span><span class="sxs-lookup"><span data-stu-id="5a4e6-106">To run the app or service, the app's image is instantiated to create a container, which will be running on the Docker host.</span></span> <span data-ttu-id="5a4e6-107">I contenitori vengono inizialmente testati in un PC o in un ambiente di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="5a4e6-107">Containers are initially tested in a development environment or PC.</span></span>

<span data-ttu-id="5a4e6-108">Archiviare le immagini in un registro di sistema, che funziona come una libreria di immagini.</span><span class="sxs-lookup"><span data-stu-id="5a4e6-108">You store images in a registry, which acts as a library of images.</span></span> <span data-ttu-id="5a4e6-109">È necessario un registro di sistema durante la distribuzione in orchestrators di produzione.</span><span class="sxs-lookup"><span data-stu-id="5a4e6-109">You need a registry when deploying to production orchestrators.</span></span> <span data-ttu-id="5a4e6-110">Docker mantiene un registro pubblico tramite l'[hub Docker](https://hub.docker.com/). Altri fornitori offrono registri per diverse raccolte di immagini.</span><span class="sxs-lookup"><span data-stu-id="5a4e6-110">Docker maintains a public registry via [Docker Hub](https://hub.docker.com/); other vendors provide registries for different collections of images.</span></span> <span data-ttu-id="5a4e6-111">In alternativa, le aziende possono gestire un registro privato locale per le proprie immagini Docker.</span><span class="sxs-lookup"><span data-stu-id="5a4e6-111">Alternatively, enterprises can have a private registry on-premises for their own Docker images.</span></span>

<span data-ttu-id="5a4e6-112">Figura 1-4 viene illustrato come le immagini e i registri in Docker correlati ad altri componenti.</span><span class="sxs-lookup"><span data-stu-id="5a4e6-112">Figure 1-4 shows how images and registries in Docker relate to other components.</span></span> <span data-ttu-id="5a4e6-113">Mostra inoltre le varie offerte dei fornitori per i registri.</span><span class="sxs-lookup"><span data-stu-id="5a4e6-113">It also shows the multiple registry offerings from vendors.</span></span>

![](./media/image4.png)

<span data-ttu-id="5a4e6-114">Figura 1-4: tassonomia di concetti e termini di Docker</span><span class="sxs-lookup"><span data-stu-id="5a4e6-114">Figure 1-4: Taxonomy of Docker terms and concepts</span></span>

<span data-ttu-id="5a4e6-115">Inserendo le immagini in un registro di sistema, è possibile archiviare i bit di applicazione statico e non modificabile, incluse tutte le relative dipendenze, un livello di framework.</span><span class="sxs-lookup"><span data-stu-id="5a4e6-115">By putting images in a registry, you can store static and immutable application bits, including all of their dependencies, at a framework level.</span></span> <span data-ttu-id="5a4e6-116">È quindi possibile modificare la versione e distribuire le immagini in più ambienti e pertanto costituiscono un'unità di distribuzione uniforme.</span><span class="sxs-lookup"><span data-stu-id="5a4e6-116">You then can version and deploy images in multiple environments and thus provide a consistent deployment unit.</span></span>

<span data-ttu-id="5a4e6-117">Registri di immagine privata ospitata in locale o nel cloud, sono consigliate per le situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5a4e6-117">Private image registries, either hosted on-premises or in the cloud, are recommended for the following situations:</span></span>

-   <span data-ttu-id="5a4e6-118">Le immagini non devono essere condivise pubblicamente per motivi di riservatezza.</span><span class="sxs-lookup"><span data-stu-id="5a4e6-118">Your images must not be shared publicly due to confidentiality.</span></span>

-   <span data-ttu-id="5a4e6-119">Si desidera una latenza di rete minima tra le immagini e l'ambiente di distribuzione scelto.</span><span class="sxs-lookup"><span data-stu-id="5a4e6-119">You want to have minimum network latency between your images and your chosen deployment environment.</span></span> <span data-ttu-id="5a4e6-120">Ad esempio, se l'ambiente di produzione Azure, si vorrà memorizzare le immagini nel Registro di sistema contenitore di Azure in modo che la latenza di rete sarà minima.</span><span class="sxs-lookup"><span data-stu-id="5a4e6-120">For example, if your production environment is Azure, you probably want to store your images in Azure Container Registry so that network latency will be minimal.</span></span> <span data-ttu-id="5a4e6-121">Allo stesso modo, se l'ambiente di produzione è ospitato in locale, è consigliabile che il registro Docker Trusted Registry sia disponibile nella stessa rete locale.</span><span class="sxs-lookup"><span data-stu-id="5a4e6-121">In a similar way, if your production environment is on-premises, you might want to have an on-premises Docker Trusted Registry available within the same local network.</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="5a4e6-122">[Precedente] (docker-terminology.md) [Avanti] (Docker-applicazione-del ciclo di vita/index.md)</span><span class="sxs-lookup"><span data-stu-id="5a4e6-122">[Previous] (docker-terminology.md) [Next] (Docker-application-lifecycle/index.md)</span></span>
