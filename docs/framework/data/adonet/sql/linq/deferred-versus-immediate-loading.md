---
title: Caricamento posticipato e immediato
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: d1d7247f-a3b7-460b-b342-5c1a2365aa1a
caps.latest.revision: 
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: 8a4fa1574b8e25a5d98f9547ad916a3c84f10b01
ms.sourcegitcommit: cf22b29db780e532e1090c6e755aa52d28273fa6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/01/2018
---
# <a name="deferred-versus-immediate-loading"></a><span data-ttu-id="c6c3b-102">Caricamento posticipato e immediato</span><span class="sxs-lookup"><span data-stu-id="c6c3b-102">Deferred versus Immediate Loading</span></span>
<span data-ttu-id="c6c3b-103">Quando si esegue una query per un oggetto, si recupera in effetti solo l'oggetto richiesto.</span><span class="sxs-lookup"><span data-stu-id="c6c3b-103">When you query for an object, you actually retrieve only the object you requested.</span></span> <span data-ttu-id="c6c3b-104">Il *correlati* oggetti non vengono recuperati contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="c6c3b-104">The *related* objects are not automatically fetched at the same time.</span></span> <span data-ttu-id="c6c3b-105">(Per ulteriori informazioni, vedere [l'esecuzione di query tra relazioni](../../../../../../docs/framework/data/adonet/sql/linq/querying-across-relationships.md).) Non è possibile verificare che gli oggetti correlati non siano già stati caricati, perché un tentativo di accedervi produce una richiesta che ne comporta il recupero.</span><span class="sxs-lookup"><span data-stu-id="c6c3b-105">(For more information, see [Querying Across Relationships](../../../../../../docs/framework/data/adonet/sql/linq/querying-across-relationships.md).) You cannot see the fact that the related objects are not already loaded, because an attempt to access them produces a request that retrieves them.</span></span>  
  
 <span data-ttu-id="c6c3b-106">Potrebbe ad esempio, si desidera eseguire una query per un particolare set di ordini e quindi inviare saltuariamente una notifica tramite posta elettronica a clienti particolari.</span><span class="sxs-lookup"><span data-stu-id="c6c3b-106">For example, you might want to query for a particular set of orders and then only occasionally send an email notification to particular customers.</span></span> <span data-ttu-id="c6c3b-107">Inizialmente potrebbe non essere necessario recuperare tutti i dati del cliente con ogni ordine.</span><span class="sxs-lookup"><span data-stu-id="c6c3b-107">You would not necessarily need initially to retrieve all customer data with every order.</span></span> <span data-ttu-id="c6c3b-108">In questo caso è possibile usare il caricamento posticipato per rinviare il recupero di informazioni aggiuntive finché non sarà assolutamente necessario.</span><span class="sxs-lookup"><span data-stu-id="c6c3b-108">You can use deferred loading to defer retrieval of extra information until you absolutely have to.</span></span> <span data-ttu-id="c6c3b-109">Si consideri l'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="c6c3b-109">Consider the following example:</span></span>  
  
 [!code-csharp[DLinqQueryConcepts#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#1)]
 [!code-vb[DLinqQueryConcepts#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#1)]  
  
 <span data-ttu-id="c6c3b-110">Potrebbe anche essere vero il contrario.</span><span class="sxs-lookup"><span data-stu-id="c6c3b-110">The opposite might also be true.</span></span> <span data-ttu-id="c6c3b-111">Si dispone di un'applicazione che richiede la visualizzazione contemporanea dei dati dei clienti e degli ordini.</span><span class="sxs-lookup"><span data-stu-id="c6c3b-111">You might have an application that has to view customer and order data at the same time.</span></span> <span data-ttu-id="c6c3b-112">È noto che sono necessari entrambi i set di dati</span><span class="sxs-lookup"><span data-stu-id="c6c3b-112">You know you need both sets of data.</span></span> <span data-ttu-id="c6c3b-113">e che l'applicazione richiede informazioni sugli ordini per ogni cliente non appena vengono restituiti i risultati.</span><span class="sxs-lookup"><span data-stu-id="c6c3b-113">You know your application needs order information for each customer as soon as you get the results.</span></span> <span data-ttu-id="c6c3b-114">Non si desidera inviare singole query per gli ordini di ogni cliente,</span><span class="sxs-lookup"><span data-stu-id="c6c3b-114">You would not want to submit individual queries for orders for every customer.</span></span> <span data-ttu-id="c6c3b-115">bensì recuperare i dati degli ordini insieme ai clienti.</span><span class="sxs-lookup"><span data-stu-id="c6c3b-115">What you really want is to retrieve the order data together with the customers.</span></span>  
  
 [!code-csharp[DLinqQueryConcepts#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#2)]
 [!code-vb[DLinqQueryConcepts#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#2)]  
  
 <span data-ttu-id="c6c3b-116">È inoltre possibile creare un join tra clienti e ordini in una query definendo il prodotto incrociato e recuperando tutti i relativi bit di dati come un'unica grande proiezione.</span><span class="sxs-lookup"><span data-stu-id="c6c3b-116">You can also join customers and orders in a query by forming the cross-product and retrieving all the relative bits of data as one large projection.</span></span> <span data-ttu-id="c6c3b-117">Tali risultati non sono tuttavia entità.</span><span class="sxs-lookup"><span data-stu-id="c6c3b-117">But these results are not entities.</span></span> <span data-ttu-id="c6c3b-118">(Per ulteriori informazioni, vedere [LINQ al modello a oggetti SQL](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)).</span><span class="sxs-lookup"><span data-stu-id="c6c3b-118">(For more information, see [The LINQ to SQL Object Model](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)).</span></span> <span data-ttu-id="c6c3b-119">Le entità sono oggetti con un'identità che è possibile modificare, mentre i risultati in questione sono proiezioni che non possono essere modificate né salvate in modo permanente.</span><span class="sxs-lookup"><span data-stu-id="c6c3b-119">Entities are objects that have identity and that you can modify, whereas these results would be projections that cannot be changed and persisted.</span></span> <span data-ttu-id="c6c3b-120">È inoltre possibile che vengano recuperati molti dati ridondanti, in quanto ogni cliente viene ripetuto per ogni ordine nell'output del join bidimensionale.</span><span class="sxs-lookup"><span data-stu-id="c6c3b-120">Even worse, you would be retrieving lots of redundant data as each customer repeats for each order in the flattened join output.</span></span>  
  
 <span data-ttu-id="c6c3b-121">È invece utile disporre di un modo per recuperare contemporaneamente un set di oggetti correlati.</span><span class="sxs-lookup"><span data-stu-id="c6c3b-121">What you really need is a way to retrieve a set of related objects at the same time.</span></span> <span data-ttu-id="c6c3b-122">Il set è una sezione delineata di un grafico che consente di recuperare sempre solo la quantità di dati necessaria per l'uso desiderato.</span><span class="sxs-lookup"><span data-stu-id="c6c3b-122">The set is a delineated section of a graph so that you would never be retrieving more or less than was necessary for your intended use.</span></span> <span data-ttu-id="c6c3b-123">A tale scopo, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] fornisce <xref:System.Data.Linq.DataLoadOptions> per il caricamento immediato di un'area del modello a oggetti.</span><span class="sxs-lookup"><span data-stu-id="c6c3b-123">For this purpose, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] provides <xref:System.Data.Linq.DataLoadOptions> for immediate loading of a region of your object model.</span></span> <span data-ttu-id="c6c3b-124">I metodi comprendono:</span><span class="sxs-lookup"><span data-stu-id="c6c3b-124">Methods include:</span></span>  
  
-   <span data-ttu-id="c6c3b-125">Il metodo <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A> per caricare immediatamente dati relativi alla destinazione principale.</span><span class="sxs-lookup"><span data-stu-id="c6c3b-125">The  <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A> method, to immediately load data related to the main target.</span></span>  
  
-   <span data-ttu-id="c6c3b-126">Il metodo <xref:System.Data.Linq.DataLoadOptions.AssociateWith%2A> per filtrare gli oggetti recuperati per una determinata relazione.</span><span class="sxs-lookup"><span data-stu-id="c6c3b-126">The <xref:System.Data.Linq.DataLoadOptions.AssociateWith%2A> method, to filter objects retrieved for a particular relationship.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6c3b-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c6c3b-127">See Also</span></span>  
 [<span data-ttu-id="c6c3b-128">Concetti relativi alle query</span><span class="sxs-lookup"><span data-stu-id="c6c3b-128">Query Concepts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)
