---
title: 'Procedura: intercettare messaggi del servizio dati (WCF Data Services)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, customizing
- query interceptors [WCF Data Services]
ms.assetid: 24b9df1b-b54b-4795-a033-edf333675de6
ms.openlocfilehash: 4f2d6cf34c820c60181d5287298898af5eb8d038
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2019
ms.locfileid: "74569036"
---
# <a name="how-to-intercept-data-service-messages-wcf-data-services"></a>Procedura: intercettare messaggi del servizio dati (WCF Data Services)
Con WCF Data Services, è possibile intercettare i messaggi di richiesta in modo che sia possibile aggiungere la logica personalizzata a un'operazione. Per intercettare un messaggio, è possibile utilizzare metodi con attributi specifici nel servizio dati. Per ulteriori informazioni, vedere [intercettori](interceptors-wcf-data-services.md).  
  
 Nell'esempio riportato in questo argomento viene usato il servizio dati Northwind di esempio. Questo servizio viene creato al completamento della [WCF Data Services Guida introduttiva](quickstart-wcf-data-services.md).  
  
### <a name="to-define-a-query-interceptor-for-the-orders-entity-set"></a>Per definire un intercettore di query per il set di entità Orders  
  
1. Nel progetto del servizio dati Northwind aprire il file Northwind.svc.  
  
2. Nella tabella codici per la classe `Northwind` aggiungere l'istruzione `using` riportata di seguito (`Imports` in Visual Basic).  
  
     [!code-csharp[Astoria Northwind Service#UsingLinqExpressions](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind2.svc.cs#usinglinqexpressions)]
     [!code-vb[Astoria Northwind Service#UsingLinqExpressions](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind2.svc.vb#usinglinqexpressions)]  
  
3. Nella classe `Northwind` definire un metodo dell'operazione del servizio denominato `OnQueryOrders` nel modo seguente:  
  
     [!code-csharp[Astoria Northwind Service#QueryInterceptorDef](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind2.svc.cs#queryinterceptordef)]
     [!code-vb[Astoria Northwind Service#QueryInterceptorDef](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind2.svc.vb#queryinterceptordef)]  
  
### <a name="to-define-a-change-interceptor-for-the-products-entity-set"></a>Per definire un intercettore di modifiche per il set di entità Products  
  
1. Nel progetto del servizio dati Northwind aprire il file Northwind.svc.  
  
2. Nella classe `Northwind` definire un metodo dell'operazione del servizio denominato `OnChangeProducts` nel modo seguente:  
  
     [!code-csharp[Astoria Northwind Service#ChangeInterceptorDef](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind2.svc.cs#changeinterceptordef)]
     [!code-vb[Astoria Northwind Service#ChangeInterceptorDef](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind2.svc.vb#changeinterceptordef)]  
  
## <a name="example"></a>Esempio  
 In questo esempio viene definito un metodo intercettore di query per il set di entità `Orders` che restituisce un'espressione lambda. Questa espressione contiene un delegato che filtra gli `Orders` richiesti in base ai `Customers` correlati che presentano un nome di contatto specifico. Il nome viene a sua volta determinato in base all'utente che lo richiede. In questo esempio si presuppone che il servizio dati sia ospitato all'interno di un'applicazione Web ASP.NET che usa WCF e che l'autenticazione è abilitata. La classe <xref:System.Web.HttpContext> viene usata per recuperare il principio della richiesta corrente.  
  
 [!code-csharp[Astoria Northwind Service#QueryInterceptor](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind2.svc.cs#queryinterceptor)]
 [!code-vb[Astoria Northwind Service#QueryInterceptor](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind2.svc.vb#queryinterceptor)]  
  
## <a name="example"></a>Esempio  
 In questo esempio viene definito un metodo intercettore di modifiche per il set di entità `Products`. Questo metodo convalida l'input per il servizio per un'operazione <xref:System.Data.Services.UpdateOperations.Add> o <xref:System.Data.Services.UpdateOperations.Change> e genera un'eccezione quando una modifica viene apportata a un prodotto non più disponibile. Blocca inoltre l'eliminazione di prodotti come operazione non supportata.  
  
 [!code-csharp[Astoria Northwind Service#ChangeInterceptor](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind2.svc.cs#changeinterceptor)]
 [!code-vb[Astoria Northwind Service#ChangeInterceptor](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind2.svc.vb#changeinterceptor)]  
  
## <a name="see-also"></a>Vedere anche

- [Procedura: definire un operatore del servizio](how-to-define-a-service-operation-wcf-data-services.md)
- [Definizione di WCF Data Services](defining-wcf-data-services.md)
