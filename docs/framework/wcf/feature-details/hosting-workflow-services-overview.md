---
title: Panoramica dell'hosting dei servizi flusso di lavoro
ms.date: 03/30/2017
ms.assetid: 19f3704f-06bf-4eeb-8724-5224e02d7ead
ms.openlocfilehash: dbe271e30e9c4e98a52c01ffaa21de25c127c7ff
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/03/2018
ms.locfileid: "48245097"
---
# <a name="hosting-workflow-services-overview"></a><span data-ttu-id="256dc-102">Panoramica dell'hosting dei servizi flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="256dc-102">Hosting Workflow Services Overview</span></span>
<span data-ttu-id="256dc-103">I servizi flusso di lavoro devono essere ospitati per poter essere eseguiti.</span><span class="sxs-lookup"><span data-stu-id="256dc-103">Workflow services must be hosted to execute.</span></span> <span data-ttu-id="256dc-104">L'oggetto <xref:System.ServiceModel.WorkflowServiceHost> è l'host del flusso di lavoro predefinito che supporta più istanze, la configurazione e la messaggistica di WCF, anche se per ospitare i flussi di lavoro non è necessario utilizzare la messaggistica.</span><span class="sxs-lookup"><span data-stu-id="256dc-104">The <xref:System.ServiceModel.WorkflowServiceHost> is the out-of-the-box workflow host that supports multiple instances, configuration, and WCF messaging (although the workflows aren’t required to use messaging in order to be hosted).</span></span>  <span data-ttu-id="256dc-105">Inoltre si integra con la persistenza, il rilevamento e il controllo dell'istanza tramite un set di comportamenti del servizio.</span><span class="sxs-lookup"><span data-stu-id="256dc-105">It also integrates with persistence, tracking, and instance control through a set of service behaviors.</span></span>  <span data-ttu-id="256dc-106">Analogamente all'oggetto <xref:System.ServiceModel.ServiceHost> di WCF, l'oggetto <xref:System.ServiceModel.WorkflowServiceHost> può essere un servizio indipendente ospitato in qualsiasi applicazione .NET gestita o un servizio ospitato su Web (come un file con estensione xamlx) in IIS/WAS.</span><span class="sxs-lookup"><span data-stu-id="256dc-106">Just like WCF’s <xref:System.ServiceModel.ServiceHost>, the <xref:System.ServiceModel.WorkflowServiceHost> can be self-hosted in any managed .NET application, or web-hosted (as a .xamlx file) in IIS / WAS.</span></span>  <span data-ttu-id="256dc-107">Negli argomenti in questa sezione viene descritto come ospitare un servizio flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="256dc-107">Topics in this section describe how to host a workflow service.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="256dc-108">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="256dc-108">In This Section</span></span>  
 [<span data-ttu-id="256dc-109">Hosting di servizi flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="256dc-109">Hosting Workflow Services</span></span>](../../../../docs/framework/wcf/feature-details/hosting-workflow-services.md)  
 <span data-ttu-id="256dc-110">Viene descritto l'hosting dei servizi flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="256dc-110">Describes hosting workflow services.</span></span>  
  
 [<span data-ttu-id="256dc-111">Elementi interni dell'host dei servizi flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="256dc-111">Workflow Service Host Internals</span></span>](../../../../docs/framework/wcf/feature-details/workflow-service-host-internals.md)  
 <span data-ttu-id="256dc-112">Viene descritta l'elaborazione dei messaggi in arrivo da parte di <xref:System.ServiceModel.WorkflowServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="256dc-112">Describes how <xref:System.ServiceModel.WorkflowServiceHost> processes incoming messages.</span></span>  
  
 [<span data-ttu-id="256dc-113">Estendibilità dell'host dei servizi flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="256dc-113">Workflow Service Host Extensibility</span></span>](../../../../docs/framework/wcf/feature-details/workflow-service-host-extensibility.md)  
 <span data-ttu-id="256dc-114">Viene descritto come estendere la funzionalità dell'host del servizio flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="256dc-114">Describes how to extend the functionality of the workflow service host.</span></span>  
  
 [<span data-ttu-id="256dc-115">Endpoint di controllo del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="256dc-115">Workflow Control Endpoint</span></span>](../../../../docs/framework/wcf/feature-details/workflow-control-endpoint.md)  
 <span data-ttu-id="256dc-116">Viene descritto come definire un endpoint che consente di creare istanze del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="256dc-116">Describes how to define an endpoint that allows you to create workflow instances.</span></span>
  
 [<span data-ttu-id="256dc-117">Procedura: Ospitare un servizio flusso di lavoro con Windows Server AppFabric</span><span class="sxs-lookup"><span data-stu-id="256dc-117">How to: Host a Workflow Service with Windows Server App Fabric</span></span>](../../../../docs/framework/wcf/feature-details/how-to-host-a-workflow-service-with-windows-server-app-fabric.md)  
 <span data-ttu-id="256dc-118">Viene illustrato come ospitare un servizio flusso di lavoro esistente in Windows Server AppFabric.</span><span class="sxs-lookup"><span data-stu-id="256dc-118">Demonstrates how to host an existing workflow service in Windows Server App Fabric.</span></span>  
  
 [<span data-ttu-id="256dc-119">Configurazione di WorkflowServiceHost</span><span class="sxs-lookup"><span data-stu-id="256dc-119">Configuring WorkflowServiceHost</span></span>](../../../../docs/framework/wcf/feature-details/configuring-workflowservicehost.md)  
 <span data-ttu-id="256dc-120">Viene descritto come controllare il comportamento di persistenza, di rilevamento, di inattività e dell'eccezione non gestita.</span><span class="sxs-lookup"><span data-stu-id="256dc-120">Describes how to control persistence, tracking, idle, and unhandled exception behavior.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="256dc-121">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="256dc-121">Reference</span></span>  
 <xref:System.ServiceModel.Activities.WorkflowServiceHost>  
  
 <xref:System.ServiceModel.Activities.WorkflowService>  
  
 <xref:System.ServiceModel.Activation.ServiceHostFactory>  
  
 <xref:System.ServiceModel.Activation.ServiceHostFactoryBase>  
  
 <xref:System.ServiceModel.Activation.WorkflowServiceHostFactory>  
  
## <a name="related-sections"></a><span data-ttu-id="256dc-122">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="256dc-122">Related Sections</span></span>  
 [<span data-ttu-id="256dc-123">Servizi flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="256dc-123">Workflow Services</span></span>](../../../../docs/framework/wcf/feature-details/workflow-services.md)
