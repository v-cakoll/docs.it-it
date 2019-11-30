---
title: 'Procedura: abilitare lo spostamento tra i risultati del servizio dati (WCF Data Services)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- paging output [WCF Data Services]
ms.assetid: 9a316cbd-9612-4482-a541-a10bc78b2635
ms.openlocfilehash: 6b7cea2475a5c11091a04ef3044bbc958e55fc5d
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2019
ms.locfileid: "74569098"
---
# <a name="how-to-enable-paging-of-data-service-results-wcf-data-services"></a>Procedura: abilitare lo spostamento tra i risultati del servizio dati (WCF Data Services)
WCF Data Services consente di limitare il numero di entità restituite da una query del servizio dati. I limiti di paging vengono definiti nel metodo chiamato all'avvio del servizio e possono essere impostati separatamente per ogni set di entità.  
  
 Quando il paging è abilitato, la voce finale nel feed contiene un collegamento alla pagina di dati successiva. Per ulteriori informazioni, vedere [configurazione del servizio dati](configuring-the-data-service-wcf-data-services.md).  
  
 In questo argomento viene illustrato come modificare un servizio dati per abilitare il paging dei set di entità `Customers` e `Orders` restituiti. Nell'esempio riportato in questo argomento viene usato il servizio dati Northwind di esempio. Questo servizio viene creato al completamento della [WCF Data Services Guida introduttiva](quickstart-wcf-data-services.md).  
  
### <a name="how-to-enable-paging-of-returned-customers-and-orders-entity-sets"></a>Modalità di abilitazione del paging dei set di entità Customers e Orders restituiti  
  
- Nel codice per il servizio dati sostituire il codice segnaposto nella funzione `InitializeService` con il codice seguente:  
  
     [!code-csharp[Astoria Northwind Service#DataServiceConfigPaging](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind.svc.cs#dataserviceconfigpaging)]
     [!code-vb[Astoria Northwind Service#DataServiceConfigPaging](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind.svc.vb#dataserviceconfigpaging)]  
  
## <a name="see-also"></a>Vedere anche

- [Caricamento di contenuto posticipato](loading-deferred-content-wcf-data-services.md)
- [Procedura: caricare risultati di paging](how-to-load-paged-results-wcf-data-services.md)
