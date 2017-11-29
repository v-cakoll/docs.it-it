---
title: Intercettori (WCF Data Services)
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
- WCF Data Services, customizing
- query interceptors [WCF Data Services]
ms.assetid: e33ae8dc-8069-41d0-99a0-75ff28db7050
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 7aad516b819723c97a40a016a46ddcbe0fcdf4d2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="interceptors-wcf-data-services"></a><span data-ttu-id="84a62-102">Intercettori (WCF Data Services)</span><span class="sxs-lookup"><span data-stu-id="84a62-102">Interceptors (WCF Data Services)</span></span>
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]<span data-ttu-id="84a62-103">consente a un'applicazione intercettare i messaggi di richiesta in modo che è possibile aggiungere la logica personalizzata a un'operazione.</span><span class="sxs-lookup"><span data-stu-id="84a62-103"> enables an application to intercept request messages so that you can add custom logic to an operation.</span></span> <span data-ttu-id="84a62-104">È possibile utilizzare questa logica personalizzata per convalidare i dati nei messaggi in arrivo.</span><span class="sxs-lookup"><span data-stu-id="84a62-104">You can use this custom logic to validate data in incoming messages.</span></span> <span data-ttu-id="84a62-105">È inoltre possibile usarla per limitare ulteriormente l'ambito di una richiesta di query, inserendo ad esempio criteri di autorizzazione personalizzati per le singole richieste.</span><span class="sxs-lookup"><span data-stu-id="84a62-105">You can also use it to further restrict the scope of a query request, such as to insert a custom authorization policy on a per request basis.</span></span>  
  
 <span data-ttu-id="84a62-106">L'intercettazione viene eseguita specificando metodi attribuiti in modo specifico nel servizio dati.</span><span class="sxs-lookup"><span data-stu-id="84a62-106">Interception is performed by specially attributed methods in the data service.</span></span> <span data-ttu-id="84a62-107">Questi metodi vengono chiamati da [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] al momento appropriato durante l'elaborazione del messaggio.</span><span class="sxs-lookup"><span data-stu-id="84a62-107">These methods are called by [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] at the appropriate point in message processing.</span></span> <span data-ttu-id="84a62-108">Gli intercettori vengono definiti nel set di base per ogni entità e i metodi dell'intercettore non accettano parametri della richiesta come operazioni del servizio.</span><span class="sxs-lookup"><span data-stu-id="84a62-108">Interceptors are defined on a per-entity set basis, and interceptor methods cannot accept parameters from the request like service operations can.</span></span> <span data-ttu-id="84a62-109">I metodi dell'intercettore di query, chiamati durante l'elaborazione di una richiesta HTTP GET, devono restituire un'espressione lambda che determina se un'istanza di entità dell'intercettore set deve essere restituita nei risultati della query.</span><span class="sxs-lookup"><span data-stu-id="84a62-109">Query interceptor methods, which are called when processing an HTTP GET request, must return a lambda expression that determines whether an instance of the interceptor's entity set should be returned by the query results.</span></span> <span data-ttu-id="84a62-110">Questa espressione viene usata dal servizio dati per definire ulteriormente l'operazione richiesta.</span><span class="sxs-lookup"><span data-stu-id="84a62-110">This expression is used by the data service to further refine the requested operation.</span></span> <span data-ttu-id="84a62-111">Di seguito viene riportato un esempio di definizione di un intercettore di query.</span><span class="sxs-lookup"><span data-stu-id="84a62-111">The following is an example definition of a query interceptor.</span></span>  
  
 [!code-csharp[Astoria Northwind Service#QueryInterceptorDef](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind service/cs/northwind2.svc.cs#queryinterceptordef)]
 [!code-vb[Astoria Northwind Service#QueryInterceptorDef](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind service/vb/northwind2.svc.vb#queryinterceptordef)]  
  
 <span data-ttu-id="84a62-112">Per ulteriori informazioni, vedere [procedura: intercettare messaggi del servizio dati](../../../../docs/framework/data/wcf/how-to-intercept-data-service-messages-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="84a62-112">For more information, see [How to: Intercept Data Service Messages](../../../../docs/framework/data/wcf/how-to-intercept-data-service-messages-wcf-data-services.md).</span></span>  
  
 <span data-ttu-id="84a62-113">Gli intercettori di modifiche, chiamati durante l'elaborazione di operazioni non di query, devono restituire `void` (`Nothing` in Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="84a62-113">Change interceptors, which are called when processing non-query operations, must return `void` (`Nothing` in Visual Basic).</span></span> <span data-ttu-id="84a62-114">I metodi dell'intercettore di modifiche devono accettare i due parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="84a62-114">Change interceptor methods must accept the following two parameters:</span></span>  
  
1.  <span data-ttu-id="84a62-115">Un parametro di un tipo compatibile con il tipo di entità del set di entità.</span><span class="sxs-lookup"><span data-stu-id="84a62-115">A parameter of a type that is compatible with the entity type of the entity set.</span></span> <span data-ttu-id="84a62-116">Quando il servizio dati richiama l'intercettore di modifiche, il valore di questo parametro riflette le informazioni sull'entità inviate dalla richiesta.</span><span class="sxs-lookup"><span data-stu-id="84a62-116">When the data service invokes the change interceptor, the value of this parameter will reflect the entity information that is sent by the request.</span></span>  
  
2.  <span data-ttu-id="84a62-117">Un parametro di tipo <xref:System.Data.Services.UpdateOperations>.</span><span class="sxs-lookup"><span data-stu-id="84a62-117">A parameter of type <xref:System.Data.Services.UpdateOperations>.</span></span> <span data-ttu-id="84a62-118">Quando il servizio dati richiama l'intercettore di modifiche, il valore di questo parametro riflette l'operazione tentata dalla richiesta.</span><span class="sxs-lookup"><span data-stu-id="84a62-118">When the data service invokes the change interceptor, the value of this parameter will reflect the operation that the request is trying to perform.</span></span>  
  
 <span data-ttu-id="84a62-119">Di seguito viene riportato un esempio di definizione di un intercettore di modifiche.</span><span class="sxs-lookup"><span data-stu-id="84a62-119">The following is an example definition of a change interceptor.</span></span>  
  
 [!code-csharp[Astoria Northwind Service#ChangeInterceptorDef](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind service/cs/northwind2.svc.cs#changeinterceptordef)]
 [!code-vb[Astoria Northwind Service#ChangeInterceptorDef](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind service/vb/northwind2.svc.vb#changeinterceptordef)]  
  
 <span data-ttu-id="84a62-120">Per ulteriori informazioni, vedere [procedura: intercettare messaggi del servizio dati](../../../../docs/framework/data/wcf/how-to-intercept-data-service-messages-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="84a62-120">For more information, see [How to: Intercept Data Service Messages](../../../../docs/framework/data/wcf/how-to-intercept-data-service-messages-wcf-data-services.md).</span></span>  
  
 <span data-ttu-id="84a62-121">Gli attributi che seguono sono supportati per l'intercettazione.</span><span class="sxs-lookup"><span data-stu-id="84a62-121">The following attributes are supported for interception.</span></span>  
  
 <span data-ttu-id="84a62-122">**[QueryInterceptor (** *EntitySetName* **)]**</span><span class="sxs-lookup"><span data-stu-id="84a62-122">**[QueryInterceptor(** *EnitySetName* **)]**</span></span>  
 <span data-ttu-id="84a62-123">Metodi a cui è applicato l'attributo <xref:System.Data.Services.QueryInterceptorAttribute> vengono chiamati quando una richiesta GET HTTP viene ricevuta per la risorsa del set di entità di destinazione.</span><span class="sxs-lookup"><span data-stu-id="84a62-123">Methods with the <xref:System.Data.Services.QueryInterceptorAttribute> attribute applied are called when an HTTP GET request is received for the targeted entity set resource.</span></span> <span data-ttu-id="84a62-124">Questi metodi devono restituire sempre un'espressione lambda nel formato `Expression<Func<T,bool>>`.</span><span class="sxs-lookup"><span data-stu-id="84a62-124">These methods must always return a lambda expression in the form of `Expression<Func<T,bool>>`.</span></span>  
  
 <span data-ttu-id="84a62-125">**[ChangeInterceptor (** *EntitySetName* **)]**</span><span class="sxs-lookup"><span data-stu-id="84a62-125">**[ChangeInterceptor(** *EnitySetName* **)]**</span></span>  
 <span data-ttu-id="84a62-126">Metodi a cui è applicato l'attributo <xref:System.Data.Services.ChangeInterceptorAttribute> vengono chiamati quando una richiesta HTTP diversa da GET viene ricevuta per la risorsa del set di entità di destinazione.</span><span class="sxs-lookup"><span data-stu-id="84a62-126">Methods with the <xref:System.Data.Services.ChangeInterceptorAttribute> attribute applied are called when an HTTP request other than HTTP GET request is received for the targeted entity set resource.</span></span> <span data-ttu-id="84a62-127">Questi metodi devono restituire sempre `void` (`Nothing` in Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="84a62-127">These methods must always return `void` (`Nothing` in Visual Basic).</span></span>  
  
 <span data-ttu-id="84a62-128">Per ulteriori informazioni, vedere [procedura: intercettare messaggi del servizio dati](../../../../docs/framework/data/wcf/how-to-intercept-data-service-messages-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="84a62-128">For more information, see [How to: Intercept Data Service Messages](../../../../docs/framework/data/wcf/how-to-intercept-data-service-messages-wcf-data-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84a62-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="84a62-129">See Also</span></span>  
 [<span data-ttu-id="84a62-130">Operazioni del servizio</span><span class="sxs-lookup"><span data-stu-id="84a62-130">Service Operations</span></span>](../../../../docs/framework/data/wcf/service-operations-wcf-data-services.md)
