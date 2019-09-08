---
title: 'Procedura: Creazione di un servizio dati tramite il provider di Reflection (WCF Data Services)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, providers
ms.assetid: 7315c6d8-f452-4fb2-a0c1-76ab0593c146
ms.openlocfilehash: feee679c37cd3dafb80021752ee25444c54f0809
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70791001"
---
# <a name="how-to-create-a-data-service-using-the-reflection-provider-wcf-data-services"></a>Procedura: Creazione di un servizio dati tramite il provider di Reflection (WCF Data Services)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] consente di definire un modello di dati basato su classi arbitrarie, purché tali classi siano esposte come oggetti che implementano l'interfaccia <xref:System.Linq.IQueryable%601>. Per ulteriori informazioni, vedere [provider di servizi dati](data-services-providers-wcf-data-services.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene definito un modello di dati che include `Orders` e `Items`. La classe contenitore di entità `OrderItemData` dispone di due metodi pubblici che restituiscono le interfacce <xref:System.Linq.IQueryable%601>. Queste interfacce sono set di entità dei tipi di entità `Orders` e `Items`. Un'entità `Order` può includere più entità `Items`, pertanto il tipo di entità `Orders` dispone di una proprietà di navigazione `Items` che restituisce una raccolta di oggetti `Items`. La classe contenitore di entità `OrderItemData` è il tipo generico della classe <xref:System.Data.Services.DataService%601> da cui deriva il servizio dati `OrderItems`.  
  
> [!NOTE]
> Poiché in questo esempio viene illustrato un provider di dati in memoria e le modifiche non vengono rese persistenti all'esterno delle istanze degli oggetti correnti, l'implementazione dell'interfaccia <xref:System.Data.Services.IUpdatable> non produce alcun vantaggio. Per un esempio che implementa l' <xref:System.Data.Services.IUpdatable> interfaccia, vedere [procedura: Creare un servizio dati utilizzando un'origine](create-a-data-service-using-linq-to-sql-wcf.md)dati LINQ to SQL.  
  
 [!code-csharp[Astoria Reflection Provider#CustomIQueryable](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_reflection_provider/cs/orderitems.svc.cs#customiqueryable)]
 [!code-vb[Astoria Reflection Provider#CustomIQueryable](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_reflection_provider/vb/orderitems.svc.vb#customiqueryable)]  
  
## <a name="see-also"></a>Vedere anche

- [Procedura: Creazione di un servizio dati tramite un'origine dati LINQ to SQL](create-a-data-service-using-linq-to-sql-wcf.md)
- [Provider di servizi dati](data-services-providers-wcf-data-services.md)
- [Procedura: Creare un servizio dati tramite un'origine dati Entity Framework ADO.NET](create-a-data-service-using-an-adonet-ef-data-wcf.md)
