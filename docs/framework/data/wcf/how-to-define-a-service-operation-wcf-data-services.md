---
title: "Procedura: definire un'operazione del servizio (WCF Data Services)"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Service Operations [WCF Data Services]
- WCF Data Services, service operations
ms.assetid: dfcd3cb1-2f07-4d0b-b16a-6b056c4f45fa
ms.openlocfilehash: e9d15698c1e020f5b4179efb3e8492f3754ff02f
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2019
ms.locfileid: "74569133"
---
# <a name="how-to-define-a-service-operation-wcf-data-services"></a>Procedura: definire un'operazione del servizio (WCF Data Services)

WCF Data Services esporre i metodi definiti nel server come operazioni del servizio. Le operazioni del servizio consentono a un servizio dati di fornire l'accesso tramite un URI a un metodo definito nel server. Per definire un'operazione del servizio, applicare l'attributo [`WebGet]` o `[WebInvoke]` al metodo. Per supportare gli operatori di query, l'operazione del servizio deve restituire un'istanza di <xref:System.Linq.IQueryable%601>. L'accesso ai dati sottostanti da parte delle operazioni del servizio può essere eseguito tramite la proprietà <xref:System.Data.Services.DataService%601.CurrentDataSource%2A> su <xref:System.Data.Services.DataService%601>. Per altre informazioni, vedere [operazioni del servizio](service-operations-wcf-data-services.md).

Nell'esempio incluso in questo argomento viene definita un'operazione del servizio denominata `GetOrdersByCity` che restituisce un'istanza di <xref:System.Linq.IQueryable%601> filtrata relativa a `Orders` e agli oggetti `Order_Details` correlati. Nell'esempio viene eseguito l'accesso all'istanza di <xref:System.Data.Objects.ObjectContext> che rappresenta l'origine dati per il servizio dati Northwind di esempio. Questo servizio viene creato al completamento della [WCF Data Services Guida introduttiva](quickstart-wcf-data-services.md).

### <a name="to-define-a-service-operation-in-the-northwind-data-service"></a>Per definire un'operazione del servizio nel servizio dati Northwind

1. Nel progetto del servizio dati Northwind aprire il file Northwind.svc.

2. Nella classe `Northwind` definire un metodo dell'operazione del servizio denominato `GetOrdersByCity` nel modo seguente:

     [!code-csharp[Astoria Northwind Service#ServiceOperationDef](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind2.svc.cs#serviceoperationdef)]
     [!code-vb[Astoria Northwind Service#ServiceOperationDef](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind2.svc.vb#serviceoperationdef)]

3. Nel metodo `InitializeService` della classe `Northwind` aggiungere il codice seguente per abilitare l'accesso all'operazione del servizio:

     [!code-csharp[Astoria Northwind Service#ServiceOperationConfig](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind2.svc.cs#serviceoperationconfig)]
     [!code-vb[Astoria Northwind Service#ServiceOperationConfig](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind2.svc.vb#serviceoperationconfig)]

### <a name="to-query-the-getordersbycity-service-operation"></a>Per eseguire una query sull'operazione del servizio GetOrdersByCity

- In un browser immettere uno degli URI indicati di seguito per richiamare l'operazione del servizio definita nell'esempio seguente:

  - `http://localhost:12345/Northwind.svc/GetOrdersByCity?city='London'`

  - `http://localhost:12345/Northwind.svc/GetOrdersByCity?city='London'&$top=2`

  - `http://localhost:12345/Northwind.svc/GetOrdersByCity?city='London'&$expand=Order_Details&$orderby=RequiredDate desc`

## <a name="example"></a>Esempio

Nell'esempio seguente viene implementa un'operazione del servizio denominata `GetOrderByCity` nel servizio dati Northwind. Questa operazione usa ADO.NET Entity Framework per restituire un set di oggetti `Orders` e di oggetti `Order_Details` correlati come istanza di <xref:System.Linq.IQueryable%601> in base al nome di città specificato.

> [!NOTE]
> Gli operatori di query sono supportati su questo endpoint dell'operazione del servizio in quanto il metodo restituisce un'istanza di <xref:System.Linq.IQueryable%601>.

[!code-csharp[Astoria Northwind Service#ServiceOperation](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind2.svc.cs#serviceoperation)]
[!code-vb[Astoria Northwind Service#ServiceOperation](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind2.svc.vb#serviceoperation)]

## <a name="see-also"></a>Vedere anche

- [Definizione di WCF Data Services](defining-wcf-data-services.md)
