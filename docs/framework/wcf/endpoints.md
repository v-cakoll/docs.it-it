---
title: Endpoint di Windows Communication Foundation
ms.date: 03/30/2017
helpviewer_keywords:
- endpoints [WCF]
ms.assetid: bd0c310f-dd9f-4081-9be2-3db5909850b6
ms.openlocfilehash: f11a8198d38a01fe27a84a3e613e1ff066c25b9d
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319906"
---
# <a name="windows-communication-foundation-endpoints"></a><span data-ttu-id="1a965-102">Endpoint di Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="1a965-102">Windows Communication Foundation Endpoints</span></span>
<span data-ttu-id="1a965-103">Tutte le comunicazioni con un servizio Windows Communication Foundation (WCF) avvengono tramite gli *endpoint* del servizio.</span><span class="sxs-lookup"><span data-stu-id="1a965-103">All communication with a Windows Communication Foundation (WCF) service occurs through the *endpoints* of the service.</span></span> <span data-ttu-id="1a965-104">Gli endpoint forniscono ai client l'accesso alla funzionalità offerta da un servizio WCF.</span><span class="sxs-lookup"><span data-stu-id="1a965-104">Endpoints provide clients access to the functionality that a WCF service offers.</span></span>  
  
 <span data-ttu-id="1a965-105">Per una panoramica su come creare un endpoint, vedere [Cenni preliminari sulla creazione di endpoint](endpoint-creation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="1a965-105">For an overview about how to create an endpoint, see [Endpoint Creation Overview](endpoint-creation-overview.md).</span></span> <span data-ttu-id="1a965-106">Ogni endpoint contiene:</span><span class="sxs-lookup"><span data-stu-id="1a965-106">Each endpoint contains:</span></span>  
  
- <span data-ttu-id="1a965-107">Un indirizzo che indica dove si trova l'endpoint.</span><span class="sxs-lookup"><span data-stu-id="1a965-107">An address that indicates where to find the endpoint.</span></span>  
  
- <span data-ttu-id="1a965-108">Un'associazione che specifica in che modo un client può comunicare con l'endpoint.</span><span class="sxs-lookup"><span data-stu-id="1a965-108">A binding that specifies how a client can communicate with the endpoint.</span></span>  
  
- <span data-ttu-id="1a965-109">Un contratto che identifica i metodi disponibili.</span><span class="sxs-lookup"><span data-stu-id="1a965-109">A contract that identifies the methods available.</span></span>  
  
 <span data-ttu-id="1a965-110">Per istruzioni su come specificare queste singole parti di un endpoint, vedere:</span><span class="sxs-lookup"><span data-stu-id="1a965-110">For descriptions about how to specify these individual parts of an endpoint, see:</span></span>  
  
- [<span data-ttu-id="1a965-111">Specifica di un indirizzo dell'endpoint</span><span class="sxs-lookup"><span data-stu-id="1a965-111">Specifying an Endpoint Address</span></span>](specifying-an-endpoint-address.md)  
  
- [<span data-ttu-id="1a965-112">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="1a965-112">Using Bindings to Configure Services and Clients</span></span>](using-bindings-to-configure-services-and-clients.md)  
  
- [<span data-ttu-id="1a965-113">Progettazione e implementazione di servizi</span><span class="sxs-lookup"><span data-stu-id="1a965-113">Designing and Implementing Services</span></span>](designing-and-implementing-services.md)  
  
## <a name="in-this-section"></a><span data-ttu-id="1a965-114">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="1a965-114">In This Section</span></span>  
 [<span data-ttu-id="1a965-115">Panoramica della creazione di endpoint</span><span class="sxs-lookup"><span data-stu-id="1a965-115">Endpoint Creation Overview</span></span>](endpoint-creation-overview.md)  
 <span data-ttu-id="1a965-116">Viene descritta la struttura di un endpoint e viene illustrato come definire un endpoint nella configurazione e nel codice, nonché come usare gli endpoint, le associazioni e i comportamenti predefiniti forniti dal runtime.</span><span class="sxs-lookup"><span data-stu-id="1a965-116">Describes the structure of an endpoint and outlines how to define an endpoint in configuration and in code, as well as how to use the default endpoints, bindings, and behaviors provided by the runtime.</span></span>  
  
 [<span data-ttu-id="1a965-117">Specifica di un indirizzo dell'endpoint</span><span class="sxs-lookup"><span data-stu-id="1a965-117">Specifying an Endpoint Address</span></span>](specifying-an-endpoint-address.md)  
 <span data-ttu-id="1a965-118">Viene descritto il modo in cui la comunicazione con un servizio WCF viene eseguita tramite gli endpoint.</span><span class="sxs-lookup"><span data-stu-id="1a965-118">Describes how communication with a WCF service occurs through endpoints.</span></span>  
  
 [<span data-ttu-id="1a965-119">Procedura: Creare un endpoint di servizio nella configurazione</span><span class="sxs-lookup"><span data-stu-id="1a965-119">How to: Create a Service Endpoint in Configuration</span></span>](./feature-details/how-to-create-a-service-endpoint-in-configuration.md)  
 <span data-ttu-id="1a965-120">Viene illustrato come creare un endpoint del servizio nella configurazione.</span><span class="sxs-lookup"><span data-stu-id="1a965-120">Demonstrates how to create a service endpoint in configuration.</span></span>  
  
 [<span data-ttu-id="1a965-121">Procedura: Creare un endpoint di servizio nel codice</span><span class="sxs-lookup"><span data-stu-id="1a965-121">How to: Create a Service Endpoint in Code</span></span>](./feature-details/how-to-create-a-service-endpoint-in-code.md)  
 <span data-ttu-id="1a965-122">Viene illustrato come creare un endpoint del servizio nel codice.</span><span class="sxs-lookup"><span data-stu-id="1a965-122">Demonstrates how to create a service endpoint in code.</span></span>  
  
 [<span data-ttu-id="1a965-123">Pubblicazione di endpoint dei metadati</span><span class="sxs-lookup"><span data-stu-id="1a965-123">Publishing Metadata Endpoints</span></span>](publishing-metadata-endpoints.md)  
 <span data-ttu-id="1a965-124">Viene illustrato come pubblicare metadati mediante la pubblicazione degli endpoint dei metadati nella configurazione e nel codice.</span><span class="sxs-lookup"><span data-stu-id="1a965-124">Demonstrates how to publish metadata by publishing metadata endpoints in configuration and in code.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="1a965-125">Reference</span><span class="sxs-lookup"><span data-stu-id="1a965-125">Reference</span></span>  
 <xref:System.ServiceModel.EndpointAddress>  
  
## <a name="related-sections"></a><span data-ttu-id="1a965-126">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="1a965-126">Related Sections</span></span>  
 [<span data-ttu-id="1a965-127">Ciclo di vita della programmazione di base</span><span class="sxs-lookup"><span data-stu-id="1a965-127">Basic Programming Lifecycle</span></span>](basic-programming-lifecycle.md)
