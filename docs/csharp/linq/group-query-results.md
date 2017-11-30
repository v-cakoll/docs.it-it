---
title: Raggruppare i risultati di una query
description: Come raggruppare i risultati.
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 12/1/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.assetid: 2e4ec27f-06fb-4de7-8973-0189906d4520
ms.openlocfilehash: ca68cf96a2c27bbd1999d5445c14fc93e8e2566c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="group-query-results"></a><span data-ttu-id="a5e8f-104">Raggruppare i risultati di una query</span><span class="sxs-lookup"><span data-stu-id="a5e8f-104">Group query results</span></span>

<span data-ttu-id="a5e8f-105">Il raggruppamento è una delle funzionalità più efficace di LINQ.</span><span class="sxs-lookup"><span data-stu-id="a5e8f-105">Grouping is one of the most powerful capabilities of LINQ.</span></span> <span data-ttu-id="a5e8f-106">Negli esempi seguenti viene illustrato come raggruppare i dati in vari modi:</span><span class="sxs-lookup"><span data-stu-id="a5e8f-106">The following examples show how to group data in various ways:</span></span>  
  
-   <span data-ttu-id="a5e8f-107">In base a una singola proprietà.</span><span class="sxs-lookup"><span data-stu-id="a5e8f-107">By a single property.</span></span>  
  
-   <span data-ttu-id="a5e8f-108">In base alla prima lettera di una proprietà stringa.</span><span class="sxs-lookup"><span data-stu-id="a5e8f-108">By the first letter of a string property.</span></span>  
  
-   <span data-ttu-id="a5e8f-109">In base a un intervallo numerico calcolato.</span><span class="sxs-lookup"><span data-stu-id="a5e8f-109">By a computed numeric range.</span></span>  
  
-   <span data-ttu-id="a5e8f-110">In base a un predicato booleano o un'altra espressione.</span><span class="sxs-lookup"><span data-stu-id="a5e8f-110">By Boolean predicate or other expression.</span></span>  
  
-   <span data-ttu-id="a5e8f-111">In base a una chiave composta.</span><span class="sxs-lookup"><span data-stu-id="a5e8f-111">By a compound key.</span></span>  
  
 <span data-ttu-id="a5e8f-112">Le ultime due query proiettano i risultati in un tipo anonimo nuovo che contiene solo il nome e il cognome dello studente.</span><span class="sxs-lookup"><span data-stu-id="a5e8f-112">In addition, the last two queries project their results into a new anonymous type that contains only the student's first and last name.</span></span> <span data-ttu-id="a5e8f-113">Per altre informazioni, vedere [Clausola group](../language-reference/keywords/group-clause.md).</span><span class="sxs-lookup"><span data-stu-id="a5e8f-113">For more information, see the [group clause](../language-reference/keywords/group-clause.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a5e8f-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="a5e8f-114">Example</span></span>  
 <span data-ttu-id="a5e8f-115">In tutti gli esempi di questo argomento vengono usate le classi di supporto e le origini dati seguenti.</span><span class="sxs-lookup"><span data-stu-id="a5e8f-115">All the examples in this topic use the following helper classes and data sources.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#15](../../../samples/snippets/csharp/concepts/linq/how-to-group-query-results_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="a5e8f-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="a5e8f-116">Example</span></span>  
 <span data-ttu-id="a5e8f-117">Nell'esempio seguente viene illustrato come raggruppare gli elementi di origine usando una sola proprietà dell'elemento come chiave di gruppo.</span><span class="sxs-lookup"><span data-stu-id="a5e8f-117">The following example shows how to group source elements by using a single property of the element as the group key.</span></span> <span data-ttu-id="a5e8f-118">In questo caso la chiave è un oggetto `string`, il cognome dello studente.</span><span class="sxs-lookup"><span data-stu-id="a5e8f-118">In this case the key is a `string`, the student's last name.</span></span> <span data-ttu-id="a5e8f-119">È anche possibile usare una sottostringa per la chiave.</span><span class="sxs-lookup"><span data-stu-id="a5e8f-119">It is also possible to use a substring for the key.</span></span> <span data-ttu-id="a5e8f-120">L'operazione di raggruppamento usa l'operatore di confronto di uguaglianza predefinito per il tipo.</span><span class="sxs-lookup"><span data-stu-id="a5e8f-120">The grouping operation uses the default equality comparer for the type.</span></span>  
  
 <span data-ttu-id="a5e8f-121">Incollare il metodo seguente nella classe `StudentClass`.</span><span class="sxs-lookup"><span data-stu-id="a5e8f-121">Paste the following method into the `StudentClass` class.</span></span> <span data-ttu-id="a5e8f-122">Modificare l'istruzione di chiamata nel metodo `Main` in `sc.GroupBySingleProperty()`.</span><span class="sxs-lookup"><span data-stu-id="a5e8f-122">Change the calling statement in the `Main` method to `sc.GroupBySingleProperty()`.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#17](../../../samples/snippets/csharp/concepts/linq/how-to-group-query-results_2.cs)]  
  
