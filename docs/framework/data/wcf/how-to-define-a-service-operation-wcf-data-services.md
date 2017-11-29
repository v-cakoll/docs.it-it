---
title: 'Procedura: definire un''operazione del servizio (WCF Data Services)'
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
- Service Operations [WCF Data Services]
- WCF Data Services, service operations
ms.assetid: dfcd3cb1-2f07-4d0b-b16a-6b056c4f45fa
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: feac51c92a7e963d440eefbae94a58b94f49797e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-define-a-service-operation-wcf-data-services"></a><span data-ttu-id="0992c-102">Procedura: definire un'operazione del servizio (WCF Data Services)</span><span class="sxs-lookup"><span data-stu-id="0992c-102">How to: Define a Service Operation (WCF Data Services)</span></span>
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]<span data-ttu-id="0992c-103"> espone i metodi definiti nel server come operazioni del servizio.</span><span class="sxs-lookup"><span data-stu-id="0992c-103"> expose methods that are defined on the server as service operations.</span></span> <span data-ttu-id="0992c-104">Operazioni del servizio consentono a un servizio dati per fornire l'accesso tramite un URI a un metodo definito nel server.</span><span class="sxs-lookup"><span data-stu-id="0992c-104">Service operations allow a data service to provide access through a URI to a method that is defined on the server.</span></span> <span data-ttu-id="0992c-105">Per definire un'operazione del servizio, si applicano le [`WebGet]` o `[WebInvoke]` attributo al metodo.</span><span class="sxs-lookup"><span data-stu-id="0992c-105">To define a service operation, apply the [`WebGet]` or `[WebInvoke]` attribute to the method.</span></span> <span data-ttu-id="0992c-106">Per supportare gli operatori di query, l'operazione di servizio deve restituire un <xref:System.Linq.IQueryable%601> istanza.</span><span class="sxs-lookup"><span data-stu-id="0992c-106">To support query operators, the service operation must return an <xref:System.Linq.IQueryable%601> instance.</span></span> <span data-ttu-id="0992c-107">L'accesso ai dati sottostanti da parte delle operazioni del servizio può essere eseguito tramite la proprietà <xref:System.Data.Services.DataService%601.CurrentDataSource%2A> su <xref:System.Data.Services.DataService%601>.</span><span class="sxs-lookup"><span data-stu-id="0992c-107">Service operations may access the underlying data source through the <xref:System.Data.Services.DataService%601.CurrentDataSource%2A> property on the <xref:System.Data.Services.DataService%601>.</span></span> <span data-ttu-id="0992c-108">Per ulteriori informazioni, vedere [operazioni del servizio](../../../../docs/framework/data/wcf/service-operations-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="0992c-108">For more information, see [Service Operations](../../../../docs/framework/data/wcf/service-operations-wcf-data-services.md).</span></span>  
  
 <span data-ttu-id="0992c-109">Nell'esempio incluso in questo argomento viene definita un'operazione del servizio denominata `GetOrdersByCity` che restituisce un'istanza di <xref:System.Linq.IQueryable%601> filtrata relativa a `Orders` e agli oggetti `Order_Details` correlati.</span><span class="sxs-lookup"><span data-stu-id="0992c-109">The example in this topic defines a service operation named `GetOrdersByCity` that returns a filtered <xref:System.Linq.IQueryable%601> instance of `Orders` and related `Order_Details` objects.</span></span> <span data-ttu-id="0992c-110">Nell'esempio viene eseguito l'accesso all'istanza di <xref:System.Data.Objects.ObjectContext> che rappresenta l'origine dati per il servizio dati Northwind di esempio.</span><span class="sxs-lookup"><span data-stu-id="0992c-110">The example accesses the <xref:System.Data.Objects.ObjectContext> instance that is the data source for the Northwind sample data service.</span></span> <span data-ttu-id="0992c-111">Questo servizio viene creato quando si completa la [Guida rapida di WCF Data Services](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="0992c-111">This service is created when you complete the [WCF Data Services quickstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).</span></span>  
  
### <a name="to-define-a-service-operation-in-the-northwind-data-service"></a><span data-ttu-id="0992c-112">Per definire un'operazione del servizio nel servizio dati Northwind</span><span class="sxs-lookup"><span data-stu-id="0992c-112">To define a service operation in the Northwind data service</span></span>  
  
1.  <span data-ttu-id="0992c-113">Nel progetto del servizio dati Northwind aprire il file Northwind.svc.</span><span class="sxs-lookup"><span data-stu-id="0992c-113">In the Northwind data service project, open the Northwind.svc file.</span></span>  
  
2.  <span data-ttu-id="0992c-114">Nella classe `Northwind` definire un metodo dell'operazione del servizio denominato `GetOrdersByCity` nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="0992c-114">In the `Northwind` class, define a service operation method named `GetOrdersByCity` as follows:</span></span>  
  
     [!code-csharp[Astoria Northwind Service#ServiceOperationDef](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind service/cs/northwind2.svc.cs#serviceoperationdef)]
     [!code-vb[Astoria Northwind Service#ServiceOperationDef](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind service/vb/northwind2.svc.vb#serviceoperationdef)]  
  
3.  <span data-ttu-id="0992c-115">Nel metodo `InitializeService` della classe `Northwind` aggiungere il codice seguente per abilitare l'accesso all'operazione del servizio:</span><span class="sxs-lookup"><span data-stu-id="0992c-115">In the `InitializeService` method of the `Northwind` class, add the following code to enable access to the service operation:</span></span>  
  
     [!code-csharp[Astoria Northwind Service#ServiceOperationConfig](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind service/cs/northwind2.svc.cs#serviceoperationconfig)]
     [!code-vb[Astoria Northwind Service#ServiceOperationConfig](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind service/vb/northwind2.svc.vb#serviceoperationconfig)]  
  
### <a name="to-query-the-getordersbycity-service-operation"></a><span data-ttu-id="0992c-116">Per eseguire una query sull'operazione del servizio GetOrdersByCity</span><span class="sxs-lookup"><span data-stu-id="0992c-116">To query the GetOrdersByCity service operation</span></span>  
  
-   <span data-ttu-id="0992c-117">In un browser immettere uno degli URI indicati di seguito per richiamare l'operazione del servizio definita nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="0992c-117">In a Web browser, enter one of the following URIs to invoke the service operation that is defined in the following example:</span></span>  
  
    -   `http://localhost:12345/Northwind.svc/GetOrdersByCity?city='London'`  
  
    -   `http://localhost:12345/Northwind.svc/GetOrdersByCity?city='London'&$top=2`  
  
    -   `http://localhost:12345/Northwind.svc/GetOrdersByCity?city='London'&$expand=Order_Details&$orderby=RequiredDate desc`  
  
## <a name="example"></a><span data-ttu-id="0992c-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="0992c-118">Example</span></span>  
 <span data-ttu-id="0992c-119">Nell'esempio seguente viene implementa un'operazione del servizio denominata `GetOrderByCity` nel servizio dati Northwind.</span><span class="sxs-lookup"><span data-stu-id="0992c-119">The following example implements a service operation named `GetOrderByCity` on the Northwind data service.</span></span> <span data-ttu-id="0992c-120">Questa operazione usa ADO.NET Entity Framework per restituire un set di oggetti `Orders` e di oggetti `Order_Details` correlati come istanza di <xref:System.Linq.IQueryable%601> in base al nome di città specificato.</span><span class="sxs-lookup"><span data-stu-id="0992c-120">This operation uses the ADO.NET Entity Framework to return a set of `Orders` and related `Order_Details` objects as an <xref:System.Linq.IQueryable%601> instance based on the provided city name.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0992c-121">Gli operatori di query sono supportati su questo endpoint dell'operazione del servizio in quanto il metodo restituisce un'istanza di <xref:System.Linq.IQueryable%601>.</span><span class="sxs-lookup"><span data-stu-id="0992c-121">Query operators are supported on this service operation endpoint because the method returns an <xref:System.Linq.IQueryable%601> instance.</span></span>  
  
 [!code-csharp[Astoria Northwind Service#ServiceOperation](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind service/cs/northwind2.svc.cs#serviceoperation)]
 [!code-vb[Astoria Northwind Service#ServiceOperation](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind service/vb/northwind2.svc.vb#serviceoperation)]  
  
## <a name="see-also"></a><span data-ttu-id="0992c-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0992c-122">See Also</span></span>  
 [<span data-ttu-id="0992c-123">Definizione di WCF Data Services</span><span class="sxs-lookup"><span data-stu-id="0992c-123">Defining WCF Data Services</span></span>](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)
