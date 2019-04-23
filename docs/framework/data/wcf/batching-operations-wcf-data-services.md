---
title: Esecuzione di operazioni in batch (WCF Data Services)
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, client library
ms.assetid: 962a49d1-cc11-4b96-bc7d-071dd6607d6c
ms.openlocfilehash: a9f74f025af6dfc5737ea9f4971f68c5ad913e8b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59133601"
---
# <a name="batching-operations-wcf-data-services"></a>Esecuzione di operazioni in batch (WCF Data Services)
Il [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] supporta l'elaborazione delle richieste per batch un' [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]-servizio basato su. Per altre informazioni, vedere [OData: Elaborazione batch](https://go.microsoft.com/fwlink/?LinkId=186075). Nelle [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)], ogni operazione che utilizza il <xref:System.Data.Services.Client.DataServiceContext>, ad esempio l'esecuzione di una query o salvataggio di modifiche, i risultati di una richiesta separata inviati al servizio dati. Per mantenere un ambito logico per i set di operazioni, è possibile definire in modo esplicito batch operativi. Ciò garantisce che tutte le operazioni nel batch vengono inviati al servizio dati in una singola richiesta HTTP, consente al server elaborare le operazioni in modo atomico e riduce il numero di round trip al servizio dati.  
  
## <a name="batching-query-operations"></a>Invio in batch di operazioni di query  
 Per eseguire più query in un unico batch, è necessario creare ogni query del batch come istanza separata della classe <xref:System.Data.Services.Client.DataServiceRequest%601>. Quando si crea una richiesta di query in questo modo, la query stessa viene definita come URI a cui vengono applicate le regole per l'indirizzamento di risorse. Per altre informazioni, vedere [accesso alle risorse del servizio dati](../../../../docs/framework/data/wcf/accessing-data-service-resources-wcf-data-services.md). Le richieste di query in batch vengono inviate al servizio dati quando viene chiamato il metodo <xref:System.Data.Services.Client.DataServiceContext.ExecuteBatch%2A> contenente gli oggetti della richiesta di query. Questo metodo restituisce un oggetto <xref:System.Data.Services.Client.DataServiceResponse> corrispondente a una raccolta di oggetti <xref:System.Data.Services.Client.QueryOperationResponse%601> che rappresentano risposte a singole query incluse nel batch, ognuna delle quali contiene una raccolta di oggetti restituiti dalla query o informazioni sull'errore. Quando una singola operazione di query inclusa nel batch ha esito negativo, le informazioni sull'errore vengono restituite nell'oggetto <xref:System.Data.Services.Client.QueryOperationResponse%601> per l'operazione non riuscita e le operazioni rimanenti vengono comunque eseguite. Per altre informazioni, vedere [Procedura: Eseguire query in un Batch](../../../../docs/framework/data/wcf/how-to-execute-queries-in-a-batch-wcf-data-services.md).  
  
 Le query in batch possono inoltre essere eseguite in modo asincrono. Per altre informazioni, vedere [operazioni asincrone](../../../../docs/framework/data/wcf/asynchronous-operations-wcf-data-services.md).  
  
## <a name="batching-the-savechanges-operation"></a>Invio in batch dell'operazione SaveChanges  
 Quando si chiama il <xref:System.Data.Services.Client.DataServiceContext.SaveChanges%2A> metodo, tutte le modifiche al contesto vengono tradotte in operazioni basate su REST che vengono inviate come richieste per il [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] servizio. Per impostazione predefinita, queste modifiche non vengono inviate in un unico messaggio di richiesta. Per richiedere che tutte le modifiche vengano inviate in una singola richiesta, è necessario chiamare il <xref:System.Data.Services.Client.DataServiceContext.SaveChanges%28System.Data.Services.Client.SaveChangesOptions%29> metodo e includere il valore <xref:System.Data.Services.Client.SaveChangesOptions.Batch> nel <xref:System.Data.Services.Client.SaveChangesOptions> enumerazione fornita al metodo.  
  
 È inoltre possibile salvare modifiche in batch in modo asincrono. Per altre informazioni, vedere [operazioni asincrone](../../../../docs/framework/data/wcf/asynchronous-operations-wcf-data-services.md).  
  
## <a name="see-also"></a>Vedere anche

- [Libreria client WCF Data Services](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)
