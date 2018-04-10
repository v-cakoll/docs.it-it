---
title: Progettazione e sviluppo di applicazioni .NET basate su più contenitori e microservizi
description: Architettura di microservizi .NET per le applicazioni .NET incluse in contenitori | Progettazione e sviluppo di applicazioni .NET basate su più contenitori e microservizi
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
ms.openlocfilehash: 2a4c59c63cb3f76975173663948e94a7c64ef193
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="designing-and-developing-multi-container-and-microservice-based-net-applications"></a><span data-ttu-id="202ba-104">Progettazione e sviluppo di applicazioni .NET basate su più contenitori e microservizi</span><span class="sxs-lookup"><span data-stu-id="202ba-104">Designing and Developing Multi-Container and Microservice-Based .NET Applications</span></span>

<span data-ttu-id="202ba-105">*Sviluppare applicazioni di microservizi incluse in contenitori significa compilare applicazioni a più contenitori. Tuttavia, un'applicazione a più contenitori potrebbe anche essere più semplice, ad esempio un'applicazione a tre livelli, e potrebbe non essere compilata usando un'architettura di microservizi.*</span><span class="sxs-lookup"><span data-stu-id="202ba-105">*Developing containerized microservice applications means you are building multi-container applications. However, a multi-container application could also be simpler—for example, a three-tier application—and might not be built using a microservice architecture.*</span></span>

<span data-ttu-id="202ba-106">In precedenza ci si è interrogati sulla necessità di Docker per la compilazione di un'architettura di microservizio.</span><span class="sxs-lookup"><span data-stu-id="202ba-106">Earlier we raised the question “Is Docker necessary when building a microservice architecture?”</span></span> <span data-ttu-id="202ba-107">In realtà, Docker non è affatto necessario.</span><span class="sxs-lookup"><span data-stu-id="202ba-107">The answer is a clear no.</span></span> <span data-ttu-id="202ba-108">Docker può rappresentare una chiave di volta e offrire vantaggi significativi, ma i contenitori e Docker non sono un requisito fondamentale per i microservizi.</span><span class="sxs-lookup"><span data-stu-id="202ba-108">Docker is an enabler and can provide significant benefits, but containers and Docker are not a hard requirement for microservices.</span></span> <span data-ttu-id="202ba-109">Ad esempio, è possibile creare un'applicazione basata su microservizi con o senza Docker quando si usa Azure Service Fabric, che supporta i microservizi in esecuzione come processi semplici o come contenitori Docker.</span><span class="sxs-lookup"><span data-stu-id="202ba-109">As an example, you could create a microservices-based application with or without Docker when using Azure Service Fabric, which supports microservices running as simple processes or as Docker containers.</span></span>

<span data-ttu-id="202ba-110">Tuttavia, se si sa come progettare e sviluppare un'applicazione basata su microservizi che sia basata anche su contenitori Docker, sarà possibile progettare e sviluppare qualsiasi altro modello di applicazione più semplice.</span><span class="sxs-lookup"><span data-stu-id="202ba-110">However, if you know how to design and develop a microservices-based application that is also based on Docker containers, you will be able to design and develop any other, simpler application model.</span></span> <span data-ttu-id="202ba-111">Ad esempio, si potrebbe progettare un'applicazione a tre livelli che richieda anche un approccio a più contenitori.</span><span class="sxs-lookup"><span data-stu-id="202ba-111">For example, you might design a three-tier application that also requires a multi-container approach.</span></span> <span data-ttu-id="202ba-112">Per questo motivo, e poiché le architetture di microservizi rappresentano una tendenza importante nel mondo dei contenitori, questa sezione è incentrata sull'implementazione di un'architettura di microservizi tramite i contenitori Docker.</span><span class="sxs-lookup"><span data-stu-id="202ba-112">Because of that, and because microservice architectures are an important trend within the container world, this section focuses on a microservice architecture implementation using Docker containers.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="202ba-113">[Precedente] (../containerize-net-framework-applications/index.md) [Successivo] (microservice-application-design.md)</span><span class="sxs-lookup"><span data-stu-id="202ba-113">[Previous] (../containerize-net-framework-applications/index.md) [Next] (microservice-application-design.md)</span></span>
