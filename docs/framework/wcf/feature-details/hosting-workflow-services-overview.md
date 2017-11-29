---
title: Panoramica dell'hosting dei servizi flusso di lavoro
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 19f3704f-06bf-4eeb-8724-5224e02d7ead
caps.latest.revision: "12"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 2c38cd352eb860982b9b1e3aa32daa7aeeee9ae9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="hosting-workflow-services-overview"></a><span data-ttu-id="0d5eb-102">Panoramica dell'hosting dei servizi flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="0d5eb-102">Hosting Workflow Services Overview</span></span>
<span data-ttu-id="0d5eb-103">I servizi flusso di lavoro devono essere ospitati per poter essere eseguiti.</span><span class="sxs-lookup"><span data-stu-id="0d5eb-103">Workflow services must be hosted to execute.</span></span> <span data-ttu-id="0d5eb-104">L'oggetto <xref:System.ServiceModel.WorkflowServiceHost> è l'host del flusso di lavoro predefinito che supporta più istanze, la configurazione e la messaggistica di WCF, anche se per ospitare i flussi di lavoro non è necessario utilizzare la messaggistica.</span><span class="sxs-lookup"><span data-stu-id="0d5eb-104">The <xref:System.ServiceModel.WorkflowServiceHost> is the out-of-the-box workflow host that supports multiple instances, configuration, and WCF messaging (although the workflows aren’t required to use messaging in order to be hosted).</span></span>  <span data-ttu-id="0d5eb-105">Inoltre si integra con la persistenza, il rilevamento e il controllo dell'istanza tramite un set di comportamenti del servizio.</span><span class="sxs-lookup"><span data-stu-id="0d5eb-105">It also integrates with persistence, tracking, and instance control through a set of service behaviors.</span></span>  <span data-ttu-id="0d5eb-106">Analogamente all'oggetto <xref:System.ServiceModel.ServiceHost> di WCF, l'oggetto <xref:System.ServiceModel.WorkflowServiceHost> può essere un servizio indipendente ospitato in qualsiasi applicazione .NET gestita o un servizio ospitato su Web (come un file con estensione xamlx) in IIS/WAS.</span><span class="sxs-lookup"><span data-stu-id="0d5eb-106">Just like WCF’s <xref:System.ServiceModel.ServiceHost>, the <xref:System.ServiceModel.WorkflowServiceHost> can be self-hosted in any managed .NET application, or web-hosted (as a .xamlx file) in IIS / WAS.</span></span>  <span data-ttu-id="0d5eb-107">Negli argomenti in questa sezione viene descritto come ospitare un servizio flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="0d5eb-107">Topics in this section describe how to host a workflow service.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0d5eb-108">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="0d5eb-108">In This Section</span></span>  
 [<span data-ttu-id="0d5eb-109">Servizi di hosting del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="0d5eb-109">Hosting Workflow Services</span></span>](../../../../docs/framework/wcf/feature-details/hosting-workflow-services.md)  
 <span data-ttu-id="0d5eb-110">Viene descritto l'hosting dei servizi flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="0d5eb-110">Describes hosting workflow services.</span></span>  
  
 [<span data-ttu-id="0d5eb-111">Elementi interni dell'Host del servizio del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="0d5eb-111">Workflow Service Host Internals</span></span>](../../../../docs/framework/wcf/feature-details/workflow-service-host-internals.md)  
 <span data-ttu-id="0d5eb-112">Viene descritta l'elaborazione dei messaggi in arrivo da parte di <xref:System.ServiceModel.WorkflowServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="0d5eb-112">Describes how <xref:System.ServiceModel.WorkflowServiceHost> processes incoming messages.</span></span>  
  
 [<span data-ttu-id="0d5eb-113">Estensibilità Host del servizio del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="0d5eb-113">Workflow Service Host Extensibility</span></span>](../../../../docs/framework/wcf/feature-details/workflow-service-host-extensibility.md)  
 <span data-ttu-id="0d5eb-114">Viene descritto come estendere la funzionalità dell'host del servizio flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="0d5eb-114">Describes how to extend the functionality of the workflow service host.</span></span>  
  
 [<span data-ttu-id="0d5eb-115">Endpoint di controllo di flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="0d5eb-115">Workflow Control Endpoint</span></span>](../../../../docs/framework/wcf/feature-details/workflow-control-endpoint.md)  
 <span data-ttu-id="0d5eb-116">Viene descritto come definire un endpoint che consente di creare istanze del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="0d5eb-116">Describes how to define an endpoint that allows you to create workflow instances.</span></span>  
  
 [<span data-ttu-id="0d5eb-117">Procedura: ospitare un flusso di lavoro non di servizio in IIS</span><span class="sxs-lookup"><span data-stu-id="0d5eb-117">How to: Host a non-service workflow in IIS</span></span>](../../../../docs/framework/wcf/feature-details/how-to-host-a-non-service-workflow-in-iis.md)  
 <span data-ttu-id="0d5eb-118">Viene illustrato l'hosting di un flusso di lavoro che non è un servizio flusso di lavoro in IIS.</span><span class="sxs-lookup"><span data-stu-id="0d5eb-118">Demonstrates hosting a workflow that is not a workflow service in IIS.</span></span>  
  
 [<span data-ttu-id="0d5eb-119">Procedura: ospitare un servizio flusso di lavoro con Windows Server AppFabric</span><span class="sxs-lookup"><span data-stu-id="0d5eb-119">How to: Host a Workflow Service with Windows Server App Fabric</span></span>](../../../../docs/framework/wcf/feature-details/how-to-host-a-workflow-service-with-windows-server-app-fabric.md)  
 <span data-ttu-id="0d5eb-120">Viene illustrato come ospitare un servizio flusso di lavoro esistente in Windows Server AppFabric.</span><span class="sxs-lookup"><span data-stu-id="0d5eb-120">Demonstrates how to host an existing workflow service in Windows Server App Fabric.</span></span>  
  
 [<span data-ttu-id="0d5eb-121">Configurazione di WorkflowServiceHost</span><span class="sxs-lookup"><span data-stu-id="0d5eb-121">Configuring WorkflowServiceHost</span></span>](../../../../docs/framework/wcf/feature-details/configuring-workflowservicehost.md)  
 <span data-ttu-id="0d5eb-122">Viene descritto come controllare il comportamento di persistenza, di rilevamento, di inattività e dell'eccezione non gestita.</span><span class="sxs-lookup"><span data-stu-id="0d5eb-122">Describes how to control persistence, tracking, idle, and unhandled exception behavior.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="0d5eb-123">Riferimento</span><span class="sxs-lookup"><span data-stu-id="0d5eb-123">Reference</span></span>  
 <xref:System.ServiceModel.Activities.WorkflowServiceHost>  
  
 <xref:System.ServiceModel.Activities.WorkflowService>  
  
 <xref:System.ServiceModel.Activation.ServiceHostFactory>  
  
 <xref:System.ServiceModel.Activation.ServiceHostFactoryBase>  
  
 <xref:System.ServiceModel.Activation.WorkflowServiceHostFactory>  
  
## <a name="related-sections"></a><span data-ttu-id="0d5eb-124">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="0d5eb-124">Related Sections</span></span>  
 [<span data-ttu-id="0d5eb-125">Servizi flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="0d5eb-125">Workflow Services</span></span>](../../../../docs/framework/wcf/feature-details/workflow-services.md)
