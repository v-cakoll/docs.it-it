---
title: Risultati delle query
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: bcd7b699-4e50-4523-8c33-2f54a103d94e
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 32133d1b6fce619fb9990ab89820b7f19b6a5926
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="query-results"></a><span data-ttu-id="bcb05-102">Risultati delle query</span><span class="sxs-lookup"><span data-stu-id="bcb05-102">Query Results</span></span>
<span data-ttu-id="bcb05-103">Dopo che una query [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] è stata convertita in un albero dei comandi ed eseguita, i risultati della query vengono in genere restituiti in una delle forme seguenti:</span><span class="sxs-lookup"><span data-stu-id="bcb05-103">After a [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] query is converted to command trees and executed, the query results are usually returned as one of the following:</span></span>  
  
-   <span data-ttu-id="bcb05-104">Raccolta di zero o più oggetti entità tipizzate o proiezione di tipi complessi nel modello concettuale.</span><span class="sxs-lookup"><span data-stu-id="bcb05-104">A collection of zero or more typed entity objects or a projection of complex types in the conceptual model.</span></span>  
  
-   <span data-ttu-id="bcb05-105">Tipi CLR supportati dal modello concettuale.</span><span class="sxs-lookup"><span data-stu-id="bcb05-105">CLR types supported by the conceptual model.</span></span>  
  
-   <span data-ttu-id="bcb05-106">Raccolte inline.</span><span class="sxs-lookup"><span data-stu-id="bcb05-106">Inline collections.</span></span>  
  
