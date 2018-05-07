---
title: Pubblicazione di endpoint dei metadati
ms.date: 03/30/2017
ms.assetid: 29cd8a60-dfb7-460c-bf5a-c2b31b782671
ms.openlocfilehash: 6060850b78c890e043dfaf6f242460bc6e0ef627
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="publishing-metadata-endpoints"></a>Pubblicazione di endpoint dei metadati
I servizi Windows Communication Foundation (WCF) pubblicano metadati tramite la pubblicazione di uno o più endpoint dei metadati. La pubblicazione di metadati del servizio rende disponibili i metadati utilizzando protocolli standard, ad esempio le richieste WS-MetadataExchange (MEX) e HTTP/GET. Gli endpoint dei metadati sono simili ad altri endpoint del servizio per indirizzo, associazione e contratto e possono essere aggiunti a un host del servizio tramite configurazione o codice. Per consentire la pubblicazione di endpoint dei metadati, è necessario aggiungere al servizio il comportamento del servizio <xref:System.ServiceModel.Description.ServiceMetadataBehavior>.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Procedura: Pubblicare metadati per un servizio usando un file di configurazione](../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)  
 Illustra come configurare un servizio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] per pubblicare metadati in modo che i client possano recuperare i metadati utilizzando una richiesta WS-MetadataExchange o HTTP/GET tramite la stringa di query `?wsdl`.  
  
 [Procedura: Pubblicare metadati per un servizio usando il codice](../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-code.md)  
 Illustra come consentire la pubblicazione di metadati per un servizio nel codice [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] in modo che i client possano recuperare i metadati utilizzando una richiesta WS-MetadataExchange o HTTP/GET tramite la stringa di query `?wsdl`.  
  
## <a name="see-also"></a>Vedere anche  
 [Pubblicazione di metadati](../../../docs/framework/wcf/feature-details/publishing-metadata.md)
