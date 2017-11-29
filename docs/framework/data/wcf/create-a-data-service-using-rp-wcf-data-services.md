---
title: 'Procedura: creare un servizio dati tramite il provider di reflection (WCF Data Services)'
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
helpviewer_keywords: WCF Data Services, providers
ms.assetid: 7315c6d8-f452-4fb2-a0c1-76ab0593c146
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: dc3f576b3d2f60fb4cbc6ac2b7b27191cb952904
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-data-service-using-the-reflection-provider-wcf-data-services"></a>Procedura: creare un servizio dati tramite il provider di reflection (WCF Data Services)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] consente di definire un modello di dati basato su classi arbitrarie, purché tali classi siano esposte come oggetti che implementano l'interfaccia <xref:System.Linq.IQueryable%601>. Per ulteriori informazioni, vedere [provider di servizi dati](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene definito un modello di dati che include `Orders` e `Items`. La classe contenitore di entità `OrderItemData` dispone di due metodi pubblici che restituiscono le interfacce <xref:System.Linq.IQueryable%601>. Queste interfacce sono set di entità dei tipi di entità `Orders` e `Items`. Un'entità `Order` può includere più entità `Items`, pertanto il tipo di entità `Orders` dispone di una proprietà di navigazione `Items` che restituisce una raccolta di oggetti `Items`. La classe contenitore di entità `OrderItemData` è il tipo generico della classe <xref:System.Data.Services.DataService%601> da cui deriva il servizio dati `OrderItems`.  
  
> [!NOTE]
>  Poiché in questo esempio viene illustrato un provider di dati in memoria e le modifiche non vengono rese persistenti all'esterno delle istanze degli oggetti correnti, l'implementazione dell'interfaccia <xref:System.Data.Services.IUpdatable> non produce alcun vantaggio. Per un esempio che implementa il <xref:System.Data.Services.IUpdatable> interfaccia, vedere [procedura: creare un servizio dati utilizzando LINQ to SQL origine](../../../../docs/framework/data/wcf/create-a-data-service-using-linq-to-sql-wcf.md).  
  
 [!code-csharp[Astoria Reflection Provider#CustomIQueryable](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria reflection provider/cs/orderitems.svc.cs#customiqueryable)]
 [!code-vb[Astoria Reflection Provider#CustomIQueryable](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria reflection provider/vb/orderitems.svc.vb#customiqueryable)]  
  
## <a name="see-also"></a>Vedere anche  
 [Procedura: creare un servizio dati tramite LINQ all'origine dati SQL](../../../../docs/framework/data/wcf/create-a-data-service-using-linq-to-sql-wcf.md)  
 [Provider di servizi dati](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md)  
 [Procedura: creare un servizio dati tramite un'origine dati di ADO.NET Entity Framework](../../../../docs/framework/data/wcf/create-a-data-service-using-an-adonet-ef-data-wcf.md)
