---
title: Clausola From
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
ms.openlocfilehash: 33680f49247b3b2a6082b3a6b27ca64f8401e42d
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84396181"
---
# <a name="from-clause-visual-basic"></a><span data-ttu-id="9a01e-102">Clausola From (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9a01e-102">From Clause (Visual Basic)</span></span>
<span data-ttu-id="9a01e-103">Specifica una o più variabili di intervallo e una raccolta su cui eseguire una query.</span><span class="sxs-lookup"><span data-stu-id="9a01e-103">Specifies one or more range variables and a collection to query.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a01e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9a01e-104">Syntax</span></span>  
  
```vb  
From element [ As type ] In collection [ _ ]  
  [, element2 [ As type2 ] In collection2 [, ... ] ]  
```  
  
## <a name="parts"></a><span data-ttu-id="9a01e-105">Parti</span><span class="sxs-lookup"><span data-stu-id="9a01e-105">Parts</span></span>  
  
|<span data-ttu-id="9a01e-106">Termine</span><span class="sxs-lookup"><span data-stu-id="9a01e-106">Term</span></span>|<span data-ttu-id="9a01e-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="9a01e-107">Definition</span></span>|  
|---|---|  
|`element`|<span data-ttu-id="9a01e-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="9a01e-108">Required.</span></span> <span data-ttu-id="9a01e-109">*Variabile di intervallo* utilizzata per scorrere gli elementi della raccolta.</span><span class="sxs-lookup"><span data-stu-id="9a01e-109">A *range variable* used to iterate through the elements of the collection.</span></span> <span data-ttu-id="9a01e-110">Una variabile di intervallo viene utilizzata per fare riferimento a ogni membro di `collection` mentre la query scorre `collection` .</span><span class="sxs-lookup"><span data-stu-id="9a01e-110">A range variable is used to refer to each member of the `collection` as the query iterates through the `collection`.</span></span> <span data-ttu-id="9a01e-111">Deve essere un tipo enumerabile.</span><span class="sxs-lookup"><span data-stu-id="9a01e-111">Must be an enumerable type.</span></span>|  
|`type`|<span data-ttu-id="9a01e-112">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="9a01e-112">Optional.</span></span> <span data-ttu-id="9a01e-113">Tipo di `element`.</span><span class="sxs-lookup"><span data-stu-id="9a01e-113">The type of `element`.</span></span> <span data-ttu-id="9a01e-114">Se non `type` viene specificato alcun parametro, il tipo di `element` viene dedotto da `collection` .</span><span class="sxs-lookup"><span data-stu-id="9a01e-114">If no `type` is specified, the type of `element` is inferred from `collection`.</span></span>|  
|`collection`|<span data-ttu-id="9a01e-115">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="9a01e-115">Required.</span></span> <span data-ttu-id="9a01e-116">Fa riferimento alla raccolta su cui eseguire una query.</span><span class="sxs-lookup"><span data-stu-id="9a01e-116">Refers to the collection to be queried.</span></span> <span data-ttu-id="9a01e-117">Deve essere un tipo enumerabile.</span><span class="sxs-lookup"><span data-stu-id="9a01e-117">Must be an enumerable type.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9a01e-118">Commenti</span><span class="sxs-lookup"><span data-stu-id="9a01e-118">Remarks</span></span>  
 <span data-ttu-id="9a01e-119">La `From` clausola viene utilizzata per identificare i dati di origine per una query e le variabili utilizzate per fare riferimento a un elemento della raccolta di origine.</span><span class="sxs-lookup"><span data-stu-id="9a01e-119">The `From` clause is used to identify the source data for a query and the variables that are used to refer to an element from the source collection.</span></span> <span data-ttu-id="9a01e-120">Queste variabili sono denominate *variabili di intervallo*.</span><span class="sxs-lookup"><span data-stu-id="9a01e-120">These variables are called *range variables*.</span></span> <span data-ttu-id="9a01e-121">La `From` clausola è obbligatoria per una query, tranne quando la `Aggregate` clausola viene utilizzata per identificare una query che restituisce solo i risultati aggregati.</span><span class="sxs-lookup"><span data-stu-id="9a01e-121">The `From` clause is required for a query, except when the `Aggregate` clause is used to identify a query that returns only aggregated results.</span></span> <span data-ttu-id="9a01e-122">Per ulteriori informazioni, vedere [clausola Aggregate](aggregate-clause.md).</span><span class="sxs-lookup"><span data-stu-id="9a01e-122">For more information, see [Aggregate Clause](aggregate-clause.md).</span></span>  
  
 <span data-ttu-id="9a01e-123">È possibile specificare più `From` clausole in una query per identificare più raccolte da unire in join.</span><span class="sxs-lookup"><span data-stu-id="9a01e-123">You can specify multiple `From` clauses in a query to identify multiple collections to be joined.</span></span> <span data-ttu-id="9a01e-124">Quando si specificano più raccolte, vengono ripetute in modo indipendente oppure è possibile unirle se sono correlate.</span><span class="sxs-lookup"><span data-stu-id="9a01e-124">When multiple collections are specified, they are iterated over independently, or you can join them if they are related.</span></span> <span data-ttu-id="9a01e-125">È possibile unire le raccolte in modo implicito usando la `Select` clausola oppure in modo esplicito usando le `Join` `Group Join` clausole o.</span><span class="sxs-lookup"><span data-stu-id="9a01e-125">You can join collections implicitly by using the `Select` clause, or explicitly by using the `Join` or `Group Join` clauses.</span></span> <span data-ttu-id="9a01e-126">In alternativa, è possibile specificare più variabili di intervallo e raccolte in una singola `From` clausola, con ogni variabile di intervallo e raccolta correlate separate dalle altre da una virgola.</span><span class="sxs-lookup"><span data-stu-id="9a01e-126">As an alternative, you can specify multiple range variables and collections in a single `From` clause, with each related range variable and collection separated from the others by a comma.</span></span> <span data-ttu-id="9a01e-127">Nell'esempio di codice seguente vengono illustrate entrambe le opzioni di sintassi per la `From` clausola.</span><span class="sxs-lookup"><span data-stu-id="9a01e-127">The following code example shows both syntax options for the `From` clause.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#21)]  
  
 <span data-ttu-id="9a01e-128">La `From` clausola definisce l'ambito di una query, che è simile all'ambito di un `For` ciclo.</span><span class="sxs-lookup"><span data-stu-id="9a01e-128">The `From` clause defines the scope of a query, which is similar to the scope of a `For` loop.</span></span> <span data-ttu-id="9a01e-129">Ogni `element` variabile di intervallo nell'ambito di una query deve pertanto avere un nome univoco.</span><span class="sxs-lookup"><span data-stu-id="9a01e-129">Therefore, each `element` range variable in the scope of a query must have a unique name.</span></span> <span data-ttu-id="9a01e-130">Poiché è possibile specificare più `From` clausole per una query, `From` le clausole successive possono fare riferimento alle variabili di intervallo nella `From` clausola oppure possono fare riferimento alle variabili di intervallo in una `From` clausola precedente.</span><span class="sxs-lookup"><span data-stu-id="9a01e-130">Because you can specify multiple `From` clauses for a query, subsequent `From` clauses can refer to range variables in the `From` clause, or they can refer to range variables in a previous `From` clause.</span></span> <span data-ttu-id="9a01e-131">Ad esempio, nell'esempio seguente viene illustrata una clausola annidata `From` in cui la raccolta nella seconda clausola è basata su una proprietà della variabile di intervallo nella prima clausola.</span><span class="sxs-lookup"><span data-stu-id="9a01e-131">For example, the following example shows a nested `From` clause where the collection in the second clause is based on a property of the range variable in the first clause.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#22)]  
  
 <span data-ttu-id="9a01e-132">Ogni `From` clausola può essere seguita da qualsiasi combinazione di clausole di query aggiuntive per perfezionare la query.</span><span class="sxs-lookup"><span data-stu-id="9a01e-132">Each `From` clause can be followed by any combination of additional query clauses to refine the query.</span></span> <span data-ttu-id="9a01e-133">È possibile affinare la query nei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="9a01e-133">You can refine the query in the following ways:</span></span>  
  
