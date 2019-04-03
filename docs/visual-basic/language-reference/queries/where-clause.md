---
title: Clausola Where (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryWhere
helpviewer_keywords:
- Where statement [Visual Basic]
- queries [Visual Basic], Where
- Where clause [Visual Basic]
ms.assetid: 48b5c2c5-3181-429c-8545-894296798c89
ms.openlocfilehash: 5632e69039baebb3d1f1fd90c04586d9e50fe40f
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58834504"
---
# <a name="where-clause-visual-basic"></a><span data-ttu-id="ed498-102">Clausola Where (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ed498-102">Where Clause (Visual Basic)</span></span>
<span data-ttu-id="ed498-103">Specifica la condizione di filtro per una query.</span><span class="sxs-lookup"><span data-stu-id="ed498-103">Specifies the filtering condition for a query.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed498-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ed498-104">Syntax</span></span>  
  
```  
Where condition  
```  
  
## <a name="parts"></a><span data-ttu-id="ed498-105">Parti</span><span class="sxs-lookup"><span data-stu-id="ed498-105">Parts</span></span>  
 `condition`  
 <span data-ttu-id="ed498-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="ed498-106">Required.</span></span> <span data-ttu-id="ed498-107">Espressione che determina se i valori per l'elemento corrente nella raccolta sono inclusi nella raccolta di output.</span><span class="sxs-lookup"><span data-stu-id="ed498-107">An expression that determines whether the values for the current item in the collection are included in the output collection.</span></span> <span data-ttu-id="ed498-108">L'espressione deve restituire un `Boolean` valore o l'equivalente di un `Boolean` valore.</span><span class="sxs-lookup"><span data-stu-id="ed498-108">The expression must evaluate to a `Boolean` value or the equivalent of a `Boolean` value.</span></span> <span data-ttu-id="ed498-109">Se la condizione restituisce `True`, l'elemento è incluso nel risultato della query; in caso contrario, l'elemento viene escluso dai risultati della query.</span><span class="sxs-lookup"><span data-stu-id="ed498-109">If the condition evaluates to `True`, the element is included in the query result; otherwise, the element is excluded from the query result.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ed498-110">Note</span><span class="sxs-lookup"><span data-stu-id="ed498-110">Remarks</span></span>  
 <span data-ttu-id="ed498-111">Il `Where` clausola consente di filtrare i dati delle query selezionando solo gli elementi che soddisfano determinati criteri.</span><span class="sxs-lookup"><span data-stu-id="ed498-111">The `Where` clause enables you to filter query data by selecting only elements that meet certain criteria.</span></span> <span data-ttu-id="ed498-112">Gli elementi i cui valori che il `Where` clausola restituisca `True` sono incluse nel risultato della query; sono esclusi gli altri elementi.</span><span class="sxs-lookup"><span data-stu-id="ed498-112">Elements whose values cause the `Where` clause to evaluate to `True` are included in the query result; other elements are excluded.</span></span> <span data-ttu-id="ed498-113">L'espressione che viene usato in un `Where` clausola deve corrispondere a un `Boolean` o l'equivalente di un `Boolean`, ad esempio un numero intero che restituisce `False` quando il valore è zero.</span><span class="sxs-lookup"><span data-stu-id="ed498-113">The expression that is used in a `Where` clause must evaluate to a `Boolean` or the equivalent of a `Boolean`, such as an Integer that evaluates to `False` when its value is zero.</span></span> <span data-ttu-id="ed498-114">È possibile combinare più espressioni in un `Where` clausola con operatori logici, ad esempio `And`, `Or`, `AndAlso`, `OrElse`, `Is`, e `IsNot`.</span><span class="sxs-lookup"><span data-stu-id="ed498-114">You can combine multiple expressions in a `Where` clause by using logical operators such as `And`, `Or`, `AndAlso`, `OrElse`, `Is`, and `IsNot`.</span></span>  
  
 <span data-ttu-id="ed498-115">Per impostazione predefinita, le espressioni di query non vengono valutate fino a quando non vi si accede, ad esempio, quando sono associati a dati o scorrere in un `For` ciclo.</span><span class="sxs-lookup"><span data-stu-id="ed498-115">By default, query expressions are not evaluated until they are accessed—for example, when they are data-bound or iterated through in a `For` loop.</span></span> <span data-ttu-id="ed498-116">Di conseguenza, il `Where` clausola non viene valutata fino a quando non si accede alla query.</span><span class="sxs-lookup"><span data-stu-id="ed498-116">As a result, the `Where` clause is not evaluated until the query is accessed.</span></span> <span data-ttu-id="ed498-117">Se si dispone di valori esterni per la query che vengono usate nel `Where` clausola, assicurarsi che il valore appropriato viene utilizzato nel `Where` clausola al momento dell'esecuzione della query.</span><span class="sxs-lookup"><span data-stu-id="ed498-117">If you have values external to the query that are used in the `Where` clause, ensure that the appropriate value is used in the `Where` clause at the time the query is executed.</span></span> <span data-ttu-id="ed498-118">Per altre informazioni sull'esecuzione di query, vedere [Writing Your prima Query LINQ](../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md).</span><span class="sxs-lookup"><span data-stu-id="ed498-118">For more information about query execution, see [Writing Your First LINQ Query](../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md).</span></span>  
  
 <span data-ttu-id="ed498-119">È possibile chiamare funzioni all'interno di un `Where` clausola per eseguire un calcolo o un'operazione su un valore dall'elemento corrente nella raccolta.</span><span class="sxs-lookup"><span data-stu-id="ed498-119">You can call functions within a `Where` clause to perform a calculation or operation on a value from the current element in the collection.</span></span> <span data-ttu-id="ed498-120">Chiamata a una funzione un `Where` clausola può comportare la query venga eseguita immediatamente quando viene definito anziché quando vi si accede.</span><span class="sxs-lookup"><span data-stu-id="ed498-120">Calling a function in a `Where` clause can cause the query to be executed immediately when it is defined instead of when it is accessed.</span></span> <span data-ttu-id="ed498-121">Per altre informazioni sull'esecuzione di query, vedere [Writing Your prima Query LINQ](../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md).</span><span class="sxs-lookup"><span data-stu-id="ed498-121">For more information about query execution, see [Writing Your First LINQ Query](../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ed498-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="ed498-122">Example</span></span>  
 <span data-ttu-id="ed498-123">La query seguente espressione Usa un `From` clausola per dichiarare una variabile di intervallo `cust` per ogni `Customer` dell'oggetto nel `customers` raccolta.</span><span class="sxs-lookup"><span data-stu-id="ed498-123">The following query expression uses a `From` clause to declare a range variable `cust` for each `Customer` object in the `customers` collection.</span></span> <span data-ttu-id="ed498-124">Il `Where` clausola utilizza la variabile di intervallo per limitare l'output per i clienti dall'area specificata.</span><span class="sxs-lookup"><span data-stu-id="ed498-124">The `Where` clause uses the range variable to restrict the output to customers from the specified region.</span></span> <span data-ttu-id="ed498-125">Il `For Each` ciclo Visualizza il nome della società per ogni cliente nel risultato della query.</span><span class="sxs-lookup"><span data-stu-id="ed498-125">The `For Each` loop displays the company name for each customer in the query result.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#23)]  
  
## <a name="example"></a><span data-ttu-id="ed498-126">Esempio</span><span class="sxs-lookup"><span data-stu-id="ed498-126">Example</span></span>  
 <span data-ttu-id="ed498-127">L'esempio seguente usa `And` e `Or` operatori logici nel `Where` clausola.</span><span class="sxs-lookup"><span data-stu-id="ed498-127">The following example uses `And` and `Or` logical operators in the `Where` clause.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#31)]  
  
## <a name="see-also"></a><span data-ttu-id="ed498-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ed498-128">See also</span></span>

- [<span data-ttu-id="ed498-129">Introduzione a LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ed498-129">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="ed498-130">Query</span><span class="sxs-lookup"><span data-stu-id="ed498-130">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="ed498-131">Clausola From</span><span class="sxs-lookup"><span data-stu-id="ed498-131">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="ed498-132">Clausola Select</span><span class="sxs-lookup"><span data-stu-id="ed498-132">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="ed498-133">Istruzione For Each...Next</span><span class="sxs-lookup"><span data-stu-id="ed498-133">For Each...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-each-next-statement.md)
