---
title: Servizi flusso di lavoro
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7b05c766-f181-425d-9a3d-2a5e150c85f7
caps.latest.revision: "20"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 8eeb446687b2aa75c90ec02995319fc5a0cbebf3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="workflow-services"></a><span data-ttu-id="8a273-102">Servizi flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="8a273-102">Workflow Services</span></span>
[!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)]<span data-ttu-id="8a273-103"> consente di descrivere in modo completo e dichiarativo un servizio basato sul flusso di lavoro in XAML.</span><span class="sxs-lookup"><span data-stu-id="8a273-103"> allows you to fully describe a workflow-based service declaratively in XAML.</span></span> <span data-ttu-id="8a273-104">È possibile definire un flusso di lavoro che implementa il servizio e descrivere l'endpoint esposto dal servizio, il tutto in XAML.</span><span class="sxs-lookup"><span data-stu-id="8a273-104">You can define a workflow that implements your service and describe endpoints the service exposes, all entirely in XAML.</span></span> <span data-ttu-id="8a273-105">Negli argomenti di questa sezione viene descritto in dettaglio il modello di programmazione che supporta la scrittura dei servizi in modo dichiarativo.</span><span class="sxs-lookup"><span data-stu-id="8a273-105">The topics in this section describe, in detail, the programming model that supports writing services declaratively.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8a273-106">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="8a273-106">In This Section</span></span>  
 [<span data-ttu-id="8a273-107">Panoramica di servizi flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="8a273-107">Workflow Services Overview</span></span>](../../../../docs/framework/wcf/feature-details/workflow-services-overview.md)  
 <span data-ttu-id="8a273-108">Descrive i componenti coinvolti nella creazione e nell'hosting di un servizio flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="8a273-108">Describes the components involved in creating and hosting a workflow service.</span></span>  
  
 [<span data-ttu-id="8a273-109">Attività di messaggistica</span><span class="sxs-lookup"><span data-stu-id="8a273-109">Messaging Activities</span></span>](../../../../docs/framework/wcf/feature-details/messaging-activities.md)  
 <span data-ttu-id="8a273-110">Descrive le attività che consentono ai flussi di lavoro di inviare e ricevere messaggi.</span><span class="sxs-lookup"><span data-stu-id="8a273-110">Discusses activities that allow workflows to send and receive messages.</span></span>  
  
 [<span data-ttu-id="8a273-111">Procedura: creare un servizio flusso di lavoro con attività di messaggistica</span><span class="sxs-lookup"><span data-stu-id="8a273-111">How to: Create a Workflow Service with Messaging Activities</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-workflow-service-with-messaging-activities.md)  
 <span data-ttu-id="8a273-112">Descrive come utilizzare le attività di messaggistica per creare un servizio flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="8a273-112">Describes how to use messaging activities to create a workflow service.</span></span>  
  
 [<span data-ttu-id="8a273-113">Procedura: Accedere a un servizio da un'applicazione flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="8a273-113">How To: Access a Service From a Workflow Application</span></span>](../../../../docs/framework/wcf/feature-details/how-to-access-a-service-from-a-workflow-application.md)  
 <span data-ttu-id="8a273-114">Descrive come chiamare un servizio da un'applicazione flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="8a273-114">Discusses how to call a service from a workflow application.</span></span>  
  
 [<span data-ttu-id="8a273-115">Correlazione</span><span class="sxs-lookup"><span data-stu-id="8a273-115">Correlation</span></span>](../../../../docs/framework/wcf/feature-details/correlation.md)  
 <span data-ttu-id="8a273-116">Descrive come la correlazione esegue il mapping di un messaggio a un altro e a un'istanza.</span><span class="sxs-lookup"><span data-stu-id="8a273-116">Discusses how correlation maps messages to each other and to instances.</span></span>  
  
 [<span data-ttu-id="8a273-117">Elaborazione dei messaggi in ordine</span><span class="sxs-lookup"><span data-stu-id="8a273-117">Out-of-Order Message Processing</span></span>](../../../../docs/framework/wcf/feature-details/out-of-order-message-processing.md)  
 <span data-ttu-id="8a273-118">Descrive la configurazione di un servizio per accettare messaggi non ordinati.</span><span class="sxs-lookup"><span data-stu-id="8a273-118">Describes configuring a service to accept out of order messages.</span></span>  
  
 [<span data-ttu-id="8a273-119">Procedura: creare un servizio flusso di lavoro che chiama il servizio di un altro flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="8a273-119">How to: Create a Workflow Service That Calls Another Workflow Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-workflow-service-that-calls-another-workflow-service.md)  
 <span data-ttu-id="8a273-120">Descrive come chiamare in modo sincrono un servizio flusso di lavoro dall'interno di un altro servizio flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="8a273-120">Describes how to synchronously call a workflow service from within another workflow service.</span></span>  
  
 [<span data-ttu-id="8a273-121">Sviluppo del servizio del flusso di lavoro con priorità al contratto ("contract-first")</span><span class="sxs-lookup"><span data-stu-id="8a273-121">Contract First Workflow Service Development</span></span>](../../../../docs/framework/windows-workflow-foundation/contract-first-workflow-service-development.md)  
 <span data-ttu-id="8a273-122">Viene descritta la creazione di un servizio di flusso di lavoro basato su un contratto di servizio esistente.</span><span class="sxs-lookup"><span data-stu-id="8a273-122">Describes creating a workflow service based on an existing service contract.</span></span>  
  
 [<span data-ttu-id="8a273-123">Procedura: Creare un servizio di flusso di lavoro che utilizza un contratto di servizio esistente</span><span class="sxs-lookup"><span data-stu-id="8a273-123">How to: Create a workflow service that consumes an existing service contract</span></span>](../../../../docs/framework/windows-workflow-foundation/how-to-create-a-workflow-service-that-consumes-an-existing-service-contract.md)  
 <span data-ttu-id="8a273-124">Fornisce un esempio dettagliato di creazione di un servizio di flusso di lavoro tramite un contratto di servizio esistente.</span><span class="sxs-lookup"><span data-stu-id="8a273-124">Provides a step-by-step example of creating a workflow service using an existing service contract.</span></span>  
  
 [<span data-ttu-id="8a273-125">Cenni preliminari sui servizi di hosting del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="8a273-125">Hosting Workflow Services Overview</span></span>](../../../../docs/framework/wcf/feature-details/hosting-workflow-services-overview.md)  
 <span data-ttu-id="8a273-126">Descrive i vari aspetti legati all'hosting di un servizio flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="8a273-126">Describes the different aspects of hosting a workflow service.</span></span>  
  
 [<span data-ttu-id="8a273-127">Uso di contratti nel flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="8a273-127">Using Contracts in Workflow</span></span>](../../../../docs/framework/wcf/feature-details/using-contracts-in-workflow.md)  
 <span data-ttu-id="8a273-128">Descrive i vari tipi di contratti e l'inferenza del contratto.</span><span class="sxs-lookup"><span data-stu-id="8a273-128">Describes the different types of contracts and contract inference.</span></span>
