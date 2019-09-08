---
title: Esecuzione di operazioni in batch (WCF Data Services)
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, client library
ms.assetid: 962a49d1-cc11-4b96-bc7d-071dd6607d6c
ms.openlocfilehash: 2a642bdfd6a8891c54c01a07609760bede2f5d5d
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70780509"
---
# <a name="batching-operations-wcf-data-services"></a>Esecuzione di operazioni in batch (WCF Data Services)
Supporta [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] l'elaborazione batch di richieste a un [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]servizio basato su. Per ulteriori informazioni, vedere [OData: Elaborazione](https://go.microsoft.com/fwlink/?LinkId=186075)batch. In [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]ogni operazione che utilizza, ad <xref:System.Data.Services.Client.DataServiceContext>esempio l'esecuzione di una query o il salvataggio di modifiche, determina l'invio di una richiesta separata al servizio dati. Per mantenere un ambito logico per i set di operazioni, è possibile definire in modo esplicito batch operativi. Ciò garantisce che tutte le operazioni nel batch vengano inviate al servizio dati in un'unica richiesta HTTP, consente al server di elaborare le operazioni in modo atomico e riduce il numero di round trip al servizio dati.  
  
## <a name="batching-query-operations"></a>Invio in batch di operazioni di query  
 Per eseguire più query in un unico batch, è necessario creare ogni query del batch come istanza separata della classe <xref:System.Data.Services.Client.DataServiceRequest%601>. Quando si crea una richiesta di query in questo modo, la query stessa viene definita come URI a cui vengono applicate le regole per l'indirizzamento di risorse. Per ulteriori informazioni, vedere [accesso alle risorse del servizio dati](accessing-data-service-resources-wcf-data-services.md). Le richieste di query in batch vengono inviate al servizio dati quando viene chiamato il metodo <xref:System.Data.Services.Client.DataServiceContext.ExecuteBatch%2A> contenente gli oggetti della richiesta di query. Questo metodo restituisce un oggetto <xref:System.Data.Services.Client.DataServiceResponse> corrispondente a una raccolta di oggetti <xref:System.Data.Services.Client.QueryOperationResponse%601> che rappresentano risposte a singole query incluse nel batch, ognuna delle quali contiene una raccolta di oggetti restituiti dalla query o informazioni sull'errore. Quando una singola operazione di query inclusa nel batch ha esito negativo, le informazioni sull'errore vengono restituite nell'oggetto <xref:System.Data.Services.Client.QueryOperationResponse%601> per l'operazione non riuscita e le operazioni rimanenti vengono comunque eseguite. Per altre informazioni, vedere [Procedura: Esecuzione di query in un](how-to-execute-queries-in-a-batch-wcf-data-services.md)batch.  
  
 Le query in batch possono inoltre essere eseguite in modo asincrono. Per altre informazioni, vedere [operazioni asincrone](asynchronous-operations-wcf-data-services.md).  
  
## <a name="batching-the-savechanges-operation"></a>Invio in batch dell'operazione SaveChanges  
 Quando si chiama il <xref:System.Data.Services.Client.DataServiceContext.SaveChanges%2A> metodo, tutte le modifiche rilevate dal contesto vengono convertite in operazioni basate su REST inviate come richieste [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] al servizio. Per impostazione predefinita, queste modifiche non vengono inviate in un unico messaggio di richiesta. Per richiedere che tutte le modifiche vengano inviate in un'unica richiesta, è necessario chiamare <xref:System.Data.Services.Client.DataServiceContext.SaveChanges%28System.Data.Services.Client.SaveChangesOptions%29> il metodo e includere il <xref:System.Data.Services.Client.SaveChangesOptions.Batch> valore nell' <xref:System.Data.Services.Client.SaveChangesOptions> enumerazione fornita al metodo.  
  
 È inoltre possibile salvare modifiche in batch in modo asincrono. Per altre informazioni, vedere [operazioni asincrone](asynchronous-operations-wcf-data-services.md).  
  
## <a name="see-also"></a>Vedere anche

- [Libreria client WCF Data Services](wcf-data-services-client-library.md)
