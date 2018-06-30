---
title: Introduzione ai contenitori e a Docker
description: Ciclo di vita delle applicazioni Docker in contenitori con piattaforma e strumenti Microsoft
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: e9f81c5fecc06b19ebd84cc4b2cc232686768a90
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/29/2018
ms.locfileid: "37106632"
---
# <a name="introduction-to-containers-and-docker"></a><span data-ttu-id="54b9c-103">Introduzione ai contenitori e a Docker</span><span class="sxs-lookup"><span data-stu-id="54b9c-103">Introduction to containers and Docker</span></span>

<span data-ttu-id="54b9c-104">La containerizzazione è un approccio allo sviluppo del software in cui un'applicazione o un servizio, le relative dipendenze e la corrispondente configurazione (astratti come file manifesto della distribuzione) sono inclusi in uno stesso pacchetto sotto forma di immagine del contenitore.</span><span class="sxs-lookup"><span data-stu-id="54b9c-104">Containerization is an approach to software development in which an application or service, its dependencies, and its configuration (abstracted as deployment manifest files) are packaged together as a container image.</span></span> <span data-ttu-id="54b9c-105">È quindi possibile testare l'applicazione nel contenitore come unità e distribuirla come istanza dell'immagine del contenitore al sistema operativo host.</span><span class="sxs-lookup"><span data-stu-id="54b9c-105">You then can test the containerized application as a unit and deploy it as a container image instance to the host operating system.</span></span>

<span data-ttu-id="54b9c-106">Proprio come nel settore delle spedizioni vengono usati container standard per il trasporto delle merci via nave, treno o camion indipendentemente dal contenuto del carico, i contenitori software fungono da unità standard di software in grado di contenere codice e dipendenze diversi.</span><span class="sxs-lookup"><span data-stu-id="54b9c-106">Just as the shipping industry uses standardized containers to move goods by ship, train, or truck, regardless of the cargo within them, software containers act as a standard unit of software that can contain different code and dependencies.</span></span> <span data-ttu-id="54b9c-107">Inserendo il software nei contenitori si consente agli sviluppatori e ai professionisti IT di distribuire tali contenitori in ambienti diversi senza nessuna modifica o con modifiche minime.</span><span class="sxs-lookup"><span data-stu-id="54b9c-107">Placing software into containers makes it possible for developers and IT professionals to deploy those containers across environments with little or no modification.</span></span>

<span data-ttu-id="54b9c-108">I contenitori isolano anche le applicazioni una dall'altra in un sistema operativo condiviso.</span><span class="sxs-lookup"><span data-stu-id="54b9c-108">Containers also isolate applications from one another on a shared operating system (OS).</span></span> <span data-ttu-id="54b9c-109">Le applicazioni in contenitori vengono eseguite in un host contenitore che a sua volta viene eseguito nel sistema operativo (Linux o Windows).</span><span class="sxs-lookup"><span data-stu-id="54b9c-109">Containerized applications run on top of a container host, which in turn runs on the OS (Linux or Windows).</span></span> <span data-ttu-id="54b9c-110">I contenitori hanno quindi un footprint notevolmente più ridotto rispetto alle immagini di macchine virtuali.</span><span class="sxs-lookup"><span data-stu-id="54b9c-110">Thus, containers have a significantly smaller footprint than virtual machine (VM) images.</span></span>

<span data-ttu-id="54b9c-111">Ogni contenitore può eseguire un intero servizio o applicazione Web, come illustrato nella figura 1-1.</span><span class="sxs-lookup"><span data-stu-id="54b9c-111">Each container can run an entire web application or a service, as shown in Figure 1-1.</span></span>

![](./media/image1.png)

<span data-ttu-id="54b9c-112">Figura 1-1: Più contenitori in esecuzione in un host contenitore</span><span class="sxs-lookup"><span data-stu-id="54b9c-112">Figure 1-1: Multiple containers running on a container host</span></span>

<span data-ttu-id="54b9c-113">In questo esempio l'host Docker è un host contenitore e App 1, App 2, Svc 1 e Svc 2 sono applicazioni o servizi in contenitori.</span><span class="sxs-lookup"><span data-stu-id="54b9c-113">In this example, Docker Host is a container host, and App 1, App 2, Svc 1, and Svc 2 are containerized applications or services.</span></span>

<span data-ttu-id="54b9c-114">Un altro vantaggio offerto dai contenitori è la scalabilità.</span><span class="sxs-lookup"><span data-stu-id="54b9c-114">Another benefit you can derive from containerization is scalability.</span></span> <span data-ttu-id="54b9c-115">È possibile ottenere rapidamente scalabilità orizzontale creando nuovi contenitori per le attività a breve termine.</span><span class="sxs-lookup"><span data-stu-id="54b9c-115">You can scale-out quickly by creating new containers for short-term tasks.</span></span> <span data-ttu-id="54b9c-116">Dal punto di vista di un'applicazione, la *creazione di un'istanza di un'immagine* (creazione di un contenitore) è analoga alla creazione di un'istanza di un processo, come un servizio o un'app Web.</span><span class="sxs-lookup"><span data-stu-id="54b9c-116">From an application point of view, *instantiating an image* (creating a container) is similar to instantiating a process like a service or web app.</span></span> <span data-ttu-id="54b9c-117">Per l'affidabilità, tuttavia, quando si eseguono più istanze della stessa immagine tra più server host, in genere si fa in modo che ogni contenitore (istanza dell'immagine) sia eseguito in un server host o in una macchina virtuale diversa in domini di errore differenti.</span><span class="sxs-lookup"><span data-stu-id="54b9c-117">For reliability, however, when you run multiple instances of the same image across multiple host servers, you typically want each container (image instance) to run in a different host server or VM in different fault domains.</span></span>

<span data-ttu-id="54b9c-118">In breve, i contenitori offrono vantaggi in termini di isolamento, portabilità, flessibilità, scalabilità e controllo nel flusso di lavoro dell'intero ciclo di vita dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="54b9c-118">In short, containers offer the benefits of isolation, portability, agility, scalability, and control across the entire application life cycle workflow.</span></span> <span data-ttu-id="54b9c-119">Il vantaggio più importante è l'isolamento fornito tra sviluppo e operazioni.</span><span class="sxs-lookup"><span data-stu-id="54b9c-119">The most important benefit is the isolation provided between Dev and Ops.</span></span>


>[!div class="step-by-step"]
[<span data-ttu-id="54b9c-120">avanti</span><span class="sxs-lookup"><span data-stu-id="54b9c-120">Next</span></span>](what-is-docker.md)
