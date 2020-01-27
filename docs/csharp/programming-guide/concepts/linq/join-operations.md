---
title: Operazioni di JoinC#()
ms.date: 07/20/2015
ms.assetid: 5105e0da-1267-4c00-837a-f0e9602279b8
no-loc:
- Join
- GroupJoin
ms.openlocfilehash: d4bf9fe76238d8824c5255df8910c1000503dcdf
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746963"
---
# <a name="opno-locjoin-operations-c"></a><span data-ttu-id="8869f-102">Operazioni di JoinC#()</span><span class="sxs-lookup"><span data-stu-id="8869f-102">Join Operations (C#)</span></span>
<span data-ttu-id="8869f-103">Un *join* di due origini dati è un'associazione di oggetti in un'origine dati con oggetti che condividono un attributo comune in un'altra origine dati.</span><span class="sxs-lookup"><span data-stu-id="8869f-103">A *join* of two data sources is the association of objects in one data source with objects that share a common attribute in another data source.</span></span>  
  
 <span data-ttu-id="8869f-104">La creazione di un join è un'operazione importante nelle query che fanno riferimento a origini dati le cui relazioni reciproche non possono essere seguite direttamente.</span><span class="sxs-lookup"><span data-stu-id="8869f-104">Joining is an important operation in queries that target data sources whose relationships to each other cannot be followed directly.</span></span> <span data-ttu-id="8869f-105">Nella programmazione orientata a oggetti ciò potrebbe corrispondere a una correlazione non modellata tra oggetti, ad esempio la direzione inversa di una relazione unidirezionale.</span><span class="sxs-lookup"><span data-stu-id="8869f-105">In object-oriented programming, this could mean a correlation between objects that is not modeled, such as the backwards direction of a one-way relationship.</span></span> <span data-ttu-id="8869f-106">Un esempio di relazione unidirezionale è costituito da una classe Customer che include una proprietà di tipo City, ma la classe City non include una proprietà che sia una raccolta di oggetti Customer.</span><span class="sxs-lookup"><span data-stu-id="8869f-106">An example of a one-way relationship is a Customer class that has a property of type City, but the City class does not have a property that is a collection of Customer objects.</span></span> <span data-ttu-id="8869f-107">Se si ha un elenco di oggetti City e si vogliono trovare tutti i clienti in ogni città, è possibile usare un'operazione join per individuarli.</span><span class="sxs-lookup"><span data-stu-id="8869f-107">If you have a list of City objects and you want to find all the customers in each city, you could use a join operation to find them.</span></span>  
  
 <span data-ttu-id="8869f-108">I metodi di join disponibili nel framework LINQ sono <xref:System.Linq.Enumerable.Join%2A> e <xref:System.Linq.Enumerable.GroupJoin%2A>.</span><span class="sxs-lookup"><span data-stu-id="8869f-108">The join methods provided in the LINQ framework are <xref:System.Linq.Enumerable.Join%2A> and <xref:System.Linq.Enumerable.GroupJoin%2A>.</span></span> <span data-ttu-id="8869f-109">Questi metodi eseguono equijoin, ovvero join che associano due origini dati in base all'uguaglianza delle rispettive chiavi.</span><span class="sxs-lookup"><span data-stu-id="8869f-109">These methods perform equijoins, or joins that match two data sources based on equality of their keys.</span></span> <span data-ttu-id="8869f-110">Per il confronto, Transact-SQL supporta operatori join diversi da' Equals ', ad esempio l'operatore ' minore di '. In termini di database relazionale, <xref:System.Linq.Enumerable.Join%2A> implementa un inner join, ovvero un tipo di join in cui vengono restituiti solo gli oggetti che hanno una corrispondenza nell'altro set di dati.</span><span class="sxs-lookup"><span data-stu-id="8869f-110">(For comparison, Transact-SQL supports join operators other than 'equals', for example the 'less than' operator.) In relational database terms, <xref:System.Linq.Enumerable.Join%2A> implements an inner join, a type of join in which only those objects that have a match in the other data set are returned.</span></span> <span data-ttu-id="8869f-111">Il metodo <xref:System.Linq.Enumerable.GroupJoin%2A> non ha equivalenti diretti in termini di database relazionale, ma implementa un superset di inner join e left outer join.</span><span class="sxs-lookup"><span data-stu-id="8869f-111">The <xref:System.Linq.Enumerable.GroupJoin%2A> method has no direct equivalent in relational database terms, but it implements a superset of inner joins and left outer joins.</span></span> <span data-ttu-id="8869f-112">Un left outer join è un join che restituisce ogni elemento della prima origine dati (a sinistra), anche se non ha elementi correlati nell'altra origine dati.</span><span class="sxs-lookup"><span data-stu-id="8869f-112">A left outer join is a join that returns each element of the first (left) data source, even if it has no correlated elements in the other data source.</span></span>  
  
 <span data-ttu-id="8869f-113">L'illustrazione seguente mostra una visualizzazione concettuale dei due set e degli elementi dei set che sono inclusi in un inner join o in un left outer join.</span><span class="sxs-lookup"><span data-stu-id="8869f-113">The following illustration shows a conceptual view of two sets and the elements within those sets that are included in either an inner join or a left outer join.</span></span>  
  
 ![Due cerchi sovrapposti che illustrano interno&#47;esterno.](./media/join-operations/join-method-overlapping-circles.png)  
  
## <a name="methods"></a><span data-ttu-id="8869f-115">Metodi</span><span class="sxs-lookup"><span data-stu-id="8869f-115">Methods</span></span>  
  
|<span data-ttu-id="8869f-116">Nome metodo</span><span class="sxs-lookup"><span data-stu-id="8869f-116">Method Name</span></span>|<span data-ttu-id="8869f-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8869f-117">Description</span></span>|<span data-ttu-id="8869f-118">Sintassi di espressione della query C#</span><span class="sxs-lookup"><span data-stu-id="8869f-118">C# Query Expression Syntax</span></span>|<span data-ttu-id="8869f-119">Altre informazioni</span><span class="sxs-lookup"><span data-stu-id="8869f-119">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|Join|<span data-ttu-id="8869f-120">Unisce due sequenze in base a funzioni selector chiave ed estrae coppie di valori</span><span class="sxs-lookup"><span data-stu-id="8869f-120">Joins two sequences based on key selector functions and extracts pairs of values.</span></span>|`join … in … on … equals …`|<xref:System.Linq.Enumerable.Join%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Join%2A?displayProperty=nameWithType>|  
|GroupJoin|<span data-ttu-id="8869f-121">Unisce due sequenze in base a funzioni selector chiave e raggruppa le corrispondenze risultanti per ogni elemento.</span><span class="sxs-lookup"><span data-stu-id="8869f-121">Joins two sequences based on key selector functions and groups the resulting matches for each element.</span></span>|`join … in … on … equals … into …`|<xref:System.Linq.Enumerable.GroupJoin%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.GroupJoin%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-examples"></a><span data-ttu-id="8869f-122">Esempi di sintassi delle espressioni di query</span><span class="sxs-lookup"><span data-stu-id="8869f-122">Query expression syntax examples</span></span>
  
### Join  
  
<span data-ttu-id="8869f-123">Nell'esempio seguente viene usata la clausola `join … in … on … equals …` per unire due sequenze in base a un valore specifico:</span><span class="sxs-lookup"><span data-stu-id="8869f-123">The following example uses the `join … in … on … equals …` clause to join two sequences based on specific value:</span></span>
  
[!code-csharp[Join](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQJoin/CS/JoinOperation.cs#Join)]  

### GroupJoin  

<span data-ttu-id="8869f-124">Nell'esempio seguente viene utilizzata la clausola `join … in … on … equals … into …` per unire due sequenze in base a un valore specifico e vengono raggruppate le corrispondenze risultanti per ogni elemento:</span><span class="sxs-lookup"><span data-stu-id="8869f-124">The following example uses the `join … in … on … equals … into …` clause to join two sequences based on specific value and groups the resulting matches for each element:</span></span>
  
[!code-csharp[GroupJoin](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQJoin/CS/JoinOperation.cs#GroupJoin)]  
  
## <a name="see-also"></a><span data-ttu-id="8869f-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8869f-125">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="8869f-126">Panoramica degli operatori di query standard (C#)</span><span class="sxs-lookup"><span data-stu-id="8869f-126">Standard Query Operators Overview (C#)</span></span>](./standard-query-operators-overview.md)
- [<span data-ttu-id="8869f-127">Tipi anonimi</span><span class="sxs-lookup"><span data-stu-id="8869f-127">Anonymous Types</span></span>](../../classes-and-structs/anonymous-types.md)
- [<span data-ttu-id="8869f-128">Formulare join e query di prodotto incrociato</span><span class="sxs-lookup"><span data-stu-id="8869f-128">Formulate Joins and Cross-Product Queries</span></span>](../../../../framework/data/adonet/sql/linq/formulate-joins-and-cross-product-queries.md)
- [<span data-ttu-id="8869f-129">Clausola join</span><span class="sxs-lookup"><span data-stu-id="8869f-129">join clause</span></span>](../../../language-reference/keywords/join-clause.md)
- <span data-ttu-id="8869f-130">[Join usando chiavi composite](../../../linq/join-by-using-composite-keys.md)</span><span class="sxs-lookup"><span data-stu-id="8869f-130">[Join by using composite keys](../../../linq/join-by-using-composite-keys.md)</span></span>
- [<span data-ttu-id="8869f-131">Come unire il contenuto da file non analoghi (LINQ)C#()</span><span class="sxs-lookup"><span data-stu-id="8869f-131">How to join content from dissimilar files (LINQ) (C#)</span></span>](./how-to-join-content-from-dissimilar-files-linq.md)
- [<span data-ttu-id="8869f-132">Ordinare i risultati di una clausola join</span><span class="sxs-lookup"><span data-stu-id="8869f-132">Order the results of a join clause</span></span>](../../../linq/order-the-results-of-a-join-clause.md)
- [<span data-ttu-id="8869f-133">Eseguire operazioni di join personalizzate</span><span class="sxs-lookup"><span data-stu-id="8869f-133">Perform custom join operations</span></span>](../../../linq/perform-custom-join-operations.md)
- [<span data-ttu-id="8869f-134">Eseguire join raggruppati</span><span class="sxs-lookup"><span data-stu-id="8869f-134">Perform grouped joins</span></span>](../../../linq/perform-grouped-joins.md)
- [<span data-ttu-id="8869f-135">Eseguire inner join</span><span class="sxs-lookup"><span data-stu-id="8869f-135">Perform inner joins</span></span>](../../../linq/perform-inner-joins.md)
- [<span data-ttu-id="8869f-136">Eseguire left outer join</span><span class="sxs-lookup"><span data-stu-id="8869f-136">Perform left outer joins</span></span>](../../../linq/perform-left-outer-joins.md)
- [<span data-ttu-id="8869f-137">Come popolare le raccolte di oggetti da più origini (LINQ)C#()</span><span class="sxs-lookup"><span data-stu-id="8869f-137">How to populate object collections from multiple sources (LINQ) (C#)</span></span>](./how-to-populate-object-collections-from-multiple-sources-linq.md)
