---
title: Contenitori, immagini e registri Docker
description: Architettura di microservizi .NET per applicazioni .NET in contenitori | Contenitori, immagini e registri Docker
ms.date: 08/31/2018
ms.openlocfilehash: 520f8d4d54f1fdd227ff9a1e88660b62e75f927f
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2019
ms.locfileid: "68674898"
---
# <a name="docker-containers-images-and-registries"></a><span data-ttu-id="12487-103">Contenitori, immagini e registri Docker</span><span class="sxs-lookup"><span data-stu-id="12487-103">Docker containers, images, and registries</span></span>

<span data-ttu-id="12487-104">Quando uno sviluppatore usa Docker, crea un app o un servizio e crea un pacchetto contenente l'app o il servizio e le relative dipendenze in un'immagine del contenitore.</span><span class="sxs-lookup"><span data-stu-id="12487-104">When using Docker, a developer creates an app or service and packages it and its dependencies into a container image.</span></span> <span data-ttu-id="12487-105">Un'immagine è una rappresentazione statica dell'app o del servizio, della relativa configurazione e delle dipendenze.</span><span class="sxs-lookup"><span data-stu-id="12487-105">An image is a static representation of the app or service and its configuration and dependencies.</span></span>

<span data-ttu-id="12487-106">Per eseguire l'app o il servizio, si crea un'istanza dell'immagine dell'app per creare un contenitore che verrà eseguito nell'host Docker.</span><span class="sxs-lookup"><span data-stu-id="12487-106">To run the app or service, the app's image is instantiated to create a container, which will be running on the Docker host.</span></span> <span data-ttu-id="12487-107">I contenitori vengono inizialmente testati in un PC o in un ambiente di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="12487-107">Containers are initially tested in a development environment or PC.</span></span>

<span data-ttu-id="12487-108">Gli sviluppatori devono archiviare le immagini in un registro, che funge da libreria di immagini e che è necessario per la distribuzione negli agenti di orchestrazione di produzione.</span><span class="sxs-lookup"><span data-stu-id="12487-108">Developers should store images in a registry, which acts as a library of images and is needed when deploying to production orchestrators.</span></span> <span data-ttu-id="12487-109">Docker mantiene un registro pubblico tramite [Docker Hub](https://hub.docker.com/). Altri fornitori offrono registri per diverse raccolte di immagini, incluso il [Registro Azure Container](https://azure.microsoft.com/services/container-registry/).</span><span class="sxs-lookup"><span data-stu-id="12487-109">Docker maintains a public registry via [Docker Hub](https://hub.docker.com/); other vendors provide registries for different collections of images, including [Azure Container Registry](https://azure.microsoft.com/services/container-registry/).</span></span> <span data-ttu-id="12487-110">In alternativa, le aziende possono gestire un registro privato locale per le proprie immagini Docker.</span><span class="sxs-lookup"><span data-stu-id="12487-110">Alternatively, enterprises can have a private registry on-premises for their own Docker images.</span></span>

<span data-ttu-id="12487-111">La figura 2-4 mostra la relazione tra le immagini e i registri in Docker con altri componenti.</span><span class="sxs-lookup"><span data-stu-id="12487-111">Figure 2-4 shows how images and registries in Docker relate to other components.</span></span> <span data-ttu-id="12487-112">Mostra inoltre le varie offerte dei fornitori per i registri.</span><span class="sxs-lookup"><span data-stu-id="12487-112">It also shows the multiple registry offerings from vendors.</span></span>

![Tassonomia di base in Docker: il registro è paragonabile a una libreria in cui le immagini sono archiviate e disponibili per il pull per la creazione di contenitori per eseguire servizi o app Web.](./media/image5.PNG)

<span data-ttu-id="12487-117">**Figura 2-4**.</span><span class="sxs-lookup"><span data-stu-id="12487-117">**Figure 2-4**.</span></span> <span data-ttu-id="12487-118">Tassonomia dei termini e dei concetti di Docker</span><span class="sxs-lookup"><span data-stu-id="12487-118">Taxonomy of Docker terms and concepts</span></span>

<span data-ttu-id="12487-119">L'inserimento delle immagini in un registro permette di archiviare bit di applicazioni statici e immutabili, incluse tutte le dipendenze a livello di framework.</span><span class="sxs-lookup"><span data-stu-id="12487-119">Putting images in a registry lets you store static and immutable application bits, including all their dependencies at a framework level.</span></span> <span data-ttu-id="12487-120">È quindi possibile creare diverse versioni delle immagini e distribuirle in più ambienti per fornire un'unità di distribuzione coerente.</span><span class="sxs-lookup"><span data-stu-id="12487-120">Those images can then be versioned and deployed in multiple environments and therefore provide a consistent deployment unit.</span></span>

<span data-ttu-id="12487-121">I registri di immagini privati, ospitati in locale o nel cloud, sono consigliati nei casi seguenti:</span><span class="sxs-lookup"><span data-stu-id="12487-121">Private image registries, either hosted on-premises or in the cloud, are recommended when:</span></span>

- <span data-ttu-id="12487-122">Le immagini non devono essere condivise pubblicamente per motivi di riservatezza.</span><span class="sxs-lookup"><span data-stu-id="12487-122">Your images must not be shared publicly due to confidentiality.</span></span>

- <span data-ttu-id="12487-123">Si desidera una latenza di rete minima tra le immagini e l'ambiente di distribuzione scelto.</span><span class="sxs-lookup"><span data-stu-id="12487-123">You want to have minimum network latency between your images and your chosen deployment environment.</span></span> <span data-ttu-id="12487-124">Se ad esempio l'ambiente di produzione è il cloud di Azure, è consigliabile archiviare le immagini nel [Registro Azure Container](https://azure.microsoft.com/services/container-registry/) per una latenza di rete minima.</span><span class="sxs-lookup"><span data-stu-id="12487-124">For example, if your production environment is Azure cloud, you probably want to store your images in [Azure Container Registry](https://azure.microsoft.com/services/container-registry/) so that network latency will be minimal.</span></span> <span data-ttu-id="12487-125">Allo stesso modo, se l'ambiente di produzione è ospitato in locale, è consigliabile che il registro Docker Trusted Registry sia disponibile nella stessa rete locale.</span><span class="sxs-lookup"><span data-stu-id="12487-125">In a similar way, if your production environment is on-premises, you might want to have an on-premises Docker Trusted Registry available within the same local network.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="12487-126">[Precedente](docker-terminology.md)
>[Successivo](../net-core-net-framework-containers/index.md)</span><span class="sxs-lookup"><span data-stu-id="12487-126">[Previous](docker-terminology.md)
[Next](../net-core-net-framework-containers/index.md)</span></span>
