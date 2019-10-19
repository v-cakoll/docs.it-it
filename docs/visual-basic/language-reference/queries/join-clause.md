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
ms.openlocfilehash: b5211d0ed3f618013dc9fe764a6d7b2db8177c26
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582287"
---
# <a name="join-clause-visual-basic"></a><span data-ttu-id="894a4-102">Clausola Join (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="894a4-102">Join Clause (Visual Basic)</span></span>

<span data-ttu-id="894a4-103">Combina due raccolte in un'unica raccolta.</span><span class="sxs-lookup"><span data-stu-id="894a4-103">Combines two collections into a single collection.</span></span> <span data-ttu-id="894a4-104">L'operazione di join è basata sulle chiavi corrispondenti e usa l'operatore `Equals`.</span><span class="sxs-lookup"><span data-stu-id="894a4-104">The join operation is based on matching keys and uses the `Equals` operator.</span></span>

## <a name="syntax"></a><span data-ttu-id="894a4-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="894a4-105">Syntax</span></span>

```vb
Join element In collection _
  [ joinClause _ ]
  [ groupJoinClause ... _ ]
On key1 Equals key2 [ And key3 Equals key4 [... ]
```

## <a name="parts"></a><span data-ttu-id="894a4-106">Parti</span><span class="sxs-lookup"><span data-stu-id="894a4-106">Parts</span></span>

<span data-ttu-id="894a4-107">`element` Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="894a4-107">`element` Required.</span></span> <span data-ttu-id="894a4-108">Variabile di controllo per la raccolta da unire in join.</span><span class="sxs-lookup"><span data-stu-id="894a4-108">The control variable for the collection being joined.</span></span>

`collection`  
<span data-ttu-id="894a4-109">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="894a4-109">Required.</span></span> <span data-ttu-id="894a4-110">Raccolta da combinare con la raccolta identificata sul lato sinistro dell'operatore di `Join`.</span><span class="sxs-lookup"><span data-stu-id="894a4-110">The collection to combine with the collection identified on the left side of the `Join` operator.</span></span> <span data-ttu-id="894a4-111">Una clausola `Join` può essere annidata in un'altra clausola `Join` o in una clausola `Group Join`.</span><span class="sxs-lookup"><span data-stu-id="894a4-111">A `Join` clause can be nested in another `Join` clause, or in a `Group Join` clause.</span></span>

`joinClause`  
<span data-ttu-id="894a4-112">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="894a4-112">Optional.</span></span> <span data-ttu-id="894a4-113">Una o più clausole `Join` aggiuntive per perfezionare ulteriormente la query.</span><span class="sxs-lookup"><span data-stu-id="894a4-113">One or more additional `Join` clauses to further refine the query.</span></span>

`groupJoinClause`  
<span data-ttu-id="894a4-114">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="894a4-114">Optional.</span></span> <span data-ttu-id="894a4-115">Una o più clausole `Group Join` aggiuntive per perfezionare ulteriormente la query.</span><span class="sxs-lookup"><span data-stu-id="894a4-115">One or more additional `Group Join` clauses to further refine the query.</span></span>

<span data-ttu-id="894a4-116">`key1` `Equals` `key2`</span><span class="sxs-lookup"><span data-stu-id="894a4-116">`key1` `Equals` `key2`</span></span>  
<span data-ttu-id="894a4-117">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="894a4-117">Required.</span></span> <span data-ttu-id="894a4-118">Identifica le chiavi per le raccolte da unire in join.</span><span class="sxs-lookup"><span data-stu-id="894a4-118">Identifies keys for the collections being joined.</span></span> <span data-ttu-id="894a4-119">È necessario utilizzare l'operatore `Equals` per confrontare le chiavi delle raccolte da unire in join.</span><span class="sxs-lookup"><span data-stu-id="894a4-119">You must use the `Equals` operator to compare keys from the collections being joined.</span></span> <span data-ttu-id="894a4-120">È possibile combinare le condizioni di join usando l'operatore `And` per identificare più chiavi.</span><span class="sxs-lookup"><span data-stu-id="894a4-120">You can combine join conditions by using the `And` operator to identify multiple keys.</span></span> <span data-ttu-id="894a4-121">`key1` deve provenire dalla raccolta sul lato sinistro dell'operatore `Join`.</span><span class="sxs-lookup"><span data-stu-id="894a4-121">`key1` must be from the collection on the left side of the `Join` operator.</span></span> <span data-ttu-id="894a4-122">`key2` deve provenire dalla raccolta sul lato destro dell'operatore `Join`.</span><span class="sxs-lookup"><span data-stu-id="894a4-122">`key2` must be from the collection on the right side of the `Join` operator.</span></span>

<span data-ttu-id="894a4-123">Le chiavi utilizzate nella condizione di join possono essere espressioni che includono più di un elemento della raccolta.</span><span class="sxs-lookup"><span data-stu-id="894a4-123">The keys used in the join condition can be expressions that include more than one item from the collection.</span></span> <span data-ttu-id="894a4-124">Ogni espressione chiave può tuttavia contenere solo elementi della rispettiva raccolta.</span><span class="sxs-lookup"><span data-stu-id="894a4-124">However, each key expression can contain only items from its respective collection.</span></span>

## <a name="remarks"></a><span data-ttu-id="894a4-125">Note</span><span class="sxs-lookup"><span data-stu-id="894a4-125">Remarks</span></span>

