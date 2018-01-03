---
title: Introduzione a contenitori e Docker
description: Architettura di microservizi .NET per le applicazioni .NET incluse in contenitori | Introduzione a contenitori e Docker
keywords: Docker, microservizi, ASP.NET, contenitore
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 8809ae41609ff0e2d2fc969d412cb5edc8939653
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="introduction-to-containers-and-docker"></a><span data-ttu-id="ca734-104">Introduzione a contenitori e Docker</span><span class="sxs-lookup"><span data-stu-id="ca734-104">Introduction to Containers and Docker</span></span>

<span data-ttu-id="ca734-105">La containerizzazione è un approccio allo sviluppo del software in cui un'applicazione o un servizio, le relative dipendenze e la corrispondente configurazione (astratti come file manifesto della distribuzione) sono inclusi in uno stesso pacchetto sotto forma di immagine del contenitore.</span><span class="sxs-lookup"><span data-stu-id="ca734-105">Containerization is an approach to software development in which an application or service, its dependencies, and its configuration (abstracted as deployment manifest files) are packaged together as a container image.</span></span> <span data-ttu-id="ca734-106">L'applicazione inclusa nel contenitore può essere testata come unità e distribuita come istanza dell'immagine del contenitore al sistema operativo host.</span><span class="sxs-lookup"><span data-stu-id="ca734-106">The containerized application can be tested as a unit and deployed as a container image instance to the host operating system (OS).</span></span>

<span data-ttu-id="ca734-107">Proprio come i container consentono il trasporto delle merci via nave, treno o camion indipendentemente dal contenuto del carico, i contenitori software fungono da unità standard di software in grado di contenere codice e dipendenze diversi.</span><span class="sxs-lookup"><span data-stu-id="ca734-107">Just as shipping containers allow goods to be transported by ship, train, or truck regardless of the cargo inside, software containers act as a standard unit of software that can contain different code and dependencies.</span></span> <span data-ttu-id="ca734-108">Questa modalità di containerizzazione del software consente a sviluppatori e professionisti IT di distribuire applicazioni tra ambienti diversi con modifiche minime se non inesistenti.</span><span class="sxs-lookup"><span data-stu-id="ca734-108">Containerizing software this way enables developers and IT professionals to deploy them across environments with little or no modification.</span></span>

<span data-ttu-id="ca734-109">I contenitori contribuiscono inoltre a isolare le applicazioni una dall'altra in un sistema operativo condiviso.</span><span class="sxs-lookup"><span data-stu-id="ca734-109">Containers also isolate applications from each other on a shared OS.</span></span> <span data-ttu-id="ca734-110">Le applicazioni incluse in contenitori sono eseguite in un host contenitore che a sua volta viene eseguito nel sistema operativo (Linux o Windows).</span><span class="sxs-lookup"><span data-stu-id="ca734-110">Containerized applications run on top of a container host that in turn runs on the OS (Linux or Windows).</span></span> <span data-ttu-id="ca734-111">I contenitori hanno pertanto un footprint notevolmente più ridotto rispetto alle immagini di macchine virtuali.</span><span class="sxs-lookup"><span data-stu-id="ca734-111">Containers therefore have a significantly smaller footprint than virtual machine (VM) images.</span></span>

<span data-ttu-id="ca734-112">Ogni contenitore può eseguire un intero servizio e applicazione Web, come illustrato nella figura 2-1.</span><span class="sxs-lookup"><span data-stu-id="ca734-112">Each container can run a whole web application or a service, as shown in Figure 2-1.</span></span> <span data-ttu-id="ca734-113">In questo esempio l'host Docker è un host contenitore e App1, App2, Svc 1 e Svc 2 sono applicazioni o servizi inclusi nei contenitori.</span><span class="sxs-lookup"><span data-stu-id="ca734-113">In this example, Docker host is a container host, and App1, App2, Svc 1, and Svc 2 are containerized applications or services.</span></span>

![](./media/image1.png)

<span data-ttu-id="ca734-114">**Figura 2-1**.</span><span class="sxs-lookup"><span data-stu-id="ca734-114">**Figure 2-1**.</span></span> <span data-ttu-id="ca734-115">Più contenitori in esecuzione in un host contenitore</span><span class="sxs-lookup"><span data-stu-id="ca734-115">Multiple containers running on a container host</span></span>

<span data-ttu-id="ca734-116">Un altro vantaggio della containerizzazione consiste nella scalabilità.</span><span class="sxs-lookup"><span data-stu-id="ca734-116">Another benefit of containerization is scalability.</span></span> <span data-ttu-id="ca734-117">La scalabilità orizzontale viene rapidamente garantita con la creazione di nuovi contenitori per le attività a breve termine.</span><span class="sxs-lookup"><span data-stu-id="ca734-117">You can scale out quickly by creating new containers for short-term tasks.</span></span> <span data-ttu-id="ca734-118">Dal punto di vista dell'applicazione, la creazione di un'istanza di un'immagine (corrispondente alla creazione di un contenitore) è analoga alla creazione di un'istanza di un processo, come un servizio o un'app Web.</span><span class="sxs-lookup"><span data-stu-id="ca734-118">From an application point of view, instantiating an image (creating a container) is similar to instantiating a process like a service or web app.</span></span> <span data-ttu-id="ca734-119">Per l'affidabilità, tuttavia, quando si eseguono più istanze della stessa immagine tra più server host, in genere si fa in modo che ogni contenitore (istanza dell'immagine) sia eseguito in un server host o in una macchina virtuale diversa in domini di errore differenti.</span><span class="sxs-lookup"><span data-stu-id="ca734-119">For reliability, however, when you run multiple instances of the same image across multiple host servers, you typically want each container (image instance) to run in a different host server or VM in different fault domains.</span></span>

<span data-ttu-id="ca734-120">In breve, i contenitori assicurano vantaggi in termini di isolamento, portabilità, flessibilità, scalabilità e controllo nel flusso di lavoro dell'intero ciclo di vita dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="ca734-120">In short, containers offer the benefits of isolation, portability, agility, scalability, and control across the whole application lifecycle workflow.</span></span> <span data-ttu-id="ca734-121">Il vantaggio più importante è l'isolamento fornito tra sviluppo e operazioni.</span><span class="sxs-lookup"><span data-stu-id="ca734-121">The most important benefit is the isolation provided between Dev and Ops.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="ca734-122">[Precedente] (../index.md) [Successivo] (docker-defined.md)</span><span class="sxs-lookup"><span data-stu-id="ca734-122">[Previous] (../index.md) [Next] (docker-defined.md)</span></span>
