---
title: Provider di servizi dati personalizzati (WCF Data Services)
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, providers
ms.assetid: e702ecdb-3419-4743-92a9-c3c0e7d44082
ms.openlocfilehash: a5041b04151a288f9c6c1a567dacec8da8c80a42
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75346139"
---
# <a name="custom-data-service-providers-wcf-data-services"></a>Provider di servizi dati personalizzati (WCF Data Services)
WCF Data Services include un set di provider che consente di definire un modello di dati basato su tipi di dati ad associazione tardiva.  
  
|Provider|Descrizione|  
|--------------|-----------------|  
|Provider di metadati|Si tratta del provider del servizio dati personalizzato principale che consente di definire un modello di dati personalizzato in fase di esecuzione mediante l'implementazione dell'interfaccia <xref:System.Data.Services.Providers.IDataServiceMetadataProvider>.|  
|Provider di query|Questo provider consente di eseguire query su un modello di dati personalizzato definito tramite l'interfaccia <xref:System.Data.Services.Providers.IDataServiceMetadataProvider>. Il provider di query viene creato mediante l'implementazione dell'interfaccia <xref:System.Data.Services.Providers.IDataServiceQueryProvider>.|  
|Provider di aggiornamento|Questo provider consente di applicare aggiornamenti ai tipi esposti in un provider del servizio dati personalizzato e di gestire la concorrenza. Un provider di aggiornamento viene creato mediante l'implementazione dell'interfaccia <xref:System.Data.Services.Providers.IDataServiceUpdateProvider>|  
|Provider di paging|Questo provider viene usato con il provider del servizio dati personalizzato per abilitare il supporto di paging basato su server. Un provider di paging per un servizio dati personalizzato viene creato mediante l'implementazione dell'interfaccia <xref:System.Data.Services.Providers.IDataServicePagingProvider>.|  
|Provider di flusso|Questo provider consente di esporre come flusso tipi di dati per oggetti binari di grandi dimensioni. Un provider di flusso viene creato mediante l'implementazione dell'interfaccia <xref:System.Data.Services.Providers.IDataServiceStreamProvider>. Il provider di flusso può essere usato anche con i provider di origini dati di Entity Framework e di reflection. Per ulteriori informazioni, vedere [provider di flussi](streaming-provider-wcf-data-services.md).|  
  
## <a name="see-also"></a>Vedere anche

- [Provider di servizi dati](data-services-providers-wcf-data-services.md)
- [Provider di Entity Framework](entity-framework-provider-wcf-data-services.md)
- [Provider di reflection](reflection-provider-wcf-data-services.md)