## <a name="example"></a><span data-ttu-id="a5e8f-123">Esempio</span><span class="sxs-lookup"><span data-stu-id="a5e8f-123">Example</span></span>  
 <span data-ttu-id="a5e8f-124">Nell'esempio seguente viene illustrato come raggruppare gli elementi di origine usando un elemento diverso da una proprietà dell'oggetto per la chiave di gruppo.</span><span class="sxs-lookup"><span data-stu-id="a5e8f-124">The following example shows how to group source elements by using something other than a property of the object for the group key.</span></span> <span data-ttu-id="a5e8f-125">In questo esempio la chiave è la prima lettera del cognome dello studente.</span><span class="sxs-lookup"><span data-stu-id="a5e8f-125">In this example, the key is the first letter of the student's last name.</span></span>  
  
 <span data-ttu-id="a5e8f-126">Incollare il metodo seguente nella classe `StudentClass`.</span><span class="sxs-lookup"><span data-stu-id="a5e8f-126">Paste the following method into the `StudentClass` class.</span></span> <span data-ttu-id="a5e8f-127">Modificare l'istruzione di chiamata nel metodo `Main` in `sc.GroupBySubstring()`.</span><span class="sxs-lookup"><span data-stu-id="a5e8f-127">Change the calling statement in the `Main` method to `sc.GroupBySubstring()`.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#18](../../../samples/snippets/csharp/concepts/linq/how-to-group-query-results_3.cs)]  
  
## <a name="example"></a><span data-ttu-id="a5e8f-128">Esempio</span><span class="sxs-lookup"><span data-stu-id="a5e8f-128">Example</span></span>  
 <span data-ttu-id="a5e8f-129">Nell'esempio seguente viene illustrato come raggruppare gli elementi di origine usando un intervallo numerico come chiave di gruppo.</span><span class="sxs-lookup"><span data-stu-id="a5e8f-129">The following example shows how to group source elements by using a numeric range as a group key.</span></span> <span data-ttu-id="a5e8f-130">La query proietta i risultati in un tipo anonimo che contiene solo il nome e il cognome e l'intervallo percentile al quale appartiene lo studente.</span><span class="sxs-lookup"><span data-stu-id="a5e8f-130">The query then projects the results into an anonymous type that contains only the first and last name and the percentile range to which the student belongs.</span></span> <span data-ttu-id="a5e8f-131">Viene usato un tipo anonimo perché non è necessario usare l'oggetto `Student` completo per visualizzare i risultati.</span><span class="sxs-lookup"><span data-stu-id="a5e8f-131">An anonymous type is used because it is not necessary to use the complete `Student` object to display the results.</span></span> <span data-ttu-id="a5e8f-132">`GetPercentile` è una funzione di supporto che consente di calcolare un percentile in base al voto medio dello studente.</span><span class="sxs-lookup"><span data-stu-id="a5e8f-132">`GetPercentile` is a helper function that calculates a percentile based on the student's average score.</span></span> <span data-ttu-id="a5e8f-133">Il metodo restituisce un numero intero compreso tra 0 e 10.</span><span class="sxs-lookup"><span data-stu-id="a5e8f-133">The method returns an integer between 0 and 10.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#50](../../../samples/snippets/csharp/concepts/linq/how-to-group-query-results_4.cs)]  
  
 <span data-ttu-id="a5e8f-134">Incollare il metodo seguente nella classe `StudentClass`.</span><span class="sxs-lookup"><span data-stu-id="a5e8f-134">Paste the following method into the `StudentClass` class.</span></span> <span data-ttu-id="a5e8f-135">Modificare l'istruzione di chiamata nel metodo `Main` in `sc.GroupByRange()`.</span><span class="sxs-lookup"><span data-stu-id="a5e8f-135">Change the calling statement in the `Main` method to `sc.GroupByRange()`.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#19](../../../samples/snippets/csharp/concepts/linq/how-to-group-query-results_5.cs)]  
  
