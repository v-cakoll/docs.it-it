---
title: 'Procedura: Caricare entità correlate (WCF Data Services)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, deferred content
- WCF Data Services, loading data
ms.assetid: 6f143d30-d997-4e6b-bcf0-d5c394ecb108
ms.openlocfilehash: 7687378ae2a6c7d8021acc53b19544206ee0cc84
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59092630"
---
# <a name="how-to-load-related-entities-wcf-data-services"></a>Procedura: Caricare entità correlate (WCF Data Services)
Per caricare entità associate in [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)], è possibile usare il metodo <xref:System.Data.Services.Client.DataServiceContext.LoadProperty%2A> sulla classe <xref:System.Data.Services.Client.DataServiceContext>. È anche possibile usare la <xref:System.Data.Services.Client.DataServiceQuery%601.Expand%2A> metodo su di <xref:System.Data.Services.Client.DataServiceQuery%601> in modo da richiedere che le entità correlate vengano caricate rapidamente nella stessa risposta alla query.  
  
 Nell'esempio riportato in questo argomento vengono usati il servizio dati Northwind di esempio e le classi del servizio dati client generate automaticamente. Questo servizio e le classi dati client vengono create quando si completa la [Guida rapida di WCF Data Services](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come caricare in modo esplicito l'entità `Customer` correlata a ogni istanza di `Orders` restituita.  
  
 [!code-csharp[Astoria Northwind Client#LoadRelatedOrderCustomer](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#loadrelatedordercustomer)]
 [!code-vb[Astoria Northwind Client#LoadRelatedOrderCustomer](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#loadrelatedordercustomer)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come usare il metodo <xref:System.Data.Services.Client.DataServiceQuery%601.Expand%2A> per restituire le entità `Order Details` che appartengono all'entità `Orders` restituita dalla query.  
  
 [!code-csharp[Astoria Northwind Client#ExpandOrderDetails](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#expandorderdetails)]
 [!code-vb[Astoria Northwind Client#ExpandOrderDetails](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#expandorderdetails)]  
  
## <a name="see-also"></a>Vedere anche

- [Esecuzione di query sul servizio dati](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md)