<span data-ttu-id="894a4-126">La clausola `Join` combina due raccolte in base ai valori di chiave corrispondenti delle raccolte da unire in join.</span><span class="sxs-lookup"><span data-stu-id="894a4-126">The `Join` clause combines two collections based on matching key values from the collections being joined.</span></span> <span data-ttu-id="894a4-127">La raccolta risultante può contenere qualsiasi combinazione di valori della raccolta identificata sul lato sinistro dell'operatore `Join` e della raccolta identificata nella clausola `Join`.</span><span class="sxs-lookup"><span data-stu-id="894a4-127">The resulting collection can contain any combination of values from the collection identified on the left side of the `Join` operator and the collection identified in the `Join` clause.</span></span> <span data-ttu-id="894a4-128">La query restituirà solo i risultati per i quali viene soddisfatta la condizione specificata dall'operatore `Equals`.</span><span class="sxs-lookup"><span data-stu-id="894a4-128">The query will return only results for which the condition specified by the `Equals` operator is met.</span></span> <span data-ttu-id="894a4-129">Equivale a un `INNER JOIN` in SQL.</span><span class="sxs-lookup"><span data-stu-id="894a4-129">This is equivalent to an `INNER JOIN` in SQL.</span></span>

<span data-ttu-id="894a4-130">È possibile utilizzare più clausole `Join` in una query per unire due o più raccolte in una singola raccolta.</span><span class="sxs-lookup"><span data-stu-id="894a4-130">You can use multiple `Join` clauses in a query to join two or more collections into a single collection.</span></span>

<span data-ttu-id="894a4-131">È possibile eseguire un join implicito per combinare raccolte senza la clausola `Join`.</span><span class="sxs-lookup"><span data-stu-id="894a4-131">You can perform an implicit join to combine collections without the `Join` clause.</span></span> <span data-ttu-id="894a4-132">A tale scopo, includere più clausole `In` nella clausola `From` e specificare una clausola `Where` che identifichi le chiavi che si desidera utilizzare per il join.</span><span class="sxs-lookup"><span data-stu-id="894a4-132">To do this, include multiple `In` clauses in your `From` clause and specify a `Where` clause that identifies the keys that you want to use for the join.</span></span>

<span data-ttu-id="894a4-133">È possibile usare la clausola `Group Join` per combinare le raccolte in un'unica raccolta gerarchica.</span><span class="sxs-lookup"><span data-stu-id="894a4-133">You can use the `Group Join` clause to combine collections into a single hierarchical collection.</span></span> <span data-ttu-id="894a4-134">Questa operazione è simile a una `LEFT OUTER JOIN` in SQL.</span><span class="sxs-lookup"><span data-stu-id="894a4-134">This is like a `LEFT OUTER JOIN` in SQL.</span></span>

## <a name="example"></a><span data-ttu-id="894a4-135">Esempio</span><span class="sxs-lookup"><span data-stu-id="894a4-135">Example</span></span>

<span data-ttu-id="894a4-136">Nell'esempio di codice seguente viene eseguito un join implicito per combinare un elenco di clienti con i relativi ordini.</span><span class="sxs-lookup"><span data-stu-id="894a4-136">The following code example performs an implicit join to combine a list of customers with their orders.</span></span>

[!code-vb[VbSimpleQuerySamples#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#13)]

## <a name="example"></a><span data-ttu-id="894a4-137">Esempio</span><span class="sxs-lookup"><span data-stu-id="894a4-137">Example</span></span>

<span data-ttu-id="894a4-138">L'esempio di codice seguente unisce due raccolte usando la clausola `Join`.</span><span class="sxs-lookup"><span data-stu-id="894a4-138">The following code example joins two collections by using the `Join` clause.</span></span>

[!code-vb[VbSimpleQuerySamples#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples2.vb#12)]

<span data-ttu-id="894a4-139">In questo esempio verrà generato un output simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="894a4-139">This example will produce output similar to the following:</span></span>

`winlogon (968), Windows Logon`

`explorer (2424), File Explorer`

`cmd (5136), Command Window`

## <a name="example"></a><span data-ttu-id="894a4-140">Esempio</span><span class="sxs-lookup"><span data-stu-id="894a4-140">Example</span></span>

<span data-ttu-id="894a4-141">Nell'esempio di codice seguente vengono unite due raccolte utilizzando la clausola `Join` con due colonne chiave.</span><span class="sxs-lookup"><span data-stu-id="894a4-141">The following code example joins two collections by using the `Join` clause with two key columns.</span></span>

[!code-vb[VbSimpleQuerySamples#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples3.vb#17)]

<span data-ttu-id="894a4-142">Nell'esempio viene generato un output simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="894a4-142">The example will produce output similar to the following:</span></span>

`winlogon (968), Windows Logon, Priority = 13`

`cmd (700), Command Window, Priority = 8`

`explorer (2424), File Explorer, Priority = 8`

## <a name="see-also"></a><span data-ttu-id="894a4-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="894a4-143">See also</span></span>

- [<span data-ttu-id="894a4-144">Introduzione a LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="894a4-144">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="894a4-145">Query</span><span class="sxs-lookup"><span data-stu-id="894a4-145">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="894a4-146">Clausola Select</span><span class="sxs-lookup"><span data-stu-id="894a4-146">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="894a4-147">Clausola From</span><span class="sxs-lookup"><span data-stu-id="894a4-147">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="894a4-148">Clausola Group Join</span><span class="sxs-lookup"><span data-stu-id="894a4-148">Group Join Clause</span></span>](../../../visual-basic/language-reference/queries/group-join-clause.md)
- [<span data-ttu-id="894a4-149">Clausola Where</span><span class="sxs-lookup"><span data-stu-id="894a4-149">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)