- <span data-ttu-id="9a01e-134">Combinare più raccolte in modo implicito usando `From` le `Select` clausole e oppure in modo esplicito usando `Join` le `Group Join` clausole o.</span><span class="sxs-lookup"><span data-stu-id="9a01e-134">Combine multiple collections implicitly by using the `From` and `Select` clauses, or explicitly by using the `Join` or `Group Join` clauses.</span></span>  
  
- <span data-ttu-id="9a01e-135">Utilizzare la `Where` clausola per filtrare il risultato della query.</span><span class="sxs-lookup"><span data-stu-id="9a01e-135">Use the `Where` clause to filter the query result.</span></span>  
  
- <span data-ttu-id="9a01e-136">Ordinare il risultato usando la `Order By` clausola.</span><span class="sxs-lookup"><span data-stu-id="9a01e-136">Sort the result by using the `Order By` clause.</span></span>  
  
- <span data-ttu-id="9a01e-137">Raggruppare i risultati simili utilizzando la `Group By` clausola.</span><span class="sxs-lookup"><span data-stu-id="9a01e-137">Group similar results together by using the `Group By` clause.</span></span>  
  
- <span data-ttu-id="9a01e-138">Utilizzare la `Aggregate` clausola per identificare le funzioni di aggregazione da valutare per l'intero risultato della query.</span><span class="sxs-lookup"><span data-stu-id="9a01e-138">Use the `Aggregate` clause to identify aggregate functions to evaluate for the whole query result.</span></span>  
  
- <span data-ttu-id="9a01e-139">Utilizzare la `Let` clausola per introdurre una variabile di iterazione il cui valore è determinato da un'espressione anziché da una raccolta.</span><span class="sxs-lookup"><span data-stu-id="9a01e-139">Use the `Let` clause to introduce an iteration variable whose value is determined by an expression instead of a collection.</span></span>  
  
