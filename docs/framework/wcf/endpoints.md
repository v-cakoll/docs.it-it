---
title: Endpoint di Windows Communication Foundation
ms.date: 03/30/2017
helpviewer_keywords:
- endpoints [WCF]
ms.assetid: bd0c310f-dd9f-4081-9be2-3db5909850b6
ms.openlocfilehash: b55abe937701f8708643efa2ea4cb62514b3521b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61923188"
---
# <a name="windows-communication-foundation-endpoints"></a><span data-ttu-id="86094-102">Endpoint di Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="86094-102">Windows Communication Foundation Endpoints</span></span>
<span data-ttu-id="86094-103">Tutte le comunicazioni con un servizio Windows Communication Foundation (WCF) viene eseguita tramite il *endpoint* del servizio.</span><span class="sxs-lookup"><span data-stu-id="86094-103">All communication with a Windows Communication Foundation (WCF) service occurs through the *endpoints* of the service.</span></span> <span data-ttu-id="86094-104">Gli endpoint forniscono ai client l'accesso alla funzionalità offerta da un servizio WCF.</span><span class="sxs-lookup"><span data-stu-id="86094-104">Endpoints provide clients access to the functionality that a WCF service offers.</span></span>  
  
 <span data-ttu-id="86094-105">Per una panoramica su come creare un endpoint, vedere [Cenni preliminari sulla creazione di Endpoint](../../../docs/framework/wcf/endpoint-creation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="86094-105">For an overview about how to create an endpoint, see [Endpoint Creation Overview](../../../docs/framework/wcf/endpoint-creation-overview.md).</span></span> <span data-ttu-id="86094-106">Ogni endpoint contiene:</span><span class="sxs-lookup"><span data-stu-id="86094-106">Each endpoint contains:</span></span>  
  
- <span data-ttu-id="86094-107">Un indirizzo che indica dove si trova l'endpoint.</span><span class="sxs-lookup"><span data-stu-id="86094-107">An address that indicates where to find the endpoint.</span></span>  
  
- <span data-ttu-id="86094-108">Un'associazione che specifica in che modo un client può comunicare con l'endpoint.</span><span class="sxs-lookup"><span data-stu-id="86094-108">A binding that specifies how a client can communicate with the endpoint.</span></span>  
  
- <span data-ttu-id="86094-109">Un contratto che identifica i metodi disponibili.</span><span class="sxs-lookup"><span data-stu-id="86094-109">A contract that identifies the methods available.</span></span>  
  
 <span data-ttu-id="86094-110">Per istruzioni su come specificare queste singole parti di un endpoint, vedere:</span><span class="sxs-lookup"><span data-stu-id="86094-110">For descriptions about how to specify these individual parts of an endpoint, see:</span></span>  
  
- [<span data-ttu-id="86094-111">Specifica di un indirizzo dell'endpoint</span><span class="sxs-lookup"><span data-stu-id="86094-111">Specifying an Endpoint Address</span></span>](../../../docs/framework/wcf/specifying-an-endpoint-address.md)  
  
- [<span data-ttu-id="86094-112">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="86094-112">Using Bindings to Configure Services and Clients</span></span>](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
  
- [<span data-ttu-id="86094-113">Progettazione e implementazione di servizi</span><span class="sxs-lookup"><span data-stu-id="86094-113">Designing and Implementing Services</span></span>](../../../docs/framework/wcf/designing-and-implementing-services.md)  
  
## <a name="in-this-section"></a><span data-ttu-id="86094-114">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="86094-114">In This Section</span></span>  
 [<span data-ttu-id="86094-115">Panoramica della creazione di endpoint</span><span class="sxs-lookup"><span data-stu-id="86094-115">Endpoint Creation Overview</span></span>](../../../docs/framework/wcf/endpoint-creation-overview.md)  
 <span data-ttu-id="86094-116">Viene descritta la struttura di un endpoint e viene illustrato come definire un endpoint nella configurazione e nel codice, nonché come usare gli endpoint, le associazioni e i comportamenti predefiniti forniti dal runtime.</span><span class="sxs-lookup"><span data-stu-id="86094-116">Describes the structure of an endpoint and outlines how to define an endpoint in configuration and in code, as well as how to use the default endpoints, bindings, and behaviors provided by the runtime.</span></span>  
  
 [<span data-ttu-id="86094-117">Specifica di un indirizzo dell'endpoint</span><span class="sxs-lookup"><span data-stu-id="86094-117">Specifying an Endpoint Address</span></span>](../../../docs/framework/wcf/specifying-an-endpoint-address.md)  
 <span data-ttu-id="86094-118">Viene descritto come la comunicazione con un servizio WCF avviene tramite gli endpoint.</span><span class="sxs-lookup"><span data-stu-id="86094-118">Describes how communication with a WCF service occurs through endpoints.</span></span>  
  
 [<span data-ttu-id="86094-119">Procedura: Creare un Endpoint del servizio nella configurazione</span><span class="sxs-lookup"><span data-stu-id="86094-119">How to: Create a Service Endpoint in Configuration</span></span>](../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md)  
 <span data-ttu-id="86094-120">Viene illustrato come creare un endpoint del servizio nella configurazione.</span><span class="sxs-lookup"><span data-stu-id="86094-120">Demonstrates how to create a service endpoint in configuration.</span></span>  
  
 [<span data-ttu-id="86094-121">Procedura: Creare un Endpoint del servizio nel codice</span><span class="sxs-lookup"><span data-stu-id="86094-121">How to: Create a Service Endpoint in Code</span></span>](../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-code.md)  
 <span data-ttu-id="86094-122">Viene illustrato come creare un endpoint del servizio nel codice.</span><span class="sxs-lookup"><span data-stu-id="86094-122">Demonstrates how to create a service endpoint in code.</span></span>  
  
 [<span data-ttu-id="86094-123">Pubblicazione di endpoint dei metadati</span><span class="sxs-lookup"><span data-stu-id="86094-123">Publishing Metadata Endpoints</span></span>](../../../docs/framework/wcf/publishing-metadata-endpoints.md)  
 <span data-ttu-id="86094-124">Viene illustrato come pubblicare metadati mediante la pubblicazione degli endpoint dei metadati nella configurazione e nel codice.</span><span class="sxs-lookup"><span data-stu-id="86094-124">Demonstrates how to publish metadata by publishing metadata endpoints in configuration and in code.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="86094-125">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="86094-125">Reference</span></span>  
 <xref:System.ServiceModel.EndpointAddress>  
  
## <a name="related-sections"></a><span data-ttu-id="86094-126">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="86094-126">Related Sections</span></span>  
 [<span data-ttu-id="86094-127">Ciclo di vita della programmazione di base</span><span class="sxs-lookup"><span data-stu-id="86094-127">Basic Programming Lifecycle</span></span>](../../../docs/framework/wcf/basic-programming-lifecycle.md)
