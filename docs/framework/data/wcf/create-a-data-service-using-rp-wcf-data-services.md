---
title: 'Procedura: Creare un servizio dati tramite il Provider di Reflection (WCF Data Services)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, providers
ms.assetid: 7315c6d8-f452-4fb2-a0c1-76ab0593c146
ms.openlocfilehash: 233b17de17b7f50547b2f4fbf6a543d7258183cf
ms.sourcegitcommit: 680a741667cf6859de71586a0caf6be14f4f7793
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/12/2019
ms.locfileid: "59517096"
---
# <a name="how-to-create-a-data-service-using-the-reflection-provider-wcf-data-services"></a><span data-ttu-id="49669-102">Procedura: Creare un servizio dati tramite il Provider di Reflection (WCF Data Services)</span><span class="sxs-lookup"><span data-stu-id="49669-102">How to: Create a Data Service Using the Reflection Provider (WCF Data Services)</span></span>
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] <span data-ttu-id="49669-103">consente di definire un modello di dati basato su classi arbitrarie, purché tali classi siano esposte come oggetti che implementano l'interfaccia <xref:System.Linq.IQueryable%601>.</span><span class="sxs-lookup"><span data-stu-id="49669-103">enables you to define a data model that is based on arbitrary classes as long as those classes are exposed as objects that implement the <xref:System.Linq.IQueryable%601> interface.</span></span> <span data-ttu-id="49669-104">Per altre informazioni, vedere [provider di servizi dati](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="49669-104">For more information, see [Data Services Providers](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="49669-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="49669-105">Example</span></span>  
 <span data-ttu-id="49669-106">Nell'esempio seguente viene definito un modello di dati che include `Orders` e `Items`.</span><span class="sxs-lookup"><span data-stu-id="49669-106">The following example defines a data model that includes `Orders` and `Items`.</span></span> <span data-ttu-id="49669-107">La classe contenitore di entità `OrderItemData` dispone di due metodi pubblici che restituiscono le interfacce <xref:System.Linq.IQueryable%601>.</span><span class="sxs-lookup"><span data-stu-id="49669-107">The entity container class `OrderItemData` has two public methods that return <xref:System.Linq.IQueryable%601> interfaces.</span></span> <span data-ttu-id="49669-108">Queste interfacce sono set di entità dei tipi di entità `Orders` e `Items`.</span><span class="sxs-lookup"><span data-stu-id="49669-108">These interfaces are the entity sets of the `Orders` and `Items` entity types.</span></span> <span data-ttu-id="49669-109">Un'entità `Order` può includere più entità `Items`, pertanto il tipo di entità `Orders` dispone di una proprietà di navigazione `Items` che restituisce una raccolta di oggetti `Items`.</span><span class="sxs-lookup"><span data-stu-id="49669-109">An `Order` can include multiple `Items`, so the `Orders` entity type has an `Items` navigation property that returns a collection of `Items` objects.</span></span> <span data-ttu-id="49669-110">La classe contenitore di entità `OrderItemData` è il tipo generico della classe <xref:System.Data.Services.DataService%601> da cui deriva il servizio dati `OrderItems`.</span><span class="sxs-lookup"><span data-stu-id="49669-110">The `OrderItemData` entity container class is the generic type of the <xref:System.Data.Services.DataService%601> class from which the `OrderItems` data service is derived.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="49669-111">Poiché in questo esempio viene illustrato un provider di dati in memoria e le modifiche non vengono rese persistenti all'esterno delle istanze degli oggetti correnti, l'implementazione dell'interfaccia <xref:System.Data.Services.IUpdatable> non produce alcun vantaggio.</span><span class="sxs-lookup"><span data-stu-id="49669-111">Because this example demonstrates an in-memory data provider and changes are not persisted outside of the current object instances, there is no benefit derived from implementing the <xref:System.Data.Services.IUpdatable> interface.</span></span> <span data-ttu-id="49669-112">Per un esempio che implementa il <xref:System.Data.Services.IUpdatable> dell'interfaccia, vedere [come: Creare un servizio dati usando un LINQ all'origine dati SQL](../../../../docs/framework/data/wcf/create-a-data-service-using-linq-to-sql-wcf.md).</span><span class="sxs-lookup"><span data-stu-id="49669-112">For an example that implements the <xref:System.Data.Services.IUpdatable> interface, see [How to: Create a Data Service Using a LINQ to SQL Data Source](../../../../docs/framework/data/wcf/create-a-data-service-using-linq-to-sql-wcf.md).</span></span>  
  
 [!code-csharp[Astoria Reflection Provider#CustomIQueryable](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_reflection_provider/cs/orderitems.svc.cs#customiqueryable)]
 [!code-vb[Astoria Reflection Provider#CustomIQueryable](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_reflection_provider/vb/orderitems.svc.vb#customiqueryable)]  
  
## <a name="see-also"></a><span data-ttu-id="49669-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="49669-113">See also</span></span>

- [<span data-ttu-id="49669-114">Procedura: Creare un servizio dati usando un LINQ all'origine dati SQL</span><span class="sxs-lookup"><span data-stu-id="49669-114">How to: Create a Data Service Using a LINQ to SQL Data Source</span></span>](../../../../docs/framework/data/wcf/create-a-data-service-using-linq-to-sql-wcf.md)
- [<span data-ttu-id="49669-115">Provider di servizi dati</span><span class="sxs-lookup"><span data-stu-id="49669-115">Data Services Providers</span></span>](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md)
- [<span data-ttu-id="49669-116">Procedura: Creare un servizio dati tramite un'origine dati ADO.NET Entity Framework</span><span class="sxs-lookup"><span data-stu-id="49669-116">How to: Create a Data Service Using an ADO.NET Entity Framework Data Source</span></span>](../../../../docs/framework/data/wcf/create-a-data-service-using-an-adonet-ef-data-wcf.md)