- <span data-ttu-id="9a01e-140">Utilizzare la `Distinct` clausola per ignorare i risultati della query duplicati.</span><span class="sxs-lookup"><span data-stu-id="9a01e-140">Use the `Distinct` clause to ignore duplicate query results.</span></span>  
  
- <span data-ttu-id="9a01e-141">Identificare le parti del risultato da restituire utilizzando le `Skip` `Take` clausole,, `Skip While` e `Take While` .</span><span class="sxs-lookup"><span data-stu-id="9a01e-141">Identify parts of the result to return by using the `Skip`, `Take`, `Skip While`, and `Take While` clauses.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9a01e-142">Esempio</span><span class="sxs-lookup"><span data-stu-id="9a01e-142">Example</span></span>  
 <span data-ttu-id="9a01e-143">Nell'espressione di query seguente viene utilizzata una `From` clausola per dichiarare una variabile di intervallo `cust` per ogni `Customer` oggetto della `customers` raccolta.</span><span class="sxs-lookup"><span data-stu-id="9a01e-143">The following query expression uses a `From` clause to declare a range variable `cust` for each `Customer` object in the `customers` collection.</span></span> <span data-ttu-id="9a01e-144">La `Where` clausola usa la variabile di intervallo per limitare l'output ai clienti dall'area specificata.</span><span class="sxs-lookup"><span data-stu-id="9a01e-144">The `Where` clause uses the range variable to restrict the output to customers from the specified region.</span></span> <span data-ttu-id="9a01e-145">Il `For Each` ciclo Visualizza il nome della società per ogni cliente nel risultato della query.</span><span class="sxs-lookup"><span data-stu-id="9a01e-145">The `For Each` loop displays the company name for each customer in the query result.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#23)]  
  
## <a name="see-also"></a><span data-ttu-id="9a01e-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9a01e-146">See also</span></span>

- [<span data-ttu-id="9a01e-147">Query</span><span class="sxs-lookup"><span data-stu-id="9a01e-147">Queries</span></span>](index.md)
- [<span data-ttu-id="9a01e-148">Introduzione a LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9a01e-148">Introduction to LINQ in Visual Basic</span></span>](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="9a01e-149">Istruzione For Each...Next</span><span class="sxs-lookup"><span data-stu-id="9a01e-149">For Each...Next Statement</span></span>](../statements/for-each-next-statement.md)
- [<span data-ttu-id="9a01e-150">Istruzione For...Next</span><span class="sxs-lookup"><span data-stu-id="9a01e-150">For...Next Statement</span></span>](../statements/for-next-statement.md)
- [<span data-ttu-id="9a01e-151">Clausola SELECT</span><span class="sxs-lookup"><span data-stu-id="9a01e-151">Select Clause</span></span>](select-clause.md)
- [<span data-ttu-id="9a01e-152">Clausola WHERE</span><span class="sxs-lookup"><span data-stu-id="9a01e-152">Where Clause</span></span>](where-clause.md)
- [<span data-ttu-id="9a01e-153">Aggregate Clause</span><span class="sxs-lookup"><span data-stu-id="9a01e-153">Aggregate Clause</span></span>](aggregate-clause.md)
- [<span data-ttu-id="9a01e-154">Clausola Distinct</span><span class="sxs-lookup"><span data-stu-id="9a01e-154">Distinct Clause</span></span>](distinct-clause.md)
- [<span data-ttu-id="9a01e-155">Clausola join</span><span class="sxs-lookup"><span data-stu-id="9a01e-155">Join Clause</span></span>](join-clause.md)
- [<span data-ttu-id="9a01e-156">Clausola Group Join</span><span class="sxs-lookup"><span data-stu-id="9a01e-156">Group Join Clause</span></span>](group-join-clause.md)
- [<span data-ttu-id="9a01e-157">Clausola Order By</span><span class="sxs-lookup"><span data-stu-id="9a01e-157">Order By Clause</span></span>](order-by-clause.md)
- [<span data-ttu-id="9a01e-158">Clausola Let</span><span class="sxs-lookup"><span data-stu-id="9a01e-158">Let Clause</span></span>](let-clause.md)
- [<span data-ttu-id="9a01e-159">Clausola Skip</span><span class="sxs-lookup"><span data-stu-id="9a01e-159">Skip Clause</span></span>](skip-clause.md)
- [<span data-ttu-id="9a01e-160">Clausola Take</span><span class="sxs-lookup"><span data-stu-id="9a01e-160">Take Clause</span></span>](take-clause.md)
- [<span data-ttu-id="9a01e-161">Clausola Skip While</span><span class="sxs-lookup"><span data-stu-id="9a01e-161">Skip While Clause</span></span>](skip-while-clause.md)
- [<span data-ttu-id="9a01e-162">Clausola Take While</span><span class="sxs-lookup"><span data-stu-id="9a01e-162">Take While Clause</span></span>](take-while-clause.md)
