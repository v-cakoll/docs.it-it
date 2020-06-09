---
title: Servizi flusso di lavoro
ms.date: 03/30/2017
ms.assetid: 7b05c766-f181-425d-9a3d-2a5e150c85f7
ms.openlocfilehash: c7a5c6245702497fcd75341b3ff7ba08dc190fa5
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84600127"
---
# <a name="workflow-services"></a><span data-ttu-id="cd03b-102">Servizi flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="cd03b-102">Workflow Services</span></span>
[!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] <span data-ttu-id="cd03b-103">consente di descrivere in modo completo e dichiarativo un servizio basato sul flusso di lavoro in XAML.</span><span class="sxs-lookup"><span data-stu-id="cd03b-103">allows you to fully describe a workflow-based service declaratively in XAML.</span></span> <span data-ttu-id="cd03b-104">È possibile definire un flusso di lavoro che implementa il servizio e descrivere l'endpoint esposto dal servizio, il tutto in XAML.</span><span class="sxs-lookup"><span data-stu-id="cd03b-104">You can define a workflow that implements your service and describe endpoints the service exposes, all entirely in XAML.</span></span> <span data-ttu-id="cd03b-105">Negli argomenti di questa sezione viene descritto in dettaglio il modello di programmazione che supporta la scrittura dei servizi in modo dichiarativo.</span><span class="sxs-lookup"><span data-stu-id="cd03b-105">The topics in this section describe, in detail, the programming model that supports writing services declaratively.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="cd03b-106">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="cd03b-106">In This Section</span></span>  
 [<span data-ttu-id="cd03b-107">Panoramica dei servizi flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="cd03b-107">Workflow Services Overview</span></span>](workflow-services-overview.md)  
 <span data-ttu-id="cd03b-108">Descrive i componenti coinvolti nella creazione e nell'hosting di un servizio flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="cd03b-108">Describes the components involved in creating and hosting a workflow service.</span></span>  
  
 [<span data-ttu-id="cd03b-109">Attività di messaggistica</span><span class="sxs-lookup"><span data-stu-id="cd03b-109">Messaging Activities</span></span>](messaging-activities.md)  
 <span data-ttu-id="cd03b-110">Descrive le attività che consentono ai flussi di lavoro di inviare e ricevere messaggi.</span><span class="sxs-lookup"><span data-stu-id="cd03b-110">Discusses activities that allow workflows to send and receive messages.</span></span>  
  
 [<span data-ttu-id="cd03b-111">Procedura: creare un servizio flusso di lavoro con attività di messaggistica</span><span class="sxs-lookup"><span data-stu-id="cd03b-111">How to: Create a Workflow Service with Messaging Activities</span></span>](how-to-create-a-workflow-service-with-messaging-activities.md)  
 <span data-ttu-id="cd03b-112">Descrive come utilizzare le attività di messaggistica per creare un servizio flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="cd03b-112">Describes how to use messaging activities to create a workflow service.</span></span>  
  
 [<span data-ttu-id="cd03b-113">Procedura: accesso a un servizio da un'applicazione flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="cd03b-113">How To: Access a Service From a Workflow Application</span></span>](how-to-access-a-service-from-a-workflow-application.md)  
 <span data-ttu-id="cd03b-114">Descrive come chiamare un servizio da un'applicazione flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="cd03b-114">Discusses how to call a service from a workflow application.</span></span>  
  
 [<span data-ttu-id="cd03b-115">Correlation</span><span class="sxs-lookup"><span data-stu-id="cd03b-115">Correlation</span></span>](correlation.md)  
 <span data-ttu-id="cd03b-116">Descrive come la correlazione esegue il mapping di un messaggio a un altro e a un'istanza.</span><span class="sxs-lookup"><span data-stu-id="cd03b-116">Discusses how correlation maps messages to each other and to instances.</span></span>  
  
 [<span data-ttu-id="cd03b-117">Elaborazione di messaggi nell'ordine non corretto</span><span class="sxs-lookup"><span data-stu-id="cd03b-117">Out-of-Order Message Processing</span></span>](out-of-order-message-processing.md)  
 <span data-ttu-id="cd03b-118">Descrive la configurazione di un servizio per accettare messaggi non ordinati.</span><span class="sxs-lookup"><span data-stu-id="cd03b-118">Describes configuring a service to accept out of order messages.</span></span>  
  
 [<span data-ttu-id="cd03b-119">Sviluppo del servizio del flusso di lavoro con priorità al contratto ("contract-first")</span><span class="sxs-lookup"><span data-stu-id="cd03b-119">Contract First Workflow Service Development</span></span>](../../windows-workflow-foundation/contract-first-workflow-service-development.md)  
 <span data-ttu-id="cd03b-120">Viene descritta la creazione di un servizio di flusso di lavoro basato su un contratto di servizio esistente.</span><span class="sxs-lookup"><span data-stu-id="cd03b-120">Describes creating a workflow service based on an existing service contract.</span></span>  
  
 [<span data-ttu-id="cd03b-121">Procedura: Creare un servizio di flusso di lavoro che utilizza un contratto di servizio esistente</span><span class="sxs-lookup"><span data-stu-id="cd03b-121">How to: Create a workflow service that consumes an existing service contract</span></span>](../../windows-workflow-foundation/how-to-create-a-workflow-service-that-consumes-an-existing-service-contract.md)  
 <span data-ttu-id="cd03b-122">Fornisce un esempio dettagliato di creazione di un servizio di flusso di lavoro tramite un contratto di servizio esistente.</span><span class="sxs-lookup"><span data-stu-id="cd03b-122">Provides a step-by-step example of creating a workflow service using an existing service contract.</span></span>  
  
 [<span data-ttu-id="cd03b-123">Panoramica dell'hosting dei servizi flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="cd03b-123">Hosting Workflow Services Overview</span></span>](hosting-workflow-services-overview.md)  
 <span data-ttu-id="cd03b-124">Descrive i vari aspetti legati all'hosting di un servizio flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="cd03b-124">Describes the different aspects of hosting a workflow service.</span></span>  
  
 [<span data-ttu-id="cd03b-125">Uso di contratti nel flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="cd03b-125">Using Contracts in Workflow</span></span>](using-contracts-in-workflow.md)  
 <span data-ttu-id="cd03b-126">Descrive i vari tipi di contratti e l'inferenza del contratto.</span><span class="sxs-lookup"><span data-stu-id="cd03b-126">Describes the different types of contracts and contract inference.</span></span>
