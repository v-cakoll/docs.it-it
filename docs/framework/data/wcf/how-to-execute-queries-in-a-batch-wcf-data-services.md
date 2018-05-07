---
title: 'Procedura: eseguire query in un batch (WCF Data Services)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, batch requests
ms.assetid: 3b4db7df-bd33-43a1-8ea4-63a18e131f97
ms.openlocfilehash: d710d6539cf465624aa985ce19a67a6d8fb8ee8d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-execute-queries-in-a-batch-wcf-data-services"></a>Procedura: eseguire query in un batch (WCF Data Services)
Tramite il [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] libreria client, è possibile eseguire più di una query sul servizio dati in un unico batch. Per ulteriori informazioni, vedere [operazioni batch](../../../../docs/framework/data/wcf/batching-operations-wcf-data-services.md).  
  
 Nell'esempio riportato in questo argomento vengono usati il servizio dati Northwind di esempio e le classi del servizio dati client generate automaticamente. Questo servizio e le classi di dati client vengono create quando si completa la [Guida rapida di WCF Data Services](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come chiamare il metodo <xref:System.Data.Services.Client.DataServiceContext.ExecuteBatch%2A> per eseguire una matrice di oggetti <xref:System.Data.Services.Client.DataServiceRequest%601> contenente query che restituiscono gli oggetti `Customers` e `Products` dal servizio dati Northwind. La raccolta di oggetti <xref:System.Data.Services.Client.QueryOperationResponse%601> inclusa nell'oggetto <xref:System.Data.Services.Client.DataServiceResponse> restituito viene enumerata, allo stesso modo della raccolta di oggetti inclusa in ogni oggetto <xref:System.Data.Services.Client.QueryOperationResponse%601>.  
  
 [!code-csharp[Astoria Northwind Client#BatchQuery](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#batchquery)]
 [!code-vb[Astoria Northwind Client#BatchQuery](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#batchquery)]  
  
## <a name="see-also"></a>Vedere anche  
 [Libreria client WCF Data Services](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)