-   <span data-ttu-id="bcb05-107">Tipi anonimi.</span><span class="sxs-lookup"><span data-stu-id="bcb05-107">Anonymous types.</span></span>  
  
 <span data-ttu-id="bcb05-108">Una volta eseguita la query sull'origine dati, i risultati vengono materializzati in tipi CLR e restituiti al client.</span><span class="sxs-lookup"><span data-stu-id="bcb05-108">When the query has executed against the data source, the results are materialized into CLR types and returned to the client.</span></span> <span data-ttu-id="bcb05-109">La materializzazione degli oggetti viene eseguita da [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bcb05-109">All object materialization is performed by the [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)].</span></span> <span data-ttu-id="bcb05-110">Qualsiasi errore dovuto all'impossibilità di eseguire il mapping tra [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] e CLR comporta la generazione di eccezioni durante la materializzazione degli oggetti.</span><span class="sxs-lookup"><span data-stu-id="bcb05-110">Any errors that result from an inability to map between the [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] and the CLR will cause exceptions to be thrown during object materialization.</span></span>  
  
 <span data-ttu-id="bcb05-111">Se l'esecuzione di una query restituisce tipi primitivi del modello concettuale, i risultati sono costituiti da tipi CLR autonomi e disconnessi da [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bcb05-111">If the query execution returns primitive conceptual model types, the results consist of CLR types that are stand-alone and disconnected from the [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)].</span></span> <span data-ttu-id="bcb05-112">Se tuttavia la query restituisce una raccolta di oggetti entità tipizzati, rappresentati da <xref:System.Data.Objects.ObjectQuery%601>, questi tipi vengono registrati dal contesto dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="bcb05-112">However, if the query returns a collection of typed entity objects, represented by <xref:System.Data.Objects.ObjectQuery%601>, those types are tracked by the object context.</span></span> <span data-ttu-id="bcb05-113">Tutti i comportamenti degli oggetti (ad esempio raccolte figlio/padre, rilevamento delle modifiche, polimorfismo e così via) sono definiti nel [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bcb05-113">All object behavior (such as child/parent collections, change tracking, polymorphism, and so on) are as defined in the [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)].</span></span> <span data-ttu-id="bcb05-114">Questa funzionalità può essere utilizzata come definito in [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bcb05-114">This functionality can be used in its capacity, as defined in the [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)].</span></span> <span data-ttu-id="bcb05-115">Per ulteriori informazioni, vedere [lavora con gli oggetti](../../../../../../docs/framework/data/adonet/ef/working-with-objects.md).</span><span class="sxs-lookup"><span data-stu-id="bcb05-115">For more information, see [Working with Objects](../../../../../../docs/framework/data/adonet/ef/working-with-objects.md).</span></span>  
  
 <span data-ttu-id="bcb05-116">I tipi di struct restituiti dalle query (ad esempio tipi anonimi e tipi complessi che ammettono i valori Null) possono avere valore `null`.</span><span class="sxs-lookup"><span data-stu-id="bcb05-116">Struct types returned from queries (such as anonymous types and nullable complex types) can be of `null` value.</span></span> <span data-ttu-id="bcb05-117">Anche una proprietà <xref:System.Data.Objects.DataClasses.EntityCollection%601> di un'entità restituita può avere valore `null`.</span><span class="sxs-lookup"><span data-stu-id="bcb05-117">An <xref:System.Data.Objects.DataClasses.EntityCollection%601> property of a returned entity can also be of `null` value.</span></span> <span data-ttu-id="bcb05-118">Questo può essere dovuto alla proiezione della proprietà della raccolta di un'entità con valore `null`, ad esempio la chiamata a <xref:System.Linq.Queryable.FirstOrDefault%2A> su un oggetto <xref:System.Data.Objects.ObjectQuery%601> che non dispone di elementi.</span><span class="sxs-lookup"><span data-stu-id="bcb05-118">This can result from projecting the collection property of an entity that is of `null` value, such as calling <xref:System.Linq.Queryable.FirstOrDefault%2A> on an <xref:System.Data.Objects.ObjectQuery%601> that has no elements.</span></span>  
  
 <span data-ttu-id="bcb05-119">In alcune situazioni, potrebbe sembrare che una query generi un risultato materializzato durante la sua esecuzione, ma la query viene eseguita nel server e l'oggetto entità non viene mai materializzato in CLR.</span><span class="sxs-lookup"><span data-stu-id="bcb05-119">In certain situations, a query might appear to generate a materialized result during its execution, but the query will be executed on the server and the entity object will never be materialized in the CLR.</span></span> <span data-ttu-id="bcb05-120">Questo può provocare problemi se si è legati agli effetti collaterali della materializzazione degli oggetti.</span><span class="sxs-lookup"><span data-stu-id="bcb05-120">This can cause problems if you are depending on side effects of object materialization.</span></span>  
  
 <span data-ttu-id="bcb05-121">L'esempio seguente contiene una classe personalizzata, `MyContact`, con una proprietà `LastName`.</span><span class="sxs-lookup"><span data-stu-id="bcb05-121">The following example contains a custom class, `MyContact`, with a `LastName` property.</span></span> <span data-ttu-id="bcb05-122">Quando viene impostata la proprietà `LastName`, viene incrementata una variabile `count`.</span><span class="sxs-lookup"><span data-stu-id="bcb05-122">When the `LastName` property is set, a `count` variable is incremented.</span></span> <span data-ttu-id="bcb05-123">Se si eseguono le due query seguenti, tramite la prima query viene incrementata la variabile  `count`, mentre tramite la seconda query no.</span><span class="sxs-lookup"><span data-stu-id="bcb05-123">If you execute the two following queries, the first query will increment `count` while the second query will not.</span></span> <span data-ttu-id="bcb05-124">Questo avviene in quanto nella seconda query la proprietà `LastName` è proiettata dai risultati e la classe `MyContact` non viene mai creata, perché non è necessaria per eseguire la query sull'archivio.</span><span class="sxs-lookup"><span data-stu-id="bcb05-124">This is because in the second query the `LastName` property is projected from the results and the `MyContact` class is never created, because it is not required to execute the query on the store.</span></span>  
  
 [!code-csharp[DP L2E Materialization Example#MaterializationSideEffects](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Materialization Example/CS/Program.cs#materializationsideeffects)]
 [!code-vb[DP L2E Materialization Example#MaterializationSideEffects](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Materialization Example/VB/Module1.vb#materializationsideeffects)]  
  
 [!code-csharp[DP L2E Materialization Example#MyContactClass](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Materialization Example/CS/Program.cs#mycontactclass)]
 [!code-vb[DP L2E Materialization Example#MyContactClass](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Materialization Example/VB/Module1.vb#mycontactclass)]