## <a name="example"></a><span data-ttu-id="a5e8f-136">Esempio</span><span class="sxs-lookup"><span data-stu-id="a5e8f-136">Example</span></span>  
 <span data-ttu-id="a5e8f-137">Nell'esempio seguente viene illustrato come raggruppare elementi di origine usando un'espressione di confronto booleana.</span><span class="sxs-lookup"><span data-stu-id="a5e8f-137">The following example shows how to group source elements by using a Boolean comparison expression.</span></span> <span data-ttu-id="a5e8f-138">In questo esempio l'espressione booleana consente di verificare se il voto medio degli esami di uno studente è maggiore di 75.</span><span class="sxs-lookup"><span data-stu-id="a5e8f-138">In this example, the Boolean expression tests whether a student's average exam score is greater than 75.</span></span> <span data-ttu-id="a5e8f-139">Come negli esempi precedenti, i risultati vengono proiettati in un tipo anonimo perché l'elemento di origine completo non è necessario.</span><span class="sxs-lookup"><span data-stu-id="a5e8f-139">As in previous examples, the results are projected into an anonymous type because the complete source element is not needed.</span></span> <span data-ttu-id="a5e8f-140">Si noti che le proprietà nel tipo anonimo diventano proprietà sul membro `Key` e sono accessibili tramite il nome quando la query viene eseguita.</span><span class="sxs-lookup"><span data-stu-id="a5e8f-140">Note that the properties in the anonymous type become properties on the `Key` member and can be accessed by name when the query is executed.</span></span>  
  
 <span data-ttu-id="a5e8f-141">Incollare il metodo seguente nella classe `StudentClass`.</span><span class="sxs-lookup"><span data-stu-id="a5e8f-141">Paste the following method into the `StudentClass` class.</span></span> <span data-ttu-id="a5e8f-142">Modificare l'istruzione di chiamata nel metodo `Main` in `sc.GroupByBoolean()`.</span><span class="sxs-lookup"><span data-stu-id="a5e8f-142">Change the calling statement in the `Main` method to `sc.GroupByBoolean()`.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#20](../../../samples/snippets/csharp/concepts/linq/how-to-group-query-results_6.cs)]  
  
## <a name="example"></a><span data-ttu-id="a5e8f-143">Esempio</span><span class="sxs-lookup"><span data-stu-id="a5e8f-143">Example</span></span>  
 <span data-ttu-id="a5e8f-144">Nell'esempio seguente viene illustrato come usare un tipo anonimo per incapsulare una chiave che contiene più valori.</span><span class="sxs-lookup"><span data-stu-id="a5e8f-144">The following example shows how to use an anonymous type to encapsulate a key that contains multiple values.</span></span> <span data-ttu-id="a5e8f-145">In questo esempio il primo valore della chiave è la prima lettera del cognome dello studente.</span><span class="sxs-lookup"><span data-stu-id="a5e8f-145">In this example, the first key value is the first letter of the student's last name.</span></span> <span data-ttu-id="a5e8f-146">Il secondo valore della chiave è un valore booleano che specifica se lo studente ha ottenuto un voto superiore a 85 nel primo esame.</span><span class="sxs-lookup"><span data-stu-id="a5e8f-146">The second key value is a Boolean that specifies whether the student scored over 85 on the first exam.</span></span> <span data-ttu-id="a5e8f-147">È possibile ordinare i gruppi in base a qualsiasi proprietà nella chiave.</span><span class="sxs-lookup"><span data-stu-id="a5e8f-147">You can order the groups by any property in the key.</span></span>  
  
 <span data-ttu-id="a5e8f-148">Incollare il metodo seguente nella classe `StudentClass`.</span><span class="sxs-lookup"><span data-stu-id="a5e8f-148">Paste the following method into the `StudentClass` class.</span></span> <span data-ttu-id="a5e8f-149">Modificare l'istruzione di chiamata nel metodo `Main` in `sc.GroupByCompositeKey()`.</span><span class="sxs-lookup"><span data-stu-id="a5e8f-149">Change the calling statement in the `Main` method to `sc.GroupByCompositeKey()`.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#21](../../../samples/snippets/csharp/concepts/linq/how-to-group-query-results_7.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="a5e8f-150">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a5e8f-150">See also</span></span>  
 <xref:System.Linq.Enumerable.GroupBy%2A>  
 <xref:System.Linq.IGrouping%602>  
 [<span data-ttu-id="a5e8f-151">Espressioni di query LINQ</span><span class="sxs-lookup"><span data-stu-id="a5e8f-151">LINQ Query Expressions</span></span>](index.md)  
 [<span data-ttu-id="a5e8f-152">Clausola group</span><span class="sxs-lookup"><span data-stu-id="a5e8f-152">group clause</span></span>](../language-reference/keywords/group-clause.md)  
 [<span data-ttu-id="a5e8f-153">Tipi anonimi</span><span class="sxs-lookup"><span data-stu-id="a5e8f-153">Anonymous Types</span></span>](../programming-guide/classes-and-structs/anonymous-types.md)  
 [<span data-ttu-id="a5e8f-154">Eseguire una sottoquery su un'operazione di raggruppamento</span><span class="sxs-lookup"><span data-stu-id="a5e8f-154">Perform a Subquery on a Grouping Operation</span></span>](perform-a-subquery-on-a-grouping-operation.md)  
 [<span data-ttu-id="a5e8f-155">Creare un gruppo annidato</span><span class="sxs-lookup"><span data-stu-id="a5e8f-155">Create a Nested Group</span></span>](create-a-nested-group.md)  
 [<span data-ttu-id="a5e8f-156">Raggruppamento dei dati</span><span class="sxs-lookup"><span data-stu-id="a5e8f-156">Grouping Data</span></span>](../programming-guide/concepts/linq/grouping-data.md)
