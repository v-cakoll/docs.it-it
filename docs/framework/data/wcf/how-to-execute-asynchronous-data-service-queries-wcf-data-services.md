---
title: 'Procedura: Eseguire query sul servizio dati asincrone (WCF Data Services)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, asynchronous operations
- asynchronous operations [WCF Data Services]
ms.assetid: 902a2dc1-d0e9-4b00-90a8-becc4cb1f6a7
ms.openlocfilehash: 4aef253ebb54fb92a0c3b2b661404ac373979e56
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59163553"
---
# <a name="how-to-execute-asynchronous-data-service-queries-wcf-data-services"></a>Procedura: Eseguire query sul servizio dati asincrone (WCF Data Services)
Tramite la libreria client di [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] è possibile eseguire in modo asincrono operazioni client-server, ad esempio query e salvataggio di modifiche. Per altre informazioni, vedere [operazioni asincrone](../../../../docs/framework/data/wcf/asynchronous-operations-wcf-data-services.md).  
  
> [!NOTE]
>  In un'applicazione in cui il callback deve essere richiamato su un thread specifico, è necessario effettuare il marshalling in modo esplicito del metodo <xref:System.Data.Services.Client.DataServiceQuery%601.EndExecute%2A>. Per altre informazioni, vedere [operazioni asincrone](../../../../docs/framework/data/wcf/asynchronous-operations-wcf-data-services.md).  
  
 Nell'esempio riportato in questo argomento vengono usati il servizio dati Northwind di esempio e le classi del servizio dati client generate automaticamente. Questo servizio e le classi dati client vengono create quando si completa la [Guida rapida di WCF Data Services](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come eseguire una query asincrona chiamando il metodo <xref:System.Data.Services.Client.DataServiceQuery%601.BeginExecute%2A> per l'avvio della query. Il delegato inline chiama il metodo <xref:System.Data.Services.Client.DataServiceQuery%601.EndExecute%2A> per visualizzare i risultati della query.  
  
 [!code-csharp[Astoria Northwind Client#ExecuteQueryAsync](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#executequeryasync)]
 [!code-vb[Astoria Northwind Client#ExecuteQueryAsync](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#executequeryasync)]  
  
## <a name="see-also"></a>Vedere anche

- [Libreria client WCF Data Services](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)
