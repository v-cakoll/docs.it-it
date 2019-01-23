---
title: 'Procedura: Abilitare il Paging dei risultati del servizio dati (WCF Data Services)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- paging output [WCF Data Services]
ms.assetid: 9a316cbd-9612-4482-a541-a10bc78b2635
ms.openlocfilehash: be5bd41494c27724a360b785b8706b618447e7de
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54523455"
---
# <a name="how-to-enable-paging-of-data-service-results-wcf-data-services"></a>Procedura: Abilitare il Paging dei risultati del servizio dati (WCF Data Services)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] consente di limitare il numero di entità restituite da una query del servizio dati. I limiti di paging vengono definiti nel metodo chiamato all'avvio del servizio e possono essere impostati separatamente per ogni set di entità.  
  
 Quando il paging è abilitato, la voce finale nel feed contiene un collegamento alla pagina di dati successiva. Per altre informazioni, vedere [configurazione del servizio dati](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md).  
  
 In questo argomento viene illustrato come modificare un servizio dati per abilitare il paging dei set di entità `Customers` e `Orders` restituiti. Nell'esempio riportato in questo argomento viene usato il servizio dati Northwind di esempio. Questo servizio viene creato quando si completa la [Guida rapida di WCF Data Services](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).  
  
### <a name="how-to-enable-paging-of-returned-customers-and-orders-entity-sets"></a>Modalità di abilitazione del paging dei set di entità Customers e Orders restituiti  
  
-   Nel codice per il servizio dati sostituire il codice segnaposto nella funzione `InitializeService` con il codice seguente:  
  
     [!code-csharp[Astoria Northwind Service#DataServiceConfigPaging](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind service/cs/northwind.svc.cs#dataserviceconfigpaging)]
     [!code-vb[Astoria Northwind Service#DataServiceConfigPaging](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind service/vb/northwind.svc.vb#dataserviceconfigpaging)]  
  
## <a name="see-also"></a>Vedere anche
- [Caricamento di contenuto posticipato](../../../../docs/framework/data/wcf/loading-deferred-content-wcf-data-services.md)
- [Procedura: Caricare risultati di paging](../../../../docs/framework/data/wcf/how-to-load-paged-results-wcf-data-services.md)
