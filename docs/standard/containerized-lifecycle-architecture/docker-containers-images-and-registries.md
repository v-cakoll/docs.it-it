---
title: Contenitori, immagini e registri Docker
description: Descrive il ruolo chiave registri dedicarsi complessivo nel modo Docker della distribuzione di applicazioni.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 11/23/2018
ms.openlocfilehash: 7a2e20e09561a5cc91aa29059fb8d19a14205bb5
ms.sourcegitcommit: 30e2fe5cc4165aa6dde7218ec80a13def3255e98
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/13/2019
ms.locfileid: "56221199"
---
# <a name="docker-containers-images-and-registries"></a><span data-ttu-id="d2338-103">Contenitori, immagini e registri Docker</span><span class="sxs-lookup"><span data-stu-id="d2338-103">Docker containers, images, and registries</span></span>

<span data-ttu-id="d2338-104">Quando si usa Docker, si crea un'app o servizio e un pacchetto e le relative dipendenze in un'immagine del contenitore.</span><span class="sxs-lookup"><span data-stu-id="d2338-104">When using Docker, you create an app or service and package it and its dependencies into a container image.</span></span> <span data-ttu-id="d2338-105">Un'immagine è una rappresentazione statica dell'app o del servizio, della relativa configurazione e delle dipendenze.</span><span class="sxs-lookup"><span data-stu-id="d2338-105">An image is a static representation of the app or service and its configuration and dependencies.</span></span>

<span data-ttu-id="d2338-106">Per eseguire l'app o il servizio, si crea un'istanza dell'immagine dell'app per creare un contenitore che verrà eseguito nell'host Docker.</span><span class="sxs-lookup"><span data-stu-id="d2338-106">To run the app or service, the app's image is instantiated to create a container, which will be running on the Docker host.</span></span> <span data-ttu-id="d2338-107">I contenitori vengono inizialmente testati in un PC o in un ambiente di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="d2338-107">Containers are initially tested in a development environment or PC.</span></span>

<span data-ttu-id="d2338-108">Archiviare immagini in un registro di sistema, che agisce come una raccolta di immagini.</span><span class="sxs-lookup"><span data-stu-id="d2338-108">You store images in a registry, which acts as a library of images.</span></span> <span data-ttu-id="d2338-109">È necessario un registro di sistema durante la distribuzione di agenti di orchestrazione di produzione.</span><span class="sxs-lookup"><span data-stu-id="d2338-109">You need a registry when deploying to production orchestrators.</span></span> <span data-ttu-id="d2338-110">Docker mantiene un registro pubblico tramite l'[hub Docker](https://hub.docker.com/). Altri fornitori offrono registri per diverse raccolte di immagini.</span><span class="sxs-lookup"><span data-stu-id="d2338-110">Docker maintains a public registry via [Docker Hub](https://hub.docker.com/); other vendors provide registries for different collections of images.</span></span> <span data-ttu-id="d2338-111">In alternativa, le aziende possono gestire un registro privato locale per le proprie immagini Docker.</span><span class="sxs-lookup"><span data-stu-id="d2338-111">Alternatively, enterprises can have a private registry on-premises for their own Docker images.</span></span>

<span data-ttu-id="d2338-112">Figura 1-4 viene illustrato come immagini e i registri in Docker correlati ad altri componenti.</span><span class="sxs-lookup"><span data-stu-id="d2338-112">Figure 1-4 shows how images and registries in Docker relate to other components.</span></span> <span data-ttu-id="d2338-113">Mostra inoltre le varie offerte dei fornitori per i registri.</span><span class="sxs-lookup"><span data-stu-id="d2338-113">It also shows the multiple registry offerings from vendors.</span></span>

![](./media/image4.png)

<span data-ttu-id="d2338-114">Figura 1-4: Tassonomia dei termini e dei concetti di Docker</span><span class="sxs-lookup"><span data-stu-id="d2338-114">Figure 1-4: Taxonomy of Docker terms and concepts</span></span>

<span data-ttu-id="d2338-115">Inserendo le immagini in un registro di sistema, è possibile archiviare bit di applicazioni statici e immutabili, incluse tutte le relative dipendenze, a livello di framework.</span><span class="sxs-lookup"><span data-stu-id="d2338-115">By putting images in a registry, you can store static and immutable application bits, including all of their dependencies, at a framework level.</span></span> <span data-ttu-id="d2338-116">È quindi possibile modificare la versione e distribuire le immagini in più ambienti e quindi di fornire un'unità di distribuzione coerente.</span><span class="sxs-lookup"><span data-stu-id="d2338-116">You then can version and deploy images in multiple environments and thus provide a consistent deployment unit.</span></span>

<span data-ttu-id="d2338-117">Registri di immagini privati, ospitati in locale o nel cloud, sono consigliati per le situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="d2338-117">Private image registries, either hosted on-premises or in the cloud, are recommended for the following situations:</span></span>

-   <span data-ttu-id="d2338-118">Le immagini non devono essere condivise pubblicamente per motivi di riservatezza.</span><span class="sxs-lookup"><span data-stu-id="d2338-118">Your images must not be shared publicly due to confidentiality.</span></span>

-   <span data-ttu-id="d2338-119">Si desidera una latenza di rete minima tra le immagini e l'ambiente di distribuzione scelto.</span><span class="sxs-lookup"><span data-stu-id="d2338-119">You want to have minimum network latency between your images and your chosen deployment environment.</span></span> <span data-ttu-id="d2338-120">Ad esempio, se l'ambiente di produzione è Azure, probabilmente desidera archiviare le immagini nel registro contenitori di Azure in modo che la latenza di rete sarà minima.</span><span class="sxs-lookup"><span data-stu-id="d2338-120">For example, if your production environment is Azure, you probably want to store your images in Azure Container Registry so that network latency will be minimal.</span></span> <span data-ttu-id="d2338-121">Allo stesso modo, se l'ambiente di produzione è ospitato in locale, è consigliabile che il registro Docker Trusted Registry sia disponibile nella stessa rete locale.</span><span class="sxs-lookup"><span data-stu-id="d2338-121">In a similar way, if your production environment is on-premises, you might want to have an on-premises Docker Trusted Registry available within the same local network.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="d2338-122">[Precedente](docker-terminology.md)
>[Successivo](road-to-modern-applications-based-on-containers.md)</span><span class="sxs-lookup"><span data-stu-id="d2338-122">[Previous](docker-terminology.md)
[Next](road-to-modern-applications-based-on-containers.md)</span></span>
