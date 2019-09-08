---
title: 'Procedura: Determinare il numero di entità restituite da una query (WCF Data Services)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, row count
ms.assetid: 03d41a82-df95-40ac-8439-a6c327d37ba8
ms.openlocfilehash: 942fc6d6cbfb35d836ca5881958e7c9965a7d08b
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70779833"
---
# <a name="how-to-determine-the-number-of-entities-returned-by-a-query-wcf-data-services"></a>Procedura: Determinare il numero di entità restituite da una query (WCF Data Services)
Con [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] è possibile determinare il numero di entità specificate nel set di entità dall'URI di una query. Il conteggio può essere incluso insieme al risultato della query o come valore integer. Per ulteriori informazioni, vedere [esecuzione di query sul servizio dati](querying-the-data-service-wcf-data-services.md).  
  
 Nell'esempio riportato in questo argomento vengono usati il servizio dati Northwind di esempio e le classi del servizio dati client generate automaticamente. Questo servizio e le classi di dati client vengono creati al completamento della [WCF Data Services avvio rapido](quickstart-wcf-data-services.md).  
  
## <a name="example"></a>Esempio  
 In questo esempio viene eseguita una query dopo avere chiamato il metodo <xref:System.Data.Services.Client.DataServiceQuery%601.IncludeTotalCount%2A>. La proprietà <xref:System.Data.Services.Client.QueryOperationResponse%601.TotalCount%2A> restituisce il numero di entità nel set di entità `Customers`.  
  
 [!code-csharp[Astoria Northwind Client#CountAllCustomers](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#countallcustomers)]
 [!code-vb[Astoria Northwind Client#CountAllCustomers](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#countallcustomers)]  
  
## <a name="example"></a>Esempio  
 In questo esempio viene chiamato il metodo <xref:System.Linq.Enumerable.Count%2A> per restituire solo un valore integer che corrisponde al numero di entità nel set di entità `Customers`.  
  
 [!code-csharp[Astoria Northwind Client#CountAllCustomersValueOnly](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#countallcustomersvalueonly)]
 [!code-vb[Astoria Northwind Client#CountAllCustomersValueOnly](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#countallcustomersvalueonly)]  
  
## <a name="see-also"></a>Vedere anche

- [Esecuzione di query sul servizio dati](querying-the-data-service-wcf-data-services.md)
