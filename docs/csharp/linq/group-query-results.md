---
title: Raggruppare i risultati di una query (LINQ in C#)
description: Informazioni su come raggruppare i risultati usando LINQ in C#.
ms.date: 12/01/2016
ms.assetid: 2e4ec27f-06fb-4de7-8973-0189906d4520
ms.openlocfilehash: 577a358c31fcf5346e7aab7a2e2b6be10fd1beff
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "61688462"
---
# <a name="group-query-results"></a><span data-ttu-id="a653a-103">Raggruppare i risultati di una query</span><span class="sxs-lookup"><span data-stu-id="a653a-103">Group query results</span></span>

<span data-ttu-id="a653a-104">Il raggruppamento è una delle funzionalità più efficace di LINQ.</span><span class="sxs-lookup"><span data-stu-id="a653a-104">Grouping is one of the most powerful capabilities of LINQ.</span></span> <span data-ttu-id="a653a-105">Negli esempi seguenti viene illustrato come raggruppare i dati in vari modi:</span><span class="sxs-lookup"><span data-stu-id="a653a-105">The following examples show how to group data in various ways:</span></span>

- <span data-ttu-id="a653a-106">In base a una singola proprietà.</span><span class="sxs-lookup"><span data-stu-id="a653a-106">By a single property.</span></span>

- <span data-ttu-id="a653a-107">In base alla prima lettera di una proprietà stringa.</span><span class="sxs-lookup"><span data-stu-id="a653a-107">By the first letter of a string property.</span></span>

- <span data-ttu-id="a653a-108">In base a un intervallo numerico calcolato.</span><span class="sxs-lookup"><span data-stu-id="a653a-108">By a computed numeric range.</span></span>

- <span data-ttu-id="a653a-109">In base a un predicato booleano o un'altra espressione.</span><span class="sxs-lookup"><span data-stu-id="a653a-109">By Boolean predicate or other expression.</span></span>

- <span data-ttu-id="a653a-110">In base a una chiave composta.</span><span class="sxs-lookup"><span data-stu-id="a653a-110">By a compound key.</span></span>

<span data-ttu-id="a653a-111">Le ultime due query proiettano i risultati in un tipo anonimo nuovo che contiene solo il nome e il cognome dello studente.</span><span class="sxs-lookup"><span data-stu-id="a653a-111">In addition, the last two queries project their results into a new anonymous type that contains only the student's first and last name.</span></span> <span data-ttu-id="a653a-112">Per altre informazioni, vedere [Clausola group](../language-reference/keywords/group-clause.md).</span><span class="sxs-lookup"><span data-stu-id="a653a-112">For more information, see the [group clause](../language-reference/keywords/group-clause.md).</span></span>

## <a name="example"></a><span data-ttu-id="a653a-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="a653a-113">Example</span></span>

<span data-ttu-id="a653a-114">In tutti gli esempi di questo argomento vengono usate le classi di supporto e le origini dati seguenti.</span><span class="sxs-lookup"><span data-stu-id="a653a-114">All the examples in this topic use the following helper classes and data sources.</span></span>

[!code-csharp[csProgGuideLINQ#15](~/samples/snippets/csharp/concepts/linq/how-to-group-query-results_1.cs)]

## <a name="example"></a><span data-ttu-id="a653a-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="a653a-115">Example</span></span>

<span data-ttu-id="a653a-116">Nell'esempio seguente viene illustrato come raggruppare gli elementi di origine usando una sola proprietà dell'elemento come chiave di gruppo.</span><span class="sxs-lookup"><span data-stu-id="a653a-116">The following example shows how to group source elements by using a single property of the element as the group key.</span></span> <span data-ttu-id="a653a-117">In questo caso la chiave è un oggetto `string`, il cognome dello studente.</span><span class="sxs-lookup"><span data-stu-id="a653a-117">In this case the key is a `string`, the student's last name.</span></span> <span data-ttu-id="a653a-118">È anche possibile usare una sottostringa per la chiave.</span><span class="sxs-lookup"><span data-stu-id="a653a-118">It is also possible to use a substring for the key.</span></span> <span data-ttu-id="a653a-119">L'operazione di raggruppamento usa l'operatore di confronto di uguaglianza predefinito per il tipo.</span><span class="sxs-lookup"><span data-stu-id="a653a-119">The grouping operation uses the default equality comparer for the type.</span></span>

<span data-ttu-id="a653a-120">Incollare il metodo seguente nella classe `StudentClass`.</span><span class="sxs-lookup"><span data-stu-id="a653a-120">Paste the following method into the `StudentClass` class.</span></span> <span data-ttu-id="a653a-121">Modificare l'istruzione di chiamata nel metodo `Main` in `sc.GroupBySingleProperty()`.</span><span class="sxs-lookup"><span data-stu-id="a653a-121">Change the calling statement in the `Main` method to `sc.GroupBySingleProperty()`.</span></span>

[!code-csharp[csProgGuideLINQ#17](~/samples/snippets/csharp/concepts/linq/how-to-group-query-results_2.cs)]

## <a name="example"></a><span data-ttu-id="a653a-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="a653a-122">Example</span></span>

<span data-ttu-id="a653a-123">Nell'esempio seguente viene illustrato come raggruppare gli elementi di origine usando un elemento diverso da una proprietà dell'oggetto per la chiave di gruppo.</span><span class="sxs-lookup"><span data-stu-id="a653a-123">The following example shows how to group source elements by using something other than a property of the object for the group key.</span></span> <span data-ttu-id="a653a-124">In questo esempio la chiave è la prima lettera del cognome dello studente.</span><span class="sxs-lookup"><span data-stu-id="a653a-124">In this example, the key is the first letter of the student's last name.</span></span>

<span data-ttu-id="a653a-125">Incollare il metodo seguente nella classe `StudentClass`.</span><span class="sxs-lookup"><span data-stu-id="a653a-125">Paste the following method into the `StudentClass` class.</span></span> <span data-ttu-id="a653a-126">Modificare l'istruzione di chiamata nel metodo `Main` in `sc.GroupBySubstring()`.</span><span class="sxs-lookup"><span data-stu-id="a653a-126">Change the calling statement in the `Main` method to `sc.GroupBySubstring()`.</span></span>

[!code-csharp[csProgGuideLINQ#18](~/samples/snippets/csharp/concepts/linq/how-to-group-query-results_3.cs)]

## <a name="example"></a><span data-ttu-id="a653a-127">Esempio</span><span class="sxs-lookup"><span data-stu-id="a653a-127">Example</span></span>

<span data-ttu-id="a653a-128">Nell'esempio seguente viene illustrato come raggruppare gli elementi di origine usando un intervallo numerico come chiave di gruppo.</span><span class="sxs-lookup"><span data-stu-id="a653a-128">The following example shows how to group source elements by using a numeric range as a group key.</span></span> <span data-ttu-id="a653a-129">La query proietta i risultati in un tipo anonimo che contiene solo il nome e il cognome e l'intervallo percentile al quale appartiene lo studente.</span><span class="sxs-lookup"><span data-stu-id="a653a-129">The query then projects the results into an anonymous type that contains only the first and last name and the percentile range to which the student belongs.</span></span> <span data-ttu-id="a653a-130">Viene usato un tipo anonimo perché non è necessario usare l'oggetto `Student` completo per visualizzare i risultati.</span><span class="sxs-lookup"><span data-stu-id="a653a-130">An anonymous type is used because it is not necessary to use the complete `Student` object to display the results.</span></span> <span data-ttu-id="a653a-131">`GetPercentile` è una funzione di supporto che consente di calcolare un percentile in base al voto medio dello studente.</span><span class="sxs-lookup"><span data-stu-id="a653a-131">`GetPercentile` is a helper function that calculates a percentile based on the student's average score.</span></span> <span data-ttu-id="a653a-132">Il metodo restituisce un numero intero compreso tra 0 e 10.</span><span class="sxs-lookup"><span data-stu-id="a653a-132">The method returns an integer between 0 and 10.</span></span>

[!code-csharp[csProgGuideLINQ#50](~/samples/snippets/csharp/concepts/linq/how-to-group-query-results_4.cs)]

<span data-ttu-id="a653a-133">Incollare il metodo seguente nella classe `StudentClass`.</span><span class="sxs-lookup"><span data-stu-id="a653a-133">Paste the following method into the `StudentClass` class.</span></span> <span data-ttu-id="a653a-134">Modificare l'istruzione di chiamata nel metodo `Main` in `sc.GroupByRange()`.</span><span class="sxs-lookup"><span data-stu-id="a653a-134">Change the calling statement in the `Main` method to `sc.GroupByRange()`.</span></span>

[!code-csharp[csProgGuideLINQ#19](~/samples/snippets/csharp/concepts/linq/how-to-group-query-results_5.cs)]

## <a name="example"></a><span data-ttu-id="a653a-135">Esempio</span><span class="sxs-lookup"><span data-stu-id="a653a-135">Example</span></span>

<span data-ttu-id="a653a-136">Nell'esempio seguente viene illustrato come raggruppare elementi di origine usando un'espressione di confronto booleana.</span><span class="sxs-lookup"><span data-stu-id="a653a-136">The following example shows how to group source elements by using a Boolean comparison expression.</span></span> <span data-ttu-id="a653a-137">In questo esempio l'espressione booleana consente di verificare se il voto medio degli esami di uno studente è maggiore di 75.</span><span class="sxs-lookup"><span data-stu-id="a653a-137">In this example, the Boolean expression tests whether a student's average exam score is greater than 75.</span></span> <span data-ttu-id="a653a-138">Come negli esempi precedenti, i risultati vengono proiettati in un tipo anonimo perché l'elemento di origine completo non è necessario.</span><span class="sxs-lookup"><span data-stu-id="a653a-138">As in previous examples, the results are projected into an anonymous type because the complete source element is not needed.</span></span> <span data-ttu-id="a653a-139">Si noti che le proprietà nel tipo anonimo diventano proprietà sul membro `Key` e sono accessibili tramite il nome quando la query viene eseguita.</span><span class="sxs-lookup"><span data-stu-id="a653a-139">Note that the properties in the anonymous type become properties on the `Key` member and can be accessed by name when the query is executed.</span></span>

<span data-ttu-id="a653a-140">Incollare il metodo seguente nella classe `StudentClass`.</span><span class="sxs-lookup"><span data-stu-id="a653a-140">Paste the following method into the `StudentClass` class.</span></span> <span data-ttu-id="a653a-141">Modificare l'istruzione di chiamata nel metodo `Main` in `sc.GroupByBoolean()`.</span><span class="sxs-lookup"><span data-stu-id="a653a-141">Change the calling statement in the `Main` method to `sc.GroupByBoolean()`.</span></span>

[!code-csharp[csProgGuideLINQ#20](~/samples/snippets/csharp/concepts/linq/how-to-group-query-results_6.cs)]

## <a name="example"></a><span data-ttu-id="a653a-142">Esempio</span><span class="sxs-lookup"><span data-stu-id="a653a-142">Example</span></span>

<span data-ttu-id="a653a-143">Nell'esempio seguente viene illustrato come usare un tipo anonimo per incapsulare una chiave che contiene più valori.</span><span class="sxs-lookup"><span data-stu-id="a653a-143">The following example shows how to use an anonymous type to encapsulate a key that contains multiple values.</span></span> <span data-ttu-id="a653a-144">In questo esempio il primo valore della chiave è la prima lettera del cognome dello studente.</span><span class="sxs-lookup"><span data-stu-id="a653a-144">In this example, the first key value is the first letter of the student's last name.</span></span> <span data-ttu-id="a653a-145">Il secondo valore della chiave è un valore booleano che specifica se lo studente ha ottenuto un voto superiore a 85 nel primo esame.</span><span class="sxs-lookup"><span data-stu-id="a653a-145">The second key value is a Boolean that specifies whether the student scored over 85 on the first exam.</span></span> <span data-ttu-id="a653a-146">È possibile ordinare i gruppi in base a qualsiasi proprietà nella chiave.</span><span class="sxs-lookup"><span data-stu-id="a653a-146">You can order the groups by any property in the key.</span></span>

<span data-ttu-id="a653a-147">Incollare il metodo seguente nella classe `StudentClass`.</span><span class="sxs-lookup"><span data-stu-id="a653a-147">Paste the following method into the `StudentClass` class.</span></span> <span data-ttu-id="a653a-148">Modificare l'istruzione di chiamata nel metodo `Main` in `sc.GroupByCompositeKey()`.</span><span class="sxs-lookup"><span data-stu-id="a653a-148">Change the calling statement in the `Main` method to `sc.GroupByCompositeKey()`.</span></span>

[!code-csharp[csProgGuideLINQ#21](~/samples/snippets/csharp/concepts/linq/how-to-group-query-results_7.cs)]

## <a name="see-also"></a><span data-ttu-id="a653a-149">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a653a-149">See also</span></span>

- <xref:System.Linq.Enumerable.GroupBy%2A>
- <xref:System.Linq.IGrouping%602>
- [<span data-ttu-id="a653a-150">Language Integrated Query (LINQ)</span><span class="sxs-lookup"><span data-stu-id="a653a-150">Language Integrated Query (LINQ)</span></span>](index.md)
- [<span data-ttu-id="a653a-151">Clausola group</span><span class="sxs-lookup"><span data-stu-id="a653a-151">group clause</span></span>](../language-reference/keywords/group-clause.md)
- [<span data-ttu-id="a653a-152">Tipi anonimi</span><span class="sxs-lookup"><span data-stu-id="a653a-152">Anonymous Types</span></span>](../programming-guide/classes-and-structs/anonymous-types.md)
- [<span data-ttu-id="a653a-153">Eseguire una sottoquery su un'operazione di raggruppamento</span><span class="sxs-lookup"><span data-stu-id="a653a-153">Perform a Subquery on a Grouping Operation</span></span>](perform-a-subquery-on-a-grouping-operation.md)
- [<span data-ttu-id="a653a-154">Creare un gruppo annidato</span><span class="sxs-lookup"><span data-stu-id="a653a-154">Create a Nested Group</span></span>](create-a-nested-group.md)
- [<span data-ttu-id="a653a-155">Raggruppamento dei dati</span><span class="sxs-lookup"><span data-stu-id="a653a-155">Grouping Data</span></span>](../programming-guide/concepts/linq/grouping-data.md)
