---
title: 'Procedura: Intercettare messaggi del servizio dati (WCF Data Services)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, customizing
- query interceptors [WCF Data Services]
ms.assetid: 24b9df1b-b54b-4795-a033-edf333675de6
ms.openlocfilehash: ad0673f72b1a81d6bcfaf0704ccd698eda7bb20c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59517833"
---
# <a name="how-to-intercept-data-service-messages-wcf-data-services"></a><span data-ttu-id="55414-102">Procedura: Intercettare messaggi del servizio dati (WCF Data Services)</span><span class="sxs-lookup"><span data-stu-id="55414-102">How to: Intercept Data Service Messages (WCF Data Services)</span></span>
<span data-ttu-id="55414-103">Con [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] è possibile intercettare i messaggi di richiesta per l'aggiunta di logica personalizzata a un'operazione.</span><span class="sxs-lookup"><span data-stu-id="55414-103">With [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)], you can intercept request messages so that you can add custom logic to an operation.</span></span> <span data-ttu-id="55414-104">Per intercettare un messaggio, si usano metodi attribuiti in modo specifico nel servizio dati.</span><span class="sxs-lookup"><span data-stu-id="55414-104">To intercept a message, you use specially attributed methods in the data service.</span></span> <span data-ttu-id="55414-105">Per altre informazioni, vedere [intercettori](../../../../docs/framework/data/wcf/interceptors-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="55414-105">For more information, see [Interceptors](../../../../docs/framework/data/wcf/interceptors-wcf-data-services.md).</span></span>  
  
 <span data-ttu-id="55414-106">Nell'esempio riportato in questo argomento viene usato il servizio dati Northwind di esempio.</span><span class="sxs-lookup"><span data-stu-id="55414-106">The example in this topic uses the Northwind sample data service.</span></span> <span data-ttu-id="55414-107">Questo servizio viene creato quando si completa la [Guida rapida di WCF Data Services](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="55414-107">This service is created when you complete the [WCF Data Services quickstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).</span></span>  
  
### <a name="to-define-a-query-interceptor-for-the-orders-entity-set"></a><span data-ttu-id="55414-108">Per definire un intercettore di query per il set di entità Orders</span><span class="sxs-lookup"><span data-stu-id="55414-108">To define a query interceptor for the Orders entity set</span></span>  
  
1. <span data-ttu-id="55414-109">Nel progetto del servizio dati Northwind aprire il file Northwind.svc.</span><span class="sxs-lookup"><span data-stu-id="55414-109">In the Northwind data service project, open the Northwind.svc file.</span></span>  
  
2. <span data-ttu-id="55414-110">Nella tabella codici per la classe `Northwind` aggiungere l'istruzione `using` riportata di seguito (`Imports` in Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="55414-110">In the code page for the `Northwind` class, add the following `using` statement (`Imports` in Visual Basic).</span></span>  
  
     [!code-csharp[Astoria Northwind Service#UsingLinqExpressions](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind2.svc.cs#usinglinqexpressions)]
     [!code-vb[Astoria Northwind Service#UsingLinqExpressions](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind2.svc.vb#usinglinqexpressions)]  
  
3. <span data-ttu-id="55414-111">Nella classe `Northwind` definire un metodo dell'operazione del servizio denominato `OnQueryOrders` nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="55414-111">In the `Northwind` class, define a service operation method named `OnQueryOrders` as follows:</span></span>  
  
     [!code-csharp[Astoria Northwind Service#QueryInterceptorDef](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind2.svc.cs#queryinterceptordef)]
     [!code-vb[Astoria Northwind Service#QueryInterceptorDef](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind2.svc.vb#queryinterceptordef)]  
  
### <a name="to-define-a-change-interceptor-for-the-products-entity-set"></a><span data-ttu-id="55414-112">Per definire un intercettore di modifiche per il set di entità Products</span><span class="sxs-lookup"><span data-stu-id="55414-112">To define a change interceptor for the Products entity set</span></span>  
  
1. <span data-ttu-id="55414-113">Nel progetto del servizio dati Northwind aprire il file Northwind.svc.</span><span class="sxs-lookup"><span data-stu-id="55414-113">In the Northwind data service project, open the Northwind.svc file.</span></span>  
  
2. <span data-ttu-id="55414-114">Nella classe `Northwind` definire un metodo dell'operazione del servizio denominato `OnChangeProducts` nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="55414-114">In the `Northwind` class, define a service operation method named `OnChangeProducts` as follows:</span></span>  
  
     [!code-csharp[Astoria Northwind Service#ChangeInterceptorDef](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind2.svc.cs#changeinterceptordef)]
     [!code-vb[Astoria Northwind Service#ChangeInterceptorDef](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind2.svc.vb#changeinterceptordef)]  
  
## <a name="example"></a><span data-ttu-id="55414-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="55414-115">Example</span></span>  
 <span data-ttu-id="55414-116">In questo esempio viene definito un metodo intercettore di query per il set di entità `Orders` che restituisce un'espressione lambda.</span><span class="sxs-lookup"><span data-stu-id="55414-116">This example defines a query interceptor method for the `Orders` entity set that returns a lambda expression.</span></span> <span data-ttu-id="55414-117">Questa espressione contiene un delegato che filtra gli `Orders` richiesti in base ai `Customers` correlati che presentano un nome di contatto specifico.</span><span class="sxs-lookup"><span data-stu-id="55414-117">This expression contains a delegate that filters the requested `Orders` based on related `Customers` that have a specific contact name.</span></span> <span data-ttu-id="55414-118">Il nome viene a sua volta determinato in base all'utente che lo richiede.</span><span class="sxs-lookup"><span data-stu-id="55414-118">The name is in turn determined based on the requesting user.</span></span> <span data-ttu-id="55414-119">In questo esempio si presuppone che il servizio dati sia ospitato all'interno di un'applicazione Web ASP.NET che usa WCF e che l'autenticazione è abilitata.</span><span class="sxs-lookup"><span data-stu-id="55414-119">This example assumes that the data service is hosted within an ASP.NET Web application that uses WCF, and that authentication is enabled.</span></span> <span data-ttu-id="55414-120">La classe <xref:System.Web.HttpContext> viene usata per recuperare il principio della richiesta corrente.</span><span class="sxs-lookup"><span data-stu-id="55414-120">The <xref:System.Web.HttpContext> class is used to retrieve the principle of the current request.</span></span>  
  
 [!code-csharp[Astoria Northwind Service#QueryInterceptor](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind2.svc.cs#queryinterceptor)]
 [!code-vb[Astoria Northwind Service#QueryInterceptor](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind2.svc.vb#queryinterceptor)]  
  
## <a name="example"></a><span data-ttu-id="55414-121">Esempio</span><span class="sxs-lookup"><span data-stu-id="55414-121">Example</span></span>  
 <span data-ttu-id="55414-122">In questo esempio viene definito un metodo intercettore di modifiche per il set di entità `Products`.</span><span class="sxs-lookup"><span data-stu-id="55414-122">This example defines a change interceptor method for the `Products` entity set.</span></span> <span data-ttu-id="55414-123">Questo metodo convalida l'input per il servizio per un'operazione <xref:System.Data.Services.UpdateOperations.Add> o <xref:System.Data.Services.UpdateOperations.Change> e genera un'eccezione quando una modifica viene apportata a un prodotto non più disponibile.</span><span class="sxs-lookup"><span data-stu-id="55414-123">This method validates input to the service for an <xref:System.Data.Services.UpdateOperations.Add> or <xref:System.Data.Services.UpdateOperations.Change> operation and raises an exception if a change is being made to a discontinued product.</span></span> <span data-ttu-id="55414-124">Blocca inoltre l'eliminazione di prodotti come operazione non supportata.</span><span class="sxs-lookup"><span data-stu-id="55414-124">It also blocks the deletion of products as an unsupported operation.</span></span>  
  
 [!code-csharp[Astoria Northwind Service#ChangeInterceptor](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind2.svc.cs#changeinterceptor)]
 [!code-vb[Astoria Northwind Service#ChangeInterceptor](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind2.svc.vb#changeinterceptor)]  
  
## <a name="see-also"></a><span data-ttu-id="55414-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="55414-125">See also</span></span>

- [<span data-ttu-id="55414-126">Procedura: Definire un'operazione del servizio</span><span class="sxs-lookup"><span data-stu-id="55414-126">How to: Define a Service Operation</span></span>](../../../../docs/framework/data/wcf/how-to-define-a-service-operation-wcf-data-services.md)
- [<span data-ttu-id="55414-127">Definizione di WCF Data Services</span><span class="sxs-lookup"><span data-stu-id="55414-127">Defining WCF Data Services</span></span>](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)
