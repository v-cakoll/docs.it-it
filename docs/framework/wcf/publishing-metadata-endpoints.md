---
title: Pubblicazione di endpoint dei metadati
ms.date: 03/30/2017
ms.assetid: 29cd8a60-dfb7-460c-bf5a-c2b31b782671
ms.openlocfilehash: 4c6ac81f0c97415dc21ff3346178dd1e9936b7a5
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319901"
---
# <a name="publishing-metadata-endpoints"></a><span data-ttu-id="0dc71-102">Pubblicazione di endpoint dei metadati</span><span class="sxs-lookup"><span data-stu-id="0dc71-102">Publishing Metadata Endpoints</span></span>
<span data-ttu-id="0dc71-103">I servizi Windows Communication Foundation (WCF) pubblicano i metadati tramite la pubblicazione di uno o più endpoint di metadati.</span><span class="sxs-lookup"><span data-stu-id="0dc71-103">Windows Communication Foundation (WCF) services publish metadata by publishing one or more metadata endpoints.</span></span> <span data-ttu-id="0dc71-104">La pubblicazione di metadati del servizio rende disponibili i metadati utilizzando protocolli standard, ad esempio le richieste WS-MetadataExchange (MEX) e HTTP/GET.</span><span class="sxs-lookup"><span data-stu-id="0dc71-104">Publishing service metadata makes the metadata available using standardized protocols, such as WS-MetadataExchange (MEX) and HTTP/GET requests.</span></span> <span data-ttu-id="0dc71-105">Gli endpoint dei metadati sono simili ad altri endpoint del servizio per indirizzo, associazione e contratto e possono essere aggiunti a un host del servizio tramite configurazione o codice.</span><span class="sxs-lookup"><span data-stu-id="0dc71-105">Metadata endpoints are similar to other service endpoints in that they have an address, a binding, and a contract, and they can be added to a service host through configuration or in code.</span></span> <span data-ttu-id="0dc71-106">Per consentire la pubblicazione di endpoint dei metadati, è necessario aggiungere al servizio il comportamento del servizio <xref:System.ServiceModel.Description.ServiceMetadataBehavior>.</span><span class="sxs-lookup"><span data-stu-id="0dc71-106">To enable publishing metadata endpoints, you must add the <xref:System.ServiceModel.Description.ServiceMetadataBehavior> service behavior to the service.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0dc71-107">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="0dc71-107">In This Section</span></span>  
 [<span data-ttu-id="0dc71-108">Procedura: Pubblicare metadati per un servizio usando un file di configurazione</span><span class="sxs-lookup"><span data-stu-id="0dc71-108">How to: Publish Metadata for a Service Using a Configuration File</span></span>](./feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)  
 <span data-ttu-id="0dc71-109">Viene illustrato come configurare un servizio WCF per pubblicare metadati in modo che i client possano recuperare i metadati utilizzando una richiesta WS-MetadataExchange o HTTP/GET utilizzando la stringa di query `?wsdl`.</span><span class="sxs-lookup"><span data-stu-id="0dc71-109">Demonstrates how to configure a WCF service to publish metadata so that clients can retrieve the metadata using a WS-MetadataExchange or an HTTP/GET request using the `?wsdl` query string.</span></span>  
  
 [<span data-ttu-id="0dc71-110">Procedura: Pubblicare metadati per un servizio usando il codice</span><span class="sxs-lookup"><span data-stu-id="0dc71-110">How to: Publish Metadata for a Service Using Code</span></span>](./feature-details/how-to-publish-metadata-for-a-service-using-code.md)  
 <span data-ttu-id="0dc71-111">Viene illustrato come abilitare la pubblicazione dei metadati per un servizio WCF nel codice in modo che i client possano recuperare i metadati utilizzando una richiesta WS-MetadataExchange o HTTP/GET utilizzando la stringa di query `?wsdl`.</span><span class="sxs-lookup"><span data-stu-id="0dc71-111">Demonstrates how to enable metadata publishing for a WCF service in code so that clients can retrieve the metadata using a WS-MetadataExchange or an HTTP/GET request using the `?wsdl` query string.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0dc71-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0dc71-112">See also</span></span>

- [<span data-ttu-id="0dc71-113">Pubblicazione di metadati</span><span class="sxs-lookup"><span data-stu-id="0dc71-113">Publishing Metadata</span></span>](./feature-details/publishing-metadata.md)
