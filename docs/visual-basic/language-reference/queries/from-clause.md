---
title: Clausola From (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryFrom
- vb.QueryFromIn
- vb.QueryFromLet
helpviewer_keywords:
- queries [Visual Basic], From
- From clause [Visual Basic]
- From statement [Visual Basic]
ms.assetid: 83e3665e-68a0-4540-a3a3-3d777a0f95d5
ms.openlocfilehash: 1f113444efae83de7d299db330593937c7800bb3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604718"
---
# <a name="from-clause-visual-basic"></a><span data-ttu-id="38250-102">Clausola From (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="38250-102">From Clause (Visual Basic)</span></span>
<span data-ttu-id="38250-103">Specifica uno o più variabili di intervallo e una raccolta di query.</span><span class="sxs-lookup"><span data-stu-id="38250-103">Specifies one or more range variables and a collection to query.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38250-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="38250-104">Syntax</span></span>  
  
```  
From element [ As type ] In collection [ _ ]  
  [, element2 [ As type2 ] In collection2 [, ... ] ]  
```  
  
## <a name="parts"></a><span data-ttu-id="38250-105">Parti</span><span class="sxs-lookup"><span data-stu-id="38250-105">Parts</span></span>  
  
|<span data-ttu-id="38250-106">Termine</span><span class="sxs-lookup"><span data-stu-id="38250-106">Term</span></span>|<span data-ttu-id="38250-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="38250-107">Definition</span></span>|  
|---|---|  
|`element`|<span data-ttu-id="38250-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="38250-108">Required.</span></span> <span data-ttu-id="38250-109">Oggetto *variabile di intervallo* utilizzato per scorrere gli elementi della raccolta.</span><span class="sxs-lookup"><span data-stu-id="38250-109">A *range variable* used to iterate through the elements of the collection.</span></span> <span data-ttu-id="38250-110">Una variabile di intervallo viene utilizzata per fare riferimento a ogni membro del `collection` quando la query scorre il `collection`.</span><span class="sxs-lookup"><span data-stu-id="38250-110">A range variable is used to refer to each member of the `collection` as the query iterates through the `collection`.</span></span> <span data-ttu-id="38250-111">Deve essere un tipo enumerabile.</span><span class="sxs-lookup"><span data-stu-id="38250-111">Must be an enumerable type.</span></span>|  
|`type`|<span data-ttu-id="38250-112">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="38250-112">Optional.</span></span> <span data-ttu-id="38250-113">Tipo di `element`.</span><span class="sxs-lookup"><span data-stu-id="38250-113">The type of `element`.</span></span> <span data-ttu-id="38250-114">Se non `type` è specificato, il tipo di `element` viene dedotto dal `collection`.</span><span class="sxs-lookup"><span data-stu-id="38250-114">If no `type` is specified, the type of `element` is inferred from `collection`.</span></span>|  
|`collection`|<span data-ttu-id="38250-115">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="38250-115">Required.</span></span> <span data-ttu-id="38250-116">Fa riferimento alla raccolta per eseguire una query.</span><span class="sxs-lookup"><span data-stu-id="38250-116">Refers to the collection to be queried.</span></span> <span data-ttu-id="38250-117">Deve essere un tipo enumerabile.</span><span class="sxs-lookup"><span data-stu-id="38250-117">Must be an enumerable type.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="38250-118">Note</span><span class="sxs-lookup"><span data-stu-id="38250-118">Remarks</span></span>  
 <span data-ttu-id="38250-119">Il `From` clausola viene utilizzata per identificare i dati di origine per una query e le variabili che vengono utilizzate per fare riferimento a un elemento dalla raccolta di origine.</span><span class="sxs-lookup"><span data-stu-id="38250-119">The `From` clause is used to identify the source data for a query and the variables that are used to refer to an element from the source collection.</span></span> <span data-ttu-id="38250-120">Queste variabili vengono chiamate *le variabili di intervallo*.</span><span class="sxs-lookup"><span data-stu-id="38250-120">These variables are called *range variables*.</span></span> <span data-ttu-id="38250-121">Il `From` è richiesta per una query, tranne quando la clausola di `Aggregate` clausola viene utilizzata per identificare una query che restituisce solo risultati aggregati.</span><span class="sxs-lookup"><span data-stu-id="38250-121">The `From` clause is required for a query, except when the `Aggregate` clause is used to identify a query that returns only aggregated results.</span></span> <span data-ttu-id="38250-122">Per ulteriori informazioni, vedere [clausola Aggregate](../../../visual-basic/language-reference/queries/aggregate-clause.md).</span><span class="sxs-lookup"><span data-stu-id="38250-122">For more information, see [Aggregate Clause](../../../visual-basic/language-reference/queries/aggregate-clause.md).</span></span>  
  
 <span data-ttu-id="38250-123">È possibile specificare più `From` clausole in una query per identificare più raccolte da unire.</span><span class="sxs-lookup"><span data-stu-id="38250-123">You can specify multiple `From` clauses in a query to identify multiple collections to be joined.</span></span> <span data-ttu-id="38250-124">Quando vengono specificate più raccolte, essi vengono scorsi in modo indipendente oppure è possibile aggiungere se sono correlati.</span><span class="sxs-lookup"><span data-stu-id="38250-124">When multiple collections are specified, they are iterated over independently, or you can join them if they are related.</span></span> <span data-ttu-id="38250-125">È possibile aggiungere le raccolte in modo implicito tramite il `Select` clausola, o in modo esplicito utilizzando il `Join` o `Group Join` clausole.</span><span class="sxs-lookup"><span data-stu-id="38250-125">You can join collections implicitly by using the `Select` clause, or explicitly by using the `Join` or `Group Join` clauses.</span></span> <span data-ttu-id="38250-126">In alternativa, è possibile specificare più variabili di intervallo e le raccolte in una singola `From` clausola, con ogni variabile di intervallo correlata e la raccolta separati dagli altri da una virgola.</span><span class="sxs-lookup"><span data-stu-id="38250-126">As an alternative, you can specify multiple range variables and collections in a single `From` clause, with each related range variable and collection separated from the others by a comma.</span></span> <span data-ttu-id="38250-127">Esempio di codice seguente illustra entrambe le opzioni di sintassi per la `From` clausola.</span><span class="sxs-lookup"><span data-stu-id="38250-127">The following code example shows both syntax options for the `From` clause.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#21](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/from-clause_1.vb)]  
  
 <span data-ttu-id="38250-128">Il `From` clausola definisce l'ambito di una query, che è simile all'ambito di un `For` ciclo.</span><span class="sxs-lookup"><span data-stu-id="38250-128">The `From` clause defines the scope of a query, which is similar to the scope of a `For` loop.</span></span> <span data-ttu-id="38250-129">Pertanto, ogni `element` variabile di intervallo nell'ambito di una query deve avere un nome univoco.</span><span class="sxs-lookup"><span data-stu-id="38250-129">Therefore, each `element` range variable in the scope of a query must have a unique name.</span></span> <span data-ttu-id="38250-130">Poiché è possibile specificare più `From` clausole per una query, le successive `From` clausole possono fare riferimento alle variabili di intervallo nel `From` clausola oppure possono fare riferimento alle variabili di intervallo precedentemente `From` clausola.</span><span class="sxs-lookup"><span data-stu-id="38250-130">Because you can specify multiple `From` clauses for a query, subsequent `From` clauses can refer to range variables in the `From` clause, or they can refer to range variables in a previous `From` clause.</span></span> <span data-ttu-id="38250-131">Ad esempio, nell'esempio seguente viene nidificata `From` clausola in cui la raccolta nella seconda clausola si basa su una proprietà della variabile di intervallo nella prima clausola.</span><span class="sxs-lookup"><span data-stu-id="38250-131">For example, the following example shows a nested `From` clause where the collection in the second clause is based on a property of the range variable in the first clause.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#22](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/from-clause_2.vb)]  
  
 <span data-ttu-id="38250-132">Ogni `From` clausola può essere seguita da una qualsiasi combinazione di clausole di query aggiuntive per perfezionare la query.</span><span class="sxs-lookup"><span data-stu-id="38250-132">Each `From` clause can be followed by any combination of additional query clauses to refine the query.</span></span> <span data-ttu-id="38250-133">È possibile affinare la query nei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="38250-133">You can refine the query in the following ways:</span></span>  
  
-   <span data-ttu-id="38250-134">Combinare più raccolte in modo implicito tramite il `From` e `Select` clausole, o in modo esplicito utilizzando il `Join` o `Group Join` clausole.</span><span class="sxs-lookup"><span data-stu-id="38250-134">Combine multiple collections implicitly by using the `From` and `Select` clauses, or explicitly by using the `Join` or `Group Join` clauses.</span></span>  
  
-   <span data-ttu-id="38250-135">Utilizzare il `Where` clausola per filtrare i risultati della query.</span><span class="sxs-lookup"><span data-stu-id="38250-135">Use the `Where` clause to filter the query result.</span></span>  
  
-   <span data-ttu-id="38250-136">Ordinare il risultato utilizzando il `Order By` clausola.</span><span class="sxs-lookup"><span data-stu-id="38250-136">Sort the result by using the `Order By` clause.</span></span>  
  
-   <span data-ttu-id="38250-137">Raggruppare i risultati simili utilizzando il `Group By` clausola.</span><span class="sxs-lookup"><span data-stu-id="38250-137">Group similar results together by using the `Group By` clause.</span></span>  
  
-   <span data-ttu-id="38250-138">Utilizzare il `Aggregate` clausola per identificare le funzioni di aggregazione da valutare per l'intero risultato della query.</span><span class="sxs-lookup"><span data-stu-id="38250-138">Use the `Aggregate` clause to identify aggregate functions to evaluate for the whole query result.</span></span>  
  
-   <span data-ttu-id="38250-139">Utilizzare il `Let` clausola per introdurre una variabile di iterazione, il cui valore è determinato da un'espressione anziché una raccolta.</span><span class="sxs-lookup"><span data-stu-id="38250-139">Use the `Let` clause to introduce an iteration variable whose value is determined by an expression instead of a collection.</span></span>  
  
-   <span data-ttu-id="38250-140">Utilizzare il `Distinct` clausola per ignorare i risultati della query duplicata.</span><span class="sxs-lookup"><span data-stu-id="38250-140">Use the `Distinct` clause to ignore duplicate query results.</span></span>  
  
-   <span data-ttu-id="38250-141">Identificare le parti del risultato da restituire utilizzando il `Skip`, `Take`, `Skip While`, e `Take While` clausole.</span><span class="sxs-lookup"><span data-stu-id="38250-141">Identify parts of the result to return by using the `Skip`, `Take`, `Skip While`, and `Take While` clauses.</span></span>  
  
## <a name="example"></a><span data-ttu-id="38250-142">Esempio</span><span class="sxs-lookup"><span data-stu-id="38250-142">Example</span></span>  
 <span data-ttu-id="38250-143">La query seguente espressione utilizza un `From` clausola per dichiarare una variabile di intervallo `cust` per ogni `Customer` oggetto di `customers` insieme.</span><span class="sxs-lookup"><span data-stu-id="38250-143">The following query expression uses a `From` clause to declare a range variable `cust` for each `Customer` object in the `customers` collection.</span></span> <span data-ttu-id="38250-144">Il `Where` clausola utilizza la variabile di intervallo per limitare l'output ai clienti dalla regione specificata.</span><span class="sxs-lookup"><span data-stu-id="38250-144">The `Where` clause uses the range variable to restrict the output to customers from the specified region.</span></span> <span data-ttu-id="38250-145">Il `For Each` ciclo Visualizza il nome della società per ogni cliente nel risultato della query.</span><span class="sxs-lookup"><span data-stu-id="38250-145">The `For Each` loop displays the company name for each customer in the query result.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#23](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/from-clause_3.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="38250-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="38250-146">See Also</span></span>  
 [<span data-ttu-id="38250-147">Query</span><span class="sxs-lookup"><span data-stu-id="38250-147">Queries</span></span>](../../../visual-basic/language-reference/queries/queries.md)  
 [<span data-ttu-id="38250-148">Introduzione a LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="38250-148">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [<span data-ttu-id="38250-149">Istruzione For Each...Next</span><span class="sxs-lookup"><span data-stu-id="38250-149">For Each...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-each-next-statement.md)  
 [<span data-ttu-id="38250-150">Istruzione For...Next</span><span class="sxs-lookup"><span data-stu-id="38250-150">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)  
 [<span data-ttu-id="38250-151">Clausola Select</span><span class="sxs-lookup"><span data-stu-id="38250-151">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)  
 [<span data-ttu-id="38250-152">Clausola Where</span><span class="sxs-lookup"><span data-stu-id="38250-152">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)  
 [<span data-ttu-id="38250-153">Clausola Aggregate</span><span class="sxs-lookup"><span data-stu-id="38250-153">Aggregate Clause</span></span>](../../../visual-basic/language-reference/queries/aggregate-clause.md)  
 [<span data-ttu-id="38250-154">Clausola Distinct</span><span class="sxs-lookup"><span data-stu-id="38250-154">Distinct Clause</span></span>](../../../visual-basic/language-reference/queries/distinct-clause.md)  
 [<span data-ttu-id="38250-155">Clausola Join</span><span class="sxs-lookup"><span data-stu-id="38250-155">Join Clause</span></span>](../../../visual-basic/language-reference/queries/join-clause.md)  
 [<span data-ttu-id="38250-156">Clausola Group Join</span><span class="sxs-lookup"><span data-stu-id="38250-156">Group Join Clause</span></span>](../../../visual-basic/language-reference/queries/group-join-clause.md)  
 [<span data-ttu-id="38250-157">Clausola Order By</span><span class="sxs-lookup"><span data-stu-id="38250-157">Order By Clause</span></span>](../../../visual-basic/language-reference/queries/order-by-clause.md)  
 [<span data-ttu-id="38250-158">Clausola Let</span><span class="sxs-lookup"><span data-stu-id="38250-158">Let Clause</span></span>](../../../visual-basic/language-reference/queries/let-clause.md)  
 [<span data-ttu-id="38250-159">Clausola Skip</span><span class="sxs-lookup"><span data-stu-id="38250-159">Skip Clause</span></span>](../../../visual-basic/language-reference/queries/skip-clause.md)  
 [<span data-ttu-id="38250-160">Clausola Take</span><span class="sxs-lookup"><span data-stu-id="38250-160">Take Clause</span></span>](../../../visual-basic/language-reference/queries/take-clause.md)  
 [<span data-ttu-id="38250-161">Clausola Skip While</span><span class="sxs-lookup"><span data-stu-id="38250-161">Skip While Clause</span></span>](../../../visual-basic/language-reference/queries/skip-while-clause.md)  
 [<span data-ttu-id="38250-162">Clausola Take While</span><span class="sxs-lookup"><span data-stu-id="38250-162">Take While Clause</span></span>](../../../visual-basic/language-reference/queries/take-while-clause.md)
