---
title: Pubblicazione di endpoint dei metadati
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 29cd8a60-dfb7-460c-bf5a-c2b31b782671
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 64032fbc675e30e9f01a5db4d56ecc36574e08de
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="publishing-metadata-endpoints"></a><span data-ttu-id="929a7-102">Pubblicazione di endpoint dei metadati</span><span class="sxs-lookup"><span data-stu-id="929a7-102">Publishing Metadata Endpoints</span></span>
<span data-ttu-id="929a7-103">I servizi [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] pubblicano metadati tramite la pubblicazione di uno o più endpoint dei metadati.</span><span class="sxs-lookup"><span data-stu-id="929a7-103">[!INCLUDE[indigo1](../../../includes/indigo1-md.md)] services publish metadata by publishing one or more metadata endpoints.</span></span> <span data-ttu-id="929a7-104">La pubblicazione di metadati del servizio rende disponibili i metadati utilizzando protocolli standard, ad esempio le richieste WS-MetadataExchange (MEX) e HTTP/GET.</span><span class="sxs-lookup"><span data-stu-id="929a7-104">Publishing service metadata makes the metadata available using standardized protocols, such as WS-MetadataExchange (MEX) and HTTP/GET requests.</span></span> <span data-ttu-id="929a7-105">Gli endpoint dei metadati sono simili ad altri endpoint del servizio per indirizzo, associazione e contratto e possono essere aggiunti a un host del servizio tramite configurazione o codice.</span><span class="sxs-lookup"><span data-stu-id="929a7-105">Metadata endpoints are similar to other service endpoints in that they have an address, a binding, and a contract, and they can be added to a service host through configuration or in code.</span></span> <span data-ttu-id="929a7-106">Per consentire la pubblicazione di endpoint dei metadati, è necessario aggiungere al servizio il comportamento del servizio <xref:System.ServiceModel.Description.ServiceMetadataBehavior>.</span><span class="sxs-lookup"><span data-stu-id="929a7-106">To enable publishing metadata endpoints, you must add the <xref:System.ServiceModel.Description.ServiceMetadataBehavior> service behavior to the service.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="929a7-107">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="929a7-107">In This Section</span></span>  
 [<span data-ttu-id="929a7-108">Procedura: pubblicare metadati per un servizio utilizzando un File di configurazione</span><span class="sxs-lookup"><span data-stu-id="929a7-108">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)  
 <span data-ttu-id="929a7-109">Illustra come configurare un servizio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] per pubblicare metadati in modo che i client possano recuperare i metadati utilizzando una richiesta WS-MetadataExchange o HTTP/GET tramite la stringa di query `?wsdl`.</span><span class="sxs-lookup"><span data-stu-id="929a7-109">Demonstrates how to configure a [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] service to publish metadata so that clients can retrieve the metadata using a WS-MetadataExchange or an HTTP/GET request using the `?wsdl` query string.</span></span>  
  
 [<span data-ttu-id="929a7-110">Procedura: pubblicare metadati per un servizio utilizzando il codice</span><span class="sxs-lookup"><span data-stu-id="929a7-110">How to: Publish Metadata for a Service Using Code</span></span>](../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-code.md)  
 <span data-ttu-id="929a7-111">Illustra come consentire la pubblicazione di metadati per un servizio nel codice [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] in modo che i client possano recuperare i metadati utilizzando una richiesta WS-MetadataExchange o HTTP/GET tramite la stringa di query `?wsdl`.</span><span class="sxs-lookup"><span data-stu-id="929a7-111">Demonstrates how to enable metadata publishing for a [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] service in code so that clients can retrieve the metadata using a WS-MetadataExchange or an HTTP/GET request using the `?wsdl` query string.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="929a7-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="929a7-112">See Also</span></span>  
 [<span data-ttu-id="929a7-113">Pubblicazione dei metadati</span><span class="sxs-lookup"><span data-stu-id="929a7-113">Publishing Metadata</span></span>](../../../docs/framework/wcf/feature-details/publishing-metadata.md)
