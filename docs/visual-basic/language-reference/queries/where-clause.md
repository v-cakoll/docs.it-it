---
title: Clausola Where
ms.date: 07/20/2015
f1_keywords:
- vb.QueryWhere
helpviewer_keywords:
- Where statement [Visual Basic]
- queries [Visual Basic], Where
- Where clause [Visual Basic]
ms.assetid: 48b5c2c5-3181-429c-8545-894296798c89
ms.openlocfilehash: 60b7ebe96ce0c4580c36675b2e4aa5f9888732c3
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349634"
---
# <a name="where-clause-visual-basic"></a><span data-ttu-id="4c23c-102">Clausola Where (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4c23c-102">Where Clause (Visual Basic)</span></span>
<span data-ttu-id="4c23c-103">Specifica la condizione di filtro per una query.</span><span class="sxs-lookup"><span data-stu-id="4c23c-103">Specifies the filtering condition for a query.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4c23c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4c23c-104">Syntax</span></span>  
  
```vb  
Where condition  
```  
  
## <a name="parts"></a><span data-ttu-id="4c23c-105">Parti</span><span class="sxs-lookup"><span data-stu-id="4c23c-105">Parts</span></span>  
 `condition`  
 <span data-ttu-id="4c23c-106">Obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="4c23c-106">Required.</span></span> <span data-ttu-id="4c23c-107">Espressione che determina se i valori per l'elemento corrente nella raccolta sono inclusi nella raccolta di output.</span><span class="sxs-lookup"><span data-stu-id="4c23c-107">An expression that determines whether the values for the current item in the collection are included in the output collection.</span></span> <span data-ttu-id="4c23c-108">L'espressione deve restituire un valore `Boolean` o l'equivalente di un valore `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="4c23c-108">The expression must evaluate to a `Boolean` value or the equivalent of a `Boolean` value.</span></span> <span data-ttu-id="4c23c-109">Se la condizione restituisce `True`, l'elemento viene incluso nel risultato della query. in caso contrario, l'elemento viene escluso dal risultato della query.</span><span class="sxs-lookup"><span data-stu-id="4c23c-109">If the condition evaluates to `True`, the element is included in the query result; otherwise, the element is excluded from the query result.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4c23c-110">Note</span><span class="sxs-lookup"><span data-stu-id="4c23c-110">Remarks</span></span>  
 <span data-ttu-id="4c23c-111">La clausola `Where` consente di filtrare i dati della query selezionando solo gli elementi che soddisfano determinati criteri.</span><span class="sxs-lookup"><span data-stu-id="4c23c-111">The `Where` clause enables you to filter query data by selecting only elements that meet certain criteria.</span></span> <span data-ttu-id="4c23c-112">Gli elementi i cui valori determinano che la clausola `Where` restituisca `True` sono inclusi nel risultato della query. gli altri elementi sono esclusi.</span><span class="sxs-lookup"><span data-stu-id="4c23c-112">Elements whose values cause the `Where` clause to evaluate to `True` are included in the query result; other elements are excluded.</span></span> <span data-ttu-id="4c23c-113">L'espressione utilizzata in una clausola `Where` deve restituire una `Boolean` o l'equivalente di un `Boolean`, ad esempio un numero intero che restituisce `False` quando il valore è zero.</span><span class="sxs-lookup"><span data-stu-id="4c23c-113">The expression that is used in a `Where` clause must evaluate to a `Boolean` or the equivalent of a `Boolean`, such as an Integer that evaluates to `False` when its value is zero.</span></span> <span data-ttu-id="4c23c-114">È possibile combinare più espressioni in una clausola `Where` usando operatori logici come `And`, `Or`, `AndAlso`, `OrElse`, `Is`e `IsNot`.</span><span class="sxs-lookup"><span data-stu-id="4c23c-114">You can combine multiple expressions in a `Where` clause by using logical operators such as `And`, `Or`, `AndAlso`, `OrElse`, `Is`, and `IsNot`.</span></span>  
  
 <span data-ttu-id="4c23c-115">Per impostazione predefinita, le espressioni di query non vengono valutate fino a quando non vengono accessibili, ad esempio quando sono associate a dati o iterate in un ciclo `For`.</span><span class="sxs-lookup"><span data-stu-id="4c23c-115">By default, query expressions are not evaluated until they are accessed—for example, when they are data-bound or iterated through in a `For` loop.</span></span> <span data-ttu-id="4c23c-116">Di conseguenza, la clausola `Where` non viene valutata fino a quando non si accede alla query.</span><span class="sxs-lookup"><span data-stu-id="4c23c-116">As a result, the `Where` clause is not evaluated until the query is accessed.</span></span> <span data-ttu-id="4c23c-117">Se i valori sono esterni alla query utilizzata nella clausola `Where`, assicurarsi che nella clausola `Where` venga utilizzato il valore appropriato nel momento in cui viene eseguita la query.</span><span class="sxs-lookup"><span data-stu-id="4c23c-117">If you have values external to the query that are used in the `Where` clause, ensure that the appropriate value is used in the `Where` clause at the time the query is executed.</span></span> <span data-ttu-id="4c23c-118">Per ulteriori informazioni sull'esecuzione di query, vedere [scrittura della prima query LINQ](../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md).</span><span class="sxs-lookup"><span data-stu-id="4c23c-118">For more information about query execution, see [Writing Your First LINQ Query](../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md).</span></span>  
  
 <span data-ttu-id="4c23c-119">È possibile chiamare funzioni all'interno di una clausola `Where` per eseguire un calcolo o un'operazione su un valore dell'elemento corrente nella raccolta.</span><span class="sxs-lookup"><span data-stu-id="4c23c-119">You can call functions within a `Where` clause to perform a calculation or operation on a value from the current element in the collection.</span></span> <span data-ttu-id="4c23c-120">La chiamata di una funzione in una clausola `Where` può causare l'esecuzione immediata della query quando viene definita al posto di quando viene eseguito l'accesso.</span><span class="sxs-lookup"><span data-stu-id="4c23c-120">Calling a function in a `Where` clause can cause the query to be executed immediately when it is defined instead of when it is accessed.</span></span> <span data-ttu-id="4c23c-121">Per ulteriori informazioni sull'esecuzione di query, vedere [scrittura della prima query LINQ](../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md).</span><span class="sxs-lookup"><span data-stu-id="4c23c-121">For more information about query execution, see [Writing Your First LINQ Query](../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4c23c-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="4c23c-122">Example</span></span>  
 <span data-ttu-id="4c23c-123">Nell'espressione di query seguente viene utilizzata una clausola `From` per dichiarare una variabile di intervallo `cust` per ogni `Customer` oggetto nella raccolta `customers`.</span><span class="sxs-lookup"><span data-stu-id="4c23c-123">The following query expression uses a `From` clause to declare a range variable `cust` for each `Customer` object in the `customers` collection.</span></span> <span data-ttu-id="4c23c-124">La clausola `Where` usa la variabile di intervallo per limitare l'output ai clienti dall'area specificata.</span><span class="sxs-lookup"><span data-stu-id="4c23c-124">The `Where` clause uses the range variable to restrict the output to customers from the specified region.</span></span> <span data-ttu-id="4c23c-125">Il ciclo `For Each` Visualizza il nome della società per ogni cliente nel risultato della query.</span><span class="sxs-lookup"><span data-stu-id="4c23c-125">The `For Each` loop displays the company name for each customer in the query result.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#23)]  
  
## <a name="example"></a><span data-ttu-id="4c23c-126">Esempio</span><span class="sxs-lookup"><span data-stu-id="4c23c-126">Example</span></span>  
 <span data-ttu-id="4c23c-127">Nell'esempio seguente vengono utilizzati gli operatori logici `And` e `Or` nella clausola `Where`.</span><span class="sxs-lookup"><span data-stu-id="4c23c-127">The following example uses `And` and `Or` logical operators in the `Where` clause.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#31)]  
  
## <a name="see-also"></a><span data-ttu-id="4c23c-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4c23c-128">See also</span></span>

- [<span data-ttu-id="4c23c-129">Introduzione a LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4c23c-129">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="4c23c-130">Query</span><span class="sxs-lookup"><span data-stu-id="4c23c-130">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="4c23c-131">Clausola From</span><span class="sxs-lookup"><span data-stu-id="4c23c-131">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="4c23c-132">Clausola Select</span><span class="sxs-lookup"><span data-stu-id="4c23c-132">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="4c23c-133">Istruzione For Each...Next</span><span class="sxs-lookup"><span data-stu-id="4c23c-133">For Each...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-each-next-statement.md)
