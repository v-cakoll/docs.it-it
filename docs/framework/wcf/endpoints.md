---
title: Endpoint di Windows Communication Foundation
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: endpoints [WCF]
ms.assetid: bd0c310f-dd9f-4081-9be2-3db5909850b6
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0725c4f4275853cce958072a57d7f6ca4059e8cf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="windows-communication-foundation-endpoints"></a><span data-ttu-id="1a88a-102">Endpoint di Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="1a88a-102">Windows Communication Foundation Endpoints</span></span>
<span data-ttu-id="1a88a-103">Tutte le comunicazioni con un [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] servizio avviene tramite il *endpoint* del servizio.</span><span class="sxs-lookup"><span data-stu-id="1a88a-103">All communication with a [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] service occurs through the *endpoints* of the service.</span></span> <span data-ttu-id="1a88a-104">Gli endpoint forniscono ai client l'accesso alla funzionalità offerta da un servizio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1a88a-104">Endpoints provide clients access to the functionality that a [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] service offers.</span></span>  
  
 <span data-ttu-id="1a88a-105">Per una panoramica su come creare un endpoint, vedere [Cenni preliminari sulla creazione di Endpoint](../../../docs/framework/wcf/endpoint-creation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="1a88a-105">For an overview about how to create an endpoint, see [Endpoint Creation Overview](../../../docs/framework/wcf/endpoint-creation-overview.md).</span></span> <span data-ttu-id="1a88a-106">Ogni endpoint contiene:</span><span class="sxs-lookup"><span data-stu-id="1a88a-106">Each endpoint contains:</span></span>  
  
-   <span data-ttu-id="1a88a-107">Un indirizzo che indica dove si trova l'endpoint.</span><span class="sxs-lookup"><span data-stu-id="1a88a-107">An address that indicates where to find the endpoint.</span></span>  
  
-   <span data-ttu-id="1a88a-108">Un'associazione che specifica in che modo un client può comunicare con l'endpoint.</span><span class="sxs-lookup"><span data-stu-id="1a88a-108">A binding that specifies how a client can communicate with the endpoint.</span></span>  
  
-   <span data-ttu-id="1a88a-109">Un contratto che identifica i metodi disponibili.</span><span class="sxs-lookup"><span data-stu-id="1a88a-109">A contract that identifies the methods available.</span></span>  
  
 <span data-ttu-id="1a88a-110">Per istruzioni su come specificare queste singole parti di un endpoint, vedere:</span><span class="sxs-lookup"><span data-stu-id="1a88a-110">For descriptions about how to specify these individual parts of an endpoint, see:</span></span>  
  
-   [<span data-ttu-id="1a88a-111">Specifica di un indirizzo dell'endpoint</span><span class="sxs-lookup"><span data-stu-id="1a88a-111">Specifying an Endpoint Address</span></span>](../../../docs/framework/wcf/specifying-an-endpoint-address.md)  
  
-   [<span data-ttu-id="1a88a-112">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="1a88a-112">Using Bindings to Configure Services and Clients</span></span>](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
  
-   [<span data-ttu-id="1a88a-113">Progettazione e implementazione di servizi</span><span class="sxs-lookup"><span data-stu-id="1a88a-113">Designing and Implementing Services</span></span>](../../../docs/framework/wcf/designing-and-implementing-services.md)  
  
## <a name="in-this-section"></a><span data-ttu-id="1a88a-114">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="1a88a-114">In This Section</span></span>  
 [<span data-ttu-id="1a88a-115">Panoramica della creazione di endpoint</span><span class="sxs-lookup"><span data-stu-id="1a88a-115">Endpoint Creation Overview</span></span>](../../../docs/framework/wcf/endpoint-creation-overview.md)  
 <span data-ttu-id="1a88a-116">Viene descritta la struttura di un endpoint e viene illustrato come definire un endpoint nella configurazione e nel codice, nonché come usare gli endpoint, le associazioni e i comportamenti predefiniti forniti dal runtime.</span><span class="sxs-lookup"><span data-stu-id="1a88a-116">Describes the structure of an endpoint and outlines how to define an endpoint in configuration and in code, as well as how to use the default endpoints, bindings, and behaviors provided by the runtime.</span></span>  
  
 [<span data-ttu-id="1a88a-117">Specifica di un indirizzo dell'endpoint</span><span class="sxs-lookup"><span data-stu-id="1a88a-117">Specifying an Endpoint Address</span></span>](../../../docs/framework/wcf/specifying-an-endpoint-address.md)  
 <span data-ttu-id="1a88a-118">Viene descritto come si verifica la comunicazione con un servizio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] tramite gli endpoint.</span><span class="sxs-lookup"><span data-stu-id="1a88a-118">Describes how communication with a [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] service occurs through endpoints.</span></span>  
  
 [<span data-ttu-id="1a88a-119">Procedura: Creare un endpoint di servizio nella configurazione</span><span class="sxs-lookup"><span data-stu-id="1a88a-119">How to: Create a Service Endpoint in Configuration</span></span>](../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md)  
 <span data-ttu-id="1a88a-120">Viene illustrato come creare un endpoint del servizio nella configurazione.</span><span class="sxs-lookup"><span data-stu-id="1a88a-120">Demonstrates how to create a service endpoint in configuration.</span></span>  
  
 [<span data-ttu-id="1a88a-121">Procedura: Creare un endpoint di servizio nel codice</span><span class="sxs-lookup"><span data-stu-id="1a88a-121">How to: Create a Service Endpoint in Code</span></span>](../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-code.md)  
 <span data-ttu-id="1a88a-122">Viene illustrato come creare un endpoint del servizio nel codice.</span><span class="sxs-lookup"><span data-stu-id="1a88a-122">Demonstrates how to create a service endpoint in code.</span></span>  
  
 [<span data-ttu-id="1a88a-123">Pubblicazione di endpoint dei metadati</span><span class="sxs-lookup"><span data-stu-id="1a88a-123">Publishing Metadata Endpoints</span></span>](../../../docs/framework/wcf/publishing-metadata-endpoints.md)  
 <span data-ttu-id="1a88a-124">Viene illustrato come pubblicare metadati mediante la pubblicazione degli endpoint dei metadati nella configurazione e nel codice.</span><span class="sxs-lookup"><span data-stu-id="1a88a-124">Demonstrates how to publish metadata by publishing metadata endpoints in configuration and in code.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="1a88a-125">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="1a88a-125">Reference</span></span>  
 <xref:System.ServiceModel.EndpointAddress>  
  
## <a name="related-sections"></a><span data-ttu-id="1a88a-126">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="1a88a-126">Related Sections</span></span>  
 [<span data-ttu-id="1a88a-127">Ciclo di vita della programmazione di base</span><span class="sxs-lookup"><span data-stu-id="1a88a-127">Basic Programming Lifecycle</span></span>](../../../docs/framework/wcf/basic-programming-lifecycle.md)
