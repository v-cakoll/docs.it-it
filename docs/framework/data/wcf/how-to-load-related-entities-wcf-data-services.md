---
title: "Procedura: caricare entità correlate (WCF Data Services)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, deferred content
- WCF Data Services, loading data
ms.assetid: 6f143d30-d997-4e6b-bcf0-d5c394ecb108
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5d25b2052c889fb6ea4614a43f67f07f3f0a073d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-load-related-entities-wcf-data-services"></a>Procedura: caricare entità correlate (WCF Data Services)
Per caricare entità associate in [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)], è possibile usare il metodo <xref:System.Data.Services.Client.DataServiceContext.LoadProperty%2A> sulla classe <xref:System.Data.Services.Client.DataServiceContext>. È inoltre possibile utilizzare il <xref:System.Data.Services.Client.DataServiceQuery%601.Expand%2A> metodo il <xref:System.Data.Services.Client.DataServiceQuery%601> per richiedere che le entità correlate vengano caricate rapidamente nella stessa risposta alla query.  
  
 Nell'esempio riportato in questo argomento vengono usati il servizio dati Northwind di esempio e le classi del servizio dati client generate automaticamente. Questo servizio e le classi di dati client vengono create quando si completa la [Guida rapida di WCF Data Services](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come caricare in modo esplicito l'entità `Customer` correlata a ogni istanza di `Orders` restituita.  
  
 [!code-csharp[Astoria Northwind Client#LoadRelatedOrderCustomer](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#loadrelatedordercustomer)]
 [!code-vb[Astoria Northwind Client#LoadRelatedOrderCustomer](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#loadrelatedordercustomer)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come usare il metodo <xref:System.Data.Services.Client.DataServiceQuery%601.Expand%2A> per restituire le entità `Order Details` che appartengono all'entità `Orders` restituita dalla query.  
  
 [!code-csharp[Astoria Northwind Client#ExpandOrderDetails](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#expandorderdetails)]
 [!code-vb[Astoria Northwind Client#ExpandOrderDetails](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#expandorderdetails)]  
  
## <a name="see-also"></a>Vedere anche  
 [Esecuzione di query sul servizio dati](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md)
