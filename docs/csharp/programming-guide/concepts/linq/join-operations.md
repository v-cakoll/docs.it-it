---
title: :::no-loc(Join):::Operazioni (C#)
description: Un join di due origini dati associa gli oggetti a oggetti che condividono un attributo tra le origini dati. Informazioni sui metodi di join nel framework LINQ in C#.
ms.date: 07/20/2015
ms.assetid: 5105e0da-1267-4c00-837a-f0e9602279b8
no-loc:
- ':::no-loc(Join):::'
- ':::no-loc(GroupJoin):::'
ms.openlocfilehash: 1b453f1752edf0cc126f8e27dbdd9e91ad9143f3
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2020
ms.locfileid: "87165688"
---
# <a name="no-locjoin-operations-c"></a><span data-ttu-id="7b5d0-104">:::no-loc(Join):::Operazioni (C#)</span><span class="sxs-lookup"><span data-stu-id="7b5d0-104">:::no-loc(Join)::: Operations (C#)</span></span>

<span data-ttu-id="7b5d0-105">Un *join* di due origini dati è un'associazione di oggetti in un'origine dati con oggetti che condividono un attributo comune in un'altra origine dati.</span><span class="sxs-lookup"><span data-stu-id="7b5d0-105">A *join* of two data sources is the association of objects in one data source with objects that share a common attribute in another data source.</span></span>  
  
 <span data-ttu-id="7b5d0-106">:::no-loc(Join):::ING è un'operazione importante nelle query che hanno come destinazione origini dati le cui relazioni reciproche non possono essere seguite direttamente.</span><span class="sxs-lookup"><span data-stu-id="7b5d0-106">:::no-loc(Join):::ing is an important operation in queries that target data sources whose relationships to each other cannot be followed directly.</span></span> <span data-ttu-id="7b5d0-107">Nella programmazione orientata a oggetti ciò potrebbe corrispondere a una correlazione non modellata tra oggetti, ad esempio la direzione inversa di una relazione unidirezionale.</span><span class="sxs-lookup"><span data-stu-id="7b5d0-107">In object-oriented programming, this could mean a correlation between objects that is not modeled, such as the backwards direction of a one-way relationship.</span></span> <span data-ttu-id="7b5d0-108">Un esempio di relazione unidirezionale è costituito da una classe Customer che include una proprietà di tipo City, ma la classe City non include una proprietà che sia una raccolta di oggetti Customer.</span><span class="sxs-lookup"><span data-stu-id="7b5d0-108">An example of a one-way relationship is a Customer class that has a property of type City, but the City class does not have a property that is a collection of Customer objects.</span></span> <span data-ttu-id="7b5d0-109">Se si ha un elenco di oggetti City e si vogliono trovare tutti i clienti in ogni città, è possibile usare un'operazione join per individuarli.</span><span class="sxs-lookup"><span data-stu-id="7b5d0-109">If you have a list of City objects and you want to find all the customers in each city, you could use a join operation to find them.</span></span>  
  
 <span data-ttu-id="7b5d0-110">I metodi di join disponibili nel framework LINQ sono <xref:System.Linq.Enumerable.:::no-loc(Join):::%2A> e <xref:System.Linq.Enumerable.:::no-loc(GroupJoin):::%2A>.</span><span class="sxs-lookup"><span data-stu-id="7b5d0-110">The join methods provided in the LINQ framework are <xref:System.Linq.Enumerable.:::no-loc(Join):::%2A> and <xref:System.Linq.Enumerable.:::no-loc(GroupJoin):::%2A>.</span></span> <span data-ttu-id="7b5d0-111">Questi metodi eseguono equijoin, ovvero join che associano due origini dati in base all'uguaglianza delle rispettive chiavi.</span><span class="sxs-lookup"><span data-stu-id="7b5d0-111">These methods perform equijoins, or joins that match two data sources based on equality of their keys.</span></span> <span data-ttu-id="7b5d0-112">Per il confronto, Transact-SQL supporta operatori join diversi da' Equals ', ad esempio l'operatore ' minore di '. In termini di database relazionale, <xref:System.Linq.Enumerable.:::no-loc(Join):::%2A> implementa un inner join, un tipo di join in cui vengono restituiti solo gli oggetti che hanno una corrispondenza nell'altro set di dati.</span><span class="sxs-lookup"><span data-stu-id="7b5d0-112">(For comparison, Transact-SQL supports join operators other than 'equals', for example the 'less than' operator.) In relational database terms, <xref:System.Linq.Enumerable.:::no-loc(Join):::%2A> implements an inner join, a type of join in which only those objects that have a match in the other data set are returned.</span></span> <span data-ttu-id="7b5d0-113">Il metodo <xref:System.Linq.Enumerable.:::no-loc(GroupJoin):::%2A> non ha equivalenti diretti in termini di database relazionale, ma implementa un superset di inner join e left outer join.</span><span class="sxs-lookup"><span data-stu-id="7b5d0-113">The <xref:System.Linq.Enumerable.:::no-loc(GroupJoin):::%2A> method has no direct equivalent in relational database terms, but it implements a superset of inner joins and left outer joins.</span></span> <span data-ttu-id="7b5d0-114">Un left outer join è un join che restituisce ogni elemento della prima origine dati (a sinistra), anche se non ha elementi correlati nell'altra origine dati.</span><span class="sxs-lookup"><span data-stu-id="7b5d0-114">A left outer join is a join that returns each element of the first (left) data source, even if it has no correlated elements in the other data source.</span></span>  
  
 <span data-ttu-id="7b5d0-115">L'illustrazione seguente mostra una visualizzazione concettuale dei due set e degli elementi dei set che sono inclusi in un inner join o in un left outer join.</span><span class="sxs-lookup"><span data-stu-id="7b5d0-115">The following illustration shows a conceptual view of two sets and the elements within those sets that are included in either an inner join or a left outer join.</span></span>  
  
 ![Due cerchi sovrapposti che illustrano interno&#47;esterno.](./media/join-operations/join-method-overlapping-circles.png)  
  
## <a name="methods"></a><span data-ttu-id="7b5d0-117">Metodi</span><span class="sxs-lookup"><span data-stu-id="7b5d0-117">Methods</span></span>  
  
|<span data-ttu-id="7b5d0-118">Nome metodo</span><span class="sxs-lookup"><span data-stu-id="7b5d0-118">Method Name</span></span>|<span data-ttu-id="7b5d0-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7b5d0-119">Description</span></span>|<span data-ttu-id="7b5d0-120">Sintassi di espressione della query C#</span><span class="sxs-lookup"><span data-stu-id="7b5d0-120">C# Query Expression Syntax</span></span>|<span data-ttu-id="7b5d0-121">Altre informazioni</span><span class="sxs-lookup"><span data-stu-id="7b5d0-121">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|:::no-loc(Join):::|<span data-ttu-id="7b5d0-122">:::no-loc(Join):::s due sequenze basate sulle funzioni del selettore principale ed estrae coppie di valori.</span><span class="sxs-lookup"><span data-stu-id="7b5d0-122">:::no-loc(Join):::s two sequences based on key selector functions and extracts pairs of values.</span></span>|`join … in … on … equals …`|<xref:System.Linq.Enumerable.:::no-loc(Join):::%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.:::no-loc(Join):::%2A?displayProperty=nameWithType>|  
|:::no-loc(GroupJoin):::|<span data-ttu-id="7b5d0-123">:::no-loc(Join):::s due sequenze basate sulle funzioni del selettore di chiave e raggruppa le corrispondenze risultanti per ogni elemento.</span><span class="sxs-lookup"><span data-stu-id="7b5d0-123">:::no-loc(Join):::s two sequences based on key selector functions and groups the resulting matches for each element.</span></span>|`join … in … on … equals … into …`|<xref:System.Linq.Enumerable.:::no-loc(GroupJoin):::%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.:::no-loc(GroupJoin):::%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-examples"></a><span data-ttu-id="7b5d0-124">Esempi di sintassi delle espressioni di query</span><span class="sxs-lookup"><span data-stu-id="7b5d0-124">Query expression syntax examples</span></span>
  
### :::no-loc(Join):::  
  
<span data-ttu-id="7b5d0-125">Nell'esempio seguente viene usata la `join … in … on … equals …` clausola per unire in join due sequenze in base a un valore specifico:</span><span class="sxs-lookup"><span data-stu-id="7b5d0-125">The following example uses the `join … in … on … equals …` clause to join two sequences based on specific value:</span></span>
  
[!code-csharp[:::no-loc(Join):::](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csLINQ:::no-loc(Join):::Operation/CS/:::no-loc(Join):::Operation.cs#:::no-loc(Join):::)]  

### :::no-loc(GroupJoin):::  

<span data-ttu-id="7b5d0-126">Nell'esempio seguente viene usata la `join … in … on … equals … into …` clausola per unire in join due sequenze in base a un valore specifico e vengono raggruppate le corrispondenze risultanti per ogni elemento:</span><span class="sxs-lookup"><span data-stu-id="7b5d0-126">The following example uses the `join … in … on … equals … into …` clause to join two sequences based on specific value and groups the resulting matches for each element:</span></span>
  
[!code-csharp[:::no-loc(GroupJoin):::](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csLINQ:::no-loc(Join):::Operation/CS/:::no-loc(Join):::Operation.cs#:::no-loc(GroupJoin):::)]  
  
## <a name="see-also"></a><span data-ttu-id="7b5d0-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7b5d0-127">See also</span></span>

- <xref:System.Linq>
- <span data-ttu-id="7b5d0-128">[Standard Query Operators Overview (C#)](./standard-query-operators-overview.md) (Panoramica degli operatori di query standard)</span><span class="sxs-lookup"><span data-stu-id="7b5d0-128">[Standard Query Operators Overview (C#)](./standard-query-operators-overview.md)</span></span>
- [<span data-ttu-id="7b5d0-129">Tipi anonimi</span><span class="sxs-lookup"><span data-stu-id="7b5d0-129">Anonymous Types</span></span>](../../classes-and-structs/anonymous-types.md)
- [<span data-ttu-id="7b5d0-130">Formulare :::no-loc(Join)::: le query e tra i prodotti</span><span class="sxs-lookup"><span data-stu-id="7b5d0-130">Formulate :::no-loc(Join):::s and Cross-Product Queries</span></span>](../../../../framework/data/adonet/sql/linq/formulate-joins-and-cross-product-queries.md)
- [<span data-ttu-id="7b5d0-131">Clausola join</span><span class="sxs-lookup"><span data-stu-id="7b5d0-131">join clause</span></span>](../../../language-reference/keywords/join-clause.md)
- [<span data-ttu-id="7b5d0-132">:::no-loc(Join):::usando chiavi composite</span><span class="sxs-lookup"><span data-stu-id="7b5d0-132">:::no-loc(Join)::: by using composite keys</span></span>](../../../linq/join-by-using-composite-keys.md)
- [<span data-ttu-id="7b5d0-133">Come unire il contenuto da file non analoghi (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="7b5d0-133">How to join content from dissimilar files (LINQ) (C#)</span></span>](./how-to-join-content-from-dissimilar-files-linq.md)
- [<span data-ttu-id="7b5d0-134">Ordinare i risultati di una clausola join</span><span class="sxs-lookup"><span data-stu-id="7b5d0-134">Order the results of a join clause</span></span>](../../../linq/order-the-results-of-a-join-clause.md)
- [<span data-ttu-id="7b5d0-135">Eseguire operazioni di join personalizzate</span><span class="sxs-lookup"><span data-stu-id="7b5d0-135">Perform custom join operations</span></span>](../../../linq/perform-custom-join-operations.md)
- [<span data-ttu-id="7b5d0-136">Eseguire join raggruppati</span><span class="sxs-lookup"><span data-stu-id="7b5d0-136">Perform grouped joins</span></span>](../../../linq/perform-grouped-joins.md)
- [<span data-ttu-id="7b5d0-137">Eseguire inner join</span><span class="sxs-lookup"><span data-stu-id="7b5d0-137">Perform inner joins</span></span>](../../../linq/perform-inner-joins.md)
- [<span data-ttu-id="7b5d0-138">Eseguire left outer join</span><span class="sxs-lookup"><span data-stu-id="7b5d0-138">Perform left outer joins</span></span>](../../../linq/perform-left-outer-joins.md)
- [<span data-ttu-id="7b5d0-139">Come popolare le raccolte di oggetti da più origini (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="7b5d0-139">How to populate object collections from multiple sources (LINQ) (C#)</span></span>](./how-to-populate-object-collections-from-multiple-sources-linq.md)
