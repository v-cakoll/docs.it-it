---
title: Provider di servizi dati personalizzati (WCF Data Services)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF Data Services, providers
ms.assetid: e702ecdb-3419-4743-92a9-c3c0e7d44082
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d7db780b97c1a7eadffbfa71f60be4afe590ccb4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="custom-data-service-providers-wcf-data-services"></a>Provider di servizi dati personalizzati (WCF Data Services)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] include un set di provider che consente di definire un modello di dati basato su tipi di dati ad associazione tardiva.  
  
|Provider|Descrizione|  
|--------------|-----------------|  
|Provider di metadati|Si tratta del provider del servizio dati personalizzato principale che consente di definire un modello di dati personalizzato in fase di esecuzione mediante l'implementazione dell'interfaccia <xref:System.Data.Services.Providers.IDataServiceMetadataProvider>.|  
|Provider di query|Questo provider consente di eseguire query su un modello di dati personalizzato definito tramite l'interfaccia <xref:System.Data.Services.Providers.IDataServiceMetadataProvider>. Il provider di query viene creato mediante l'implementazione dell'interfaccia <xref:System.Data.Services.Providers.IDataServiceQueryProvider>.|  
|Provider di aggiornamento|Questo provider consente di applicare aggiornamenti ai tipi esposti in un provider del servizio dati personalizzato e di gestire la concorrenza. Un provider di aggiornamento viene creato mediante l'implementazione dell'interfaccia <xref:System.Data.Services.Providers.IDataServiceUpdateProvider>|  
|Provider di paging|Questo provider viene usato con il provider del servizio dati personalizzato per abilitare il supporto di paging basato su server. Un provider di paging per un servizio dati personalizzato viene creato mediante l'implementazione dell'interfaccia <xref:System.Data.Services.Providers.IDataServicePagingProvider>.|  
|Provider di flusso|Questo provider consente di esporre come flusso tipi di dati per oggetti binari di grandi dimensioni. Un provider di flusso viene creato mediante l'implementazione dell'interfaccia <xref:System.Data.Services.Providers.IDataServiceStreamProvider>. Il provider di flusso può essere usato anche con i provider di origini dati di Entity Framework e di reflection. Per ulteriori informazioni, vedere [Provider di flusso](../../../../docs/framework/data/wcf/streaming-provider-wcf-data-services.md).|  
  
 Per ulteriori informazioni, vedere l'articolo [provider di servizi dati personalizzati](http://go.microsoft.com/fwlink/?LinkID=186850) e [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] Toolkit del Provider nel [OData SDK](http://go.microsoft.com/fwlink/?LinkId=186069).  
  
## <a name="see-also"></a>Vedere anche  
 [Provider di servizi dati](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md)  
 [Provider di Entity Framework](../../../../docs/framework/data/wcf/entity-framework-provider-wcf-data-services.md)  
 [Provider di reflection](../../../../docs/framework/data/wcf/reflection-provider-wcf-data-services.md)
