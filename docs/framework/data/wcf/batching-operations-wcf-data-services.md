---
title: Esecuzione di operazioni in batch (WCF Data Services)
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, client library
ms.assetid: 962a49d1-cc11-4b96-bc7d-071dd6607d6c
ms.openlocfilehash: f6e6356b8acc6b5abb217ecc4edd2c3cd185f71a
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75346156"
---
# <a name="batching-operations-wcf-data-services"></a>Esecuzione di operazioni in batch (WCF Data Services)
Il Open Data Protocol (OData) supporta l'elaborazione batch di richieste a un servizio basato su OData. Per ulteriori informazioni, vedere [OData: elaborazione batch](https://www.odata.org/documentation/odata-version-2-0/batch-processing/). In WCF Data Services, ogni operazione che usa il <xref:System.Data.Services.Client.DataServiceContext>, ad esempio l'esecuzione di una query o il salvataggio di modifiche, comporta l'invio di una richiesta separata al servizio dati. Per mantenere un ambito logico per i set di operazioni, è possibile definire in modo esplicito batch operativi. Ciò garantisce che tutte le operazioni nel batch vengano inviate al servizio dati in un'unica richiesta HTTP, consente al server di elaborare le operazioni in modo atomico e riduce il numero di round trip al servizio dati.  
  
## <a name="batching-query-operations"></a>Invio in batch di operazioni di query  
 Per eseguire più query in un unico batch, è necessario creare ogni query del batch come istanza separata della classe <xref:System.Data.Services.Client.DataServiceRequest%601>. Quando si crea una richiesta di query in questo modo, la query stessa viene definita come URI a cui vengono applicate le regole per l'indirizzamento di risorse. Per ulteriori informazioni, vedere [accesso alle risorse del servizio dati](accessing-data-service-resources-wcf-data-services.md). Le richieste di query in batch vengono inviate al servizio dati quando viene chiamato il metodo <xref:System.Data.Services.Client.DataServiceContext.ExecuteBatch%2A> contenente gli oggetti della richiesta di query. Questo metodo restituisce un oggetto <xref:System.Data.Services.Client.DataServiceResponse> corrispondente a una raccolta di oggetti <xref:System.Data.Services.Client.QueryOperationResponse%601> che rappresentano risposte a singole query incluse nel batch, ognuna delle quali contiene una raccolta di oggetti restituiti dalla query o informazioni sull'errore. Quando una singola operazione di query inclusa nel batch ha esito negativo, le informazioni sull'errore vengono restituite nell'oggetto <xref:System.Data.Services.Client.QueryOperationResponse%601> per l'operazione non riuscita e le operazioni rimanenti vengono comunque eseguite. Per altre informazioni, vedere [procedura: eseguire query in un batch](how-to-execute-queries-in-a-batch-wcf-data-services.md).  
  
 Le query in batch possono inoltre essere eseguite in modo asincrono. Per altre informazioni, vedere [operazioni asincrone](asynchronous-operations-wcf-data-services.md).  
  
## <a name="batching-the-savechanges-operation"></a>Invio in batch dell'operazione SaveChanges  
 Quando si chiama il metodo <xref:System.Data.Services.Client.DataServiceContext.SaveChanges%2A>, tutte le modifiche rilevate dal contesto vengono convertite in operazioni basate su REST inviate come richieste al servizio OData. Per impostazione predefinita, queste modifiche non vengono inviate in un unico messaggio di richiesta. Per richiedere che tutte le modifiche vengano inviate in un'unica richiesta, è necessario chiamare il metodo <xref:System.Data.Services.Client.DataServiceContext.SaveChanges%28System.Data.Services.Client.SaveChangesOptions%29> e includere il valore <xref:System.Data.Services.Client.SaveChangesOptions.Batch> nell'enumerazione <xref:System.Data.Services.Client.SaveChangesOptions> fornita al metodo.  
  
 È inoltre possibile salvare modifiche in batch in modo asincrono. Per altre informazioni, vedere [operazioni asincrone](asynchronous-operations-wcf-data-services.md).  
  
## <a name="see-also"></a>Vedere anche

- [Libreria client WCF Data Services](wcf-data-services-client-library.md)
