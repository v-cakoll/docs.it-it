---
title: 'Procedura: eseguire query in un batch (WCF Data Services)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, batch requests
ms.assetid: 3b4db7df-bd33-43a1-8ea4-63a18e131f97
ms.openlocfilehash: 0ddf5b4f68ca08fca0c55cfcdfcd5431bcec6de2
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2019
ms.locfileid: "74569059"
---
# <a name="how-to-execute-queries-in-a-batch-wcf-data-services"></a>Procedura: eseguire query in un batch (WCF Data Services)
Utilizzando la libreria client di WCF Data Services, è possibile eseguire più query sul servizio dati in un singolo batch. Per altre informazioni, vedere [operazioni](batching-operations-wcf-data-services.md)di invio in batch.  
  
 Nell'esempio riportato in questo argomento vengono usati il servizio dati Northwind di esempio e le classi del servizio dati client generate automaticamente. Questo servizio e le classi di dati client vengono creati al completamento della [WCF Data Services avvio rapido](quickstart-wcf-data-services.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come chiamare il metodo <xref:System.Data.Services.Client.DataServiceContext.ExecuteBatch%2A> per eseguire una matrice di oggetti <xref:System.Data.Services.Client.DataServiceRequest%601> contenente query che restituiscono gli oggetti `Customers` e `Products` dal servizio dati Northwind. La raccolta di oggetti <xref:System.Data.Services.Client.QueryOperationResponse%601> inclusa nell'oggetto <xref:System.Data.Services.Client.DataServiceResponse> restituito viene enumerata, allo stesso modo della raccolta di oggetti inclusa in ogni oggetto <xref:System.Data.Services.Client.QueryOperationResponse%601>.  
  
 [!code-csharp[Astoria Northwind Client#BatchQuery](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#batchquery)]
 [!code-vb[Astoria Northwind Client#BatchQuery](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#batchquery)]  
  
## <a name="see-also"></a>Vedere anche

- [Libreria client WCF Data Services](wcf-data-services-client-library.md)
