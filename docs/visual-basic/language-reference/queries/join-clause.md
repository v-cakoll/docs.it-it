---
title: Clausola Join (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryJoinIn
- vb.QueryJoin
- vb.QueryJoinOn
helpviewer_keywords:
- queries [Visual Basic], Join
- Join statement [Visual Basic]
- Join clause [Visual Basic]
ms.assetid: 6dd37936-b27c-4e00-98ad-154b23f4de64
ms.openlocfilehash: b1551583079c66d1bf5f6963a42d5d24e518fff3
ms.sourcegitcommit: ba5c189bf44d44204a3e8838e59ec378a62d82f3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/13/2018
ms.locfileid: "44778435"
---
# <a name="join-clause-visual-basic"></a><span data-ttu-id="84297-102">Clausola Join (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="84297-102">Join Clause (Visual Basic)</span></span>
<span data-ttu-id="84297-103">Combina due raccolte in un'unica raccolta.</span><span class="sxs-lookup"><span data-stu-id="84297-103">Combines two collections into a single collection.</span></span> <span data-ttu-id="84297-104">L'operazione di join è basata su chiavi corrispondenti e viene utilizzato il `Equals` operatore.</span><span class="sxs-lookup"><span data-stu-id="84297-104">The join operation is based on matching keys and uses the `Equals` operator.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84297-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="84297-105">Syntax</span></span>  
  
```  
Join element In collection _  
  [ joinClause _ ]   
  [ groupJoinClause ... _ ]   
On key1 Equals key2 [ And key3 Equals key4 [... ]  
```  
  
## <a name="parts"></a><span data-ttu-id="84297-106">Parti</span><span class="sxs-lookup"><span data-stu-id="84297-106">Parts</span></span>  
 `element`  
 <span data-ttu-id="84297-107">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="84297-107">Required.</span></span> <span data-ttu-id="84297-108">La variabile di controllo per la raccolta da unire in join.</span><span class="sxs-lookup"><span data-stu-id="84297-108">The control variable for the collection being joined.</span></span>  
  
 `collection`  
 <span data-ttu-id="84297-109">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="84297-109">Required.</span></span> <span data-ttu-id="84297-110">La raccolta da combinare con l'insieme è identificato nel lato sinistro del `Join` operatore.</span><span class="sxs-lookup"><span data-stu-id="84297-110">The collection to combine with the collection identified on the left side of the `Join` operator.</span></span> <span data-ttu-id="84297-111">Oggetto `Join` clausola può essere annidata in un'altra `Join` clausola, o in un `Group Join` clausola.</span><span class="sxs-lookup"><span data-stu-id="84297-111">A `Join` clause can be nested in another `Join` clause, or in a `Group Join` clause.</span></span>  
  
 `joinClause`  
 <span data-ttu-id="84297-112">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="84297-112">Optional.</span></span> <span data-ttu-id="84297-113">Uno o più altre `Join` clausole per perfezionare la query.</span><span class="sxs-lookup"><span data-stu-id="84297-113">One or more additional `Join` clauses to further refine the query.</span></span>  
  
 `groupJoinClause`  
 <span data-ttu-id="84297-114">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="84297-114">Optional.</span></span> <span data-ttu-id="84297-115">Uno o più altre `Group Join` clausole per perfezionare la query.</span><span class="sxs-lookup"><span data-stu-id="84297-115">One or more additional `Group Join` clauses to further refine the query.</span></span>  
  
 <span data-ttu-id="84297-116">`key1` `Equals` `key2`</span><span class="sxs-lookup"><span data-stu-id="84297-116">`key1` `Equals` `key2`</span></span>  
 <span data-ttu-id="84297-117">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="84297-117">Required.</span></span> <span data-ttu-id="84297-118">Identifica le chiavi per le raccolte da unire in join.</span><span class="sxs-lookup"><span data-stu-id="84297-118">Identifies keys for the collections being joined.</span></span> <span data-ttu-id="84297-119">È necessario usare il `Equals` operatore per confrontare le chiavi delle raccolte da unire in join.</span><span class="sxs-lookup"><span data-stu-id="84297-119">You must use the `Equals` operator to compare keys from the collections being joined.</span></span> <span data-ttu-id="84297-120">È possibile combinare le condizioni di join tramite il `And` operatore per identificare più chiavi.</span><span class="sxs-lookup"><span data-stu-id="84297-120">You can combine join conditions by using the `And` operator to identify multiple keys.</span></span> <span data-ttu-id="84297-121">`key1` deve essere compresa tra la raccolta sul lato sinistro del `Join` operatore.</span><span class="sxs-lookup"><span data-stu-id="84297-121">`key1` must be from the collection on the left side of the `Join` operator.</span></span> <span data-ttu-id="84297-122">`key2` deve essere compresa tra la raccolta sul lato destro del `Join` operatore.</span><span class="sxs-lookup"><span data-stu-id="84297-122">`key2` must be from the collection on the right side of the `Join` operator.</span></span>  
  
 <span data-ttu-id="84297-123">Le chiavi usate nella condizione di join possono essere espressioni che includono più di un elemento dalla raccolta.</span><span class="sxs-lookup"><span data-stu-id="84297-123">The keys used in the join condition can be expressions that include more than one item from the collection.</span></span> <span data-ttu-id="84297-124">Tuttavia, ogni espressione chiave può contenere solo gli elementi del rispettivo insieme.</span><span class="sxs-lookup"><span data-stu-id="84297-124">However, each key expression can contain only items from its respective collection.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="84297-125">Note</span><span class="sxs-lookup"><span data-stu-id="84297-125">Remarks</span></span>  
 <span data-ttu-id="84297-126">Il `Join` clausola combina due raccolte in base ai corrispondenti valori di chiave da raccolte da includere.</span><span class="sxs-lookup"><span data-stu-id="84297-126">The `Join` clause combines two collections based on matching key values from the collections being joined.</span></span> <span data-ttu-id="84297-127">La raccolta risultante può contenere qualsiasi combinazione di valori dalla raccolta identificata nel lato sinistro della `Join` operatore e la raccolta identificata nel `Join` clausola.</span><span class="sxs-lookup"><span data-stu-id="84297-127">The resulting collection can contain any combination of values from the collection identified on the left side of the `Join` operator and the collection identified in the `Join` clause.</span></span> <span data-ttu-id="84297-128">La query restituirà solo i risultati per il quale la condizione specificata dal `Equals` operatore viene soddisfatta.</span><span class="sxs-lookup"><span data-stu-id="84297-128">The query will return only results for which the condition specified by the `Equals` operator is met.</span></span> <span data-ttu-id="84297-129">Ciò equivale a un `INNER JOIN` in SQL.</span><span class="sxs-lookup"><span data-stu-id="84297-129">This is equivalent to an `INNER JOIN` in SQL.</span></span>  
  
 <span data-ttu-id="84297-130">È possibile usare più `Join` clausole in una query per unire due o più raccolte in un'unica raccolta.</span><span class="sxs-lookup"><span data-stu-id="84297-130">You can use multiple `Join` clauses in a query to join two or more collections into a single collection.</span></span>  
  
 <span data-ttu-id="84297-131">È possibile eseguire un join implicito per combinare raccolte senza il `Join` clausola.</span><span class="sxs-lookup"><span data-stu-id="84297-131">You can perform an implicit join to combine collections without the `Join` clause.</span></span> <span data-ttu-id="84297-132">A tale scopo, includere più `In` clausole nel `From` clausola e specificare un `Where` clausola che identifica le chiavi che si desidera utilizzare per il join.</span><span class="sxs-lookup"><span data-stu-id="84297-132">To do this, include multiple `In` clauses in your `From` clause and specify a `Where` clause that identifies the keys that you want to use for the join.</span></span>  
  
 <span data-ttu-id="84297-133">È possibile usare il `Group Join` clausola per combinare raccolte in un'unica raccolta gerarchica.</span><span class="sxs-lookup"><span data-stu-id="84297-133">You can use the `Group Join` clause to combine collections into a single hierarchical collection.</span></span> <span data-ttu-id="84297-134">Si tratta, ad esempio un `LEFT OUTER JOIN` in SQL.</span><span class="sxs-lookup"><span data-stu-id="84297-134">This is like a `LEFT OUTER JOIN` in SQL.</span></span>  
  
## <a name="example"></a><span data-ttu-id="84297-135">Esempio</span><span class="sxs-lookup"><span data-stu-id="84297-135">Example</span></span>  
 <span data-ttu-id="84297-136">Esempio di codice seguente esegue un join implicito per combinare un elenco di clienti con i relativi ordini.</span><span class="sxs-lookup"><span data-stu-id="84297-136">The following code example performs an implicit join to combine a list of customers with their orders.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#13](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/join-clause_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="84297-137">Esempio</span><span class="sxs-lookup"><span data-stu-id="84297-137">Example</span></span>  
 <span data-ttu-id="84297-138">Esempio di codice seguente unisce due raccolte mediante il `Join` clausola.</span><span class="sxs-lookup"><span data-stu-id="84297-138">The following code example joins two collections by using the `Join` clause.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#12](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/join-clause_2.vb)]  
  
 <span data-ttu-id="84297-139">In questo esempio viene prodotto un output simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="84297-139">This example will produce output similar to the following:</span></span>  
  
 `winlogon (968), Windows Logon`  
  
 `explorer (2424), File Explorer`  
  
 `cmd (5136), Command Window`  
  
## <a name="example"></a><span data-ttu-id="84297-140">Esempio</span><span class="sxs-lookup"><span data-stu-id="84297-140">Example</span></span>  
 <span data-ttu-id="84297-141">Esempio di codice seguente unisce due raccolte mediante il `Join` clausola con due colonne chiave.</span><span class="sxs-lookup"><span data-stu-id="84297-141">The following code example joins two collections by using the `Join` clause with two key columns.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#17](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/join-clause_3.vb)]  
  
 <span data-ttu-id="84297-142">Nell'esempio viene prodotto un output simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="84297-142">The example will produce output similar to the following:</span></span>  
  
 `winlogon (968), Windows Logon, Priority = 13`  
  
 `cmd (700), Command Window, Priority = 8`  
  
 `explorer (2424), File Explorer, Priority = 8`  
  
## <a name="see-also"></a><span data-ttu-id="84297-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="84297-143">See Also</span></span>  
 [<span data-ttu-id="84297-144">Introduzione a LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="84297-144">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [<span data-ttu-id="84297-145">Query</span><span class="sxs-lookup"><span data-stu-id="84297-145">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)  
 [<span data-ttu-id="84297-146">Clausola Select</span><span class="sxs-lookup"><span data-stu-id="84297-146">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)  
 [<span data-ttu-id="84297-147">Clausola From</span><span class="sxs-lookup"><span data-stu-id="84297-147">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)  
 [<span data-ttu-id="84297-148">Clausola Group Join</span><span class="sxs-lookup"><span data-stu-id="84297-148">Group Join Clause</span></span>](../../../visual-basic/language-reference/queries/group-join-clause.md)  
 [<span data-ttu-id="84297-149">Clausola Where</span><span class="sxs-lookup"><span data-stu-id="84297-149">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)
