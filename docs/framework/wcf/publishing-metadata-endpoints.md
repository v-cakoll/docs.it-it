---
title: Pubblicazione di endpoint dei metadati
ms.date: 03/30/2017
ms.assetid: 29cd8a60-dfb7-460c-bf5a-c2b31b782671
ms.openlocfilehash: 5de1122a4b603e4c0cd3ae55f3ac7424a7fd77f8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54626591"
---
# <a name="publishing-metadata-endpoints"></a><span data-ttu-id="8a795-102">Pubblicazione di endpoint dei metadati</span><span class="sxs-lookup"><span data-stu-id="8a795-102">Publishing Metadata Endpoints</span></span>
<span data-ttu-id="8a795-103">Servizi Windows Communication Foundation (WCF) pubblicano metadati tramite la pubblicazione di uno o più endpoint di metadati.</span><span class="sxs-lookup"><span data-stu-id="8a795-103">Windows Communication Foundation (WCF) services publish metadata by publishing one or more metadata endpoints.</span></span> <span data-ttu-id="8a795-104">La pubblicazione di metadati del servizio rende disponibili i metadati utilizzando protocolli standard, ad esempio le richieste WS-MetadataExchange (MEX) e HTTP/GET.</span><span class="sxs-lookup"><span data-stu-id="8a795-104">Publishing service metadata makes the metadata available using standardized protocols, such as WS-MetadataExchange (MEX) and HTTP/GET requests.</span></span> <span data-ttu-id="8a795-105">Gli endpoint dei metadati sono simili ad altri endpoint del servizio per indirizzo, associazione e contratto e possono essere aggiunti a un host del servizio tramite configurazione o codice.</span><span class="sxs-lookup"><span data-stu-id="8a795-105">Metadata endpoints are similar to other service endpoints in that they have an address, a binding, and a contract, and they can be added to a service host through configuration or in code.</span></span> <span data-ttu-id="8a795-106">Per consentire la pubblicazione di endpoint dei metadati, è necessario aggiungere al servizio il comportamento del servizio <xref:System.ServiceModel.Description.ServiceMetadataBehavior>.</span><span class="sxs-lookup"><span data-stu-id="8a795-106">To enable publishing metadata endpoints, you must add the <xref:System.ServiceModel.Description.ServiceMetadataBehavior> service behavior to the service.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8a795-107">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="8a795-107">In This Section</span></span>  
 [<span data-ttu-id="8a795-108">Procedura: Pubblicare i metadati per un servizio utilizzando un File di configurazione</span><span class="sxs-lookup"><span data-stu-id="8a795-108">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)  
 <span data-ttu-id="8a795-109">Viene illustrato come configurare un servizio WCF per pubblicare metadati in modo che i client possono recuperare i metadati utilizzando un WS-MetadataExchange o una richiesta HTTP/GET tramite la `?wsdl` stringa di query.</span><span class="sxs-lookup"><span data-stu-id="8a795-109">Demonstrates how to configure a WCF service to publish metadata so that clients can retrieve the metadata using a WS-MetadataExchange or an HTTP/GET request using the `?wsdl` query string.</span></span>  
  
 [<span data-ttu-id="8a795-110">Procedura: Pubblicare metadati per un servizio tramite codice</span><span class="sxs-lookup"><span data-stu-id="8a795-110">How to: Publish Metadata for a Service Using Code</span></span>](../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-code.md)  
 <span data-ttu-id="8a795-111">Viene illustrato come abilitare la pubblicazione dei metadati per un servizio WCF nel codice in modo che i client possono recuperare i metadati utilizzando un WS-MetadataExchange o una richiesta HTTP/GET tramite la `?wsdl` stringa di query.</span><span class="sxs-lookup"><span data-stu-id="8a795-111">Demonstrates how to enable metadata publishing for a WCF service in code so that clients can retrieve the metadata using a WS-MetadataExchange or an HTTP/GET request using the `?wsdl` query string.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a795-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8a795-112">See also</span></span>
- [<span data-ttu-id="8a795-113">Pubblicazione di metadati</span><span class="sxs-lookup"><span data-stu-id="8a795-113">Publishing Metadata</span></span>](../../../docs/framework/wcf/feature-details/publishing-metadata.md)
