---
title: 'Procedura: impostare le intestazioni nella richiesta del client (WCF Data Services)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, customizing requests
ms.assetid: 3d55168d-5901-4f48-8117-6c93da3ab5ae
ms.openlocfilehash: af158fa525f1f83c081ab293bfdbfb4177caf5a6
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75348384"
---
# <a name="how-to-set-headers-in-the-client-request-wcf-data-services"></a>Procedura: impostare le intestazioni nella richiesta del client (WCF Data Services)
Quando si utilizza la libreria client di WCF Data Services per accedere a un servizio dati che supporta il Open Data Protocol (OData), la libreria client imposta automaticamente le intestazioni HTTP necessarie nei messaggi di richiesta inviati al servizio dati. Tuttavia, tramite la libreria client non vengono impostate le intestazioni del messaggio richieste in determinati casi, ad esempio quando il servizio dati richiede l'autenticazione basata sulle attestazioni o i cookie. Per altre informazioni, vedere [Securing WCF Data Services](securing-wcf-data-services.md#clientAuthentication). In questi casi, è necessario impostare manualmente le intestazioni nel messaggio di richiesta prima che venga inviato. L'esempio in questo argomento illustra come gestire l'evento <xref:System.Data.Services.Client.DataServiceContext.SendingRequest> per aggiungere una nuova intestazione al messaggio di richiesta prima che venga inviato al servizio dati.  
  
 Nell'esempio riportato in questo argomento vengono usati il servizio dati Northwind di esempio e le classi del servizio dati client generate automaticamente. Questo servizio e le classi di dati client vengono creati al completamento della [WCF Data Services avvio rapido](quickstart-wcf-data-services.md). È inoltre possibile utilizzare il [servizio dati di esempio Northwind](https://services.odata.org/Northwind/Northwind.svc/) pubblicato sul sito Web OData. Questo servizio dati di esempio è di sola lettura e il tentativo di salvare le modifiche restituisce un errore. I servizi dati di esempio nel sito Web OData consentono l'autenticazione anonima.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene registrato un gestore per l'evento <xref:System.Data.Services.Client.DataServiceContext.SendingRequest>, quindi viene eseguita una query sul servizio dati.  
  
> [!NOTE]
> Quando un servizio dati richiede che l'intestazione del messaggio venga impostata manualmente per ogni richiesta, considerare registrare il gestore per l'evento <xref:System.Data.Services.Client.DataServiceContext.SendingRequest> eseguendo l'override del metodo parziale `OnContextCreated` nel contenitore di entità che rappresenta il servizio dati che in questo caso è `NorthwindEntities`.  
  
[!code-csharp[Astoria Northwind Client#RegisterHeadersQuery](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#registerheadersquery)]   
[!code-vb[Astoria Northwind Client#RegisterHeadersQuery](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#registerheadersquery)]
  
## <a name="example"></a>Esempio  
 Nel metodo seguente viene gestito l'evento <xref:System.Data.Services.Client.DataServiceContext.SendingRequest> e viene aggiunta un'intestazione di autenticazione alla richiesta.  
  
 [!code-csharp[Astoria Northwind Client#OnSendingRequest](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#onsendingrequest)]  
 [!code-vb[Astoria Northwind Client#OnSendingRequest](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#onsendingrequest)]  
  
## <a name="see-also"></a>Vedere anche

- [Protezione di WCF Data Services](securing-wcf-data-services.md)
- [Libreria client WCF Data Services](wcf-data-services-client-library.md)
