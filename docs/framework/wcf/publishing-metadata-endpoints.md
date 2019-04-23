---
title: Pubblicazione di endpoint dei metadati
ms.date: 03/30/2017
ms.assetid: 29cd8a60-dfb7-460c-bf5a-c2b31b782671
ms.openlocfilehash: 143a46ce18a0d9dee89bbbffac9be9a467e951df
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59121732"
---
# <a name="publishing-metadata-endpoints"></a>Pubblicazione di endpoint dei metadati
Servizi Windows Communication Foundation (WCF) pubblicano metadati tramite la pubblicazione di uno o più endpoint di metadati. La pubblicazione di metadati del servizio rende disponibili i metadati utilizzando protocolli standard, ad esempio le richieste WS-MetadataExchange (MEX) e HTTP/GET. Gli endpoint dei metadati sono simili ad altri endpoint del servizio per indirizzo, associazione e contratto e possono essere aggiunti a un host del servizio tramite configurazione o codice. Per consentire la pubblicazione di endpoint dei metadati, è necessario aggiungere al servizio il comportamento del servizio <xref:System.ServiceModel.Description.ServiceMetadataBehavior>.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Procedura: Pubblicare i metadati per un servizio utilizzando un File di configurazione](../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)  
 Viene illustrato come configurare un servizio WCF per pubblicare metadati in modo che i client possono recuperare i metadati utilizzando un WS-MetadataExchange o una richiesta HTTP/GET tramite la `?wsdl` stringa di query.  
  
 [Procedura: Pubblicare metadati per un servizio tramite codice](../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-code.md)  
 Viene illustrato come abilitare la pubblicazione dei metadati per un servizio WCF nel codice in modo che i client possono recuperare i metadati utilizzando un WS-MetadataExchange o una richiesta HTTP/GET tramite la `?wsdl` stringa di query.  
  
## <a name="see-also"></a>Vedere anche

- [Pubblicazione di metadati](../../../docs/framework/wcf/feature-details/publishing-metadata.md)
