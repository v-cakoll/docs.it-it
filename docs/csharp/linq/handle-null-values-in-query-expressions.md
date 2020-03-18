---
title: Gestire valori null nelle espressioni di query (LINQ in C#)
description: Informazioni su come gestire i valori Null nelle espressioni di query LINQ in C#.
ms.date: 12/01/2016
ms.assetid: ac63ae8b-724d-4251-9334-528f4e884ae7
ms.openlocfilehash: c9a3aaec05fa029a8db66826bdcb4a1d106176e3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "73736864"
---
# <a name="handle-null-values-in-query-expressions"></a><span data-ttu-id="b056e-103">Gestire i valori Null nelle espressioni di query</span><span class="sxs-lookup"><span data-stu-id="b056e-103">Handle null values in query expressions</span></span>

<span data-ttu-id="b056e-104">In questo esempio viene illustrato come gestire i possibili valori Null nelle raccolte di origine.</span><span class="sxs-lookup"><span data-stu-id="b056e-104">This example shows how to handle possible null values in source collections.</span></span> <span data-ttu-id="b056e-105">Una raccolta di oggetti, ad esempio <xref:System.Collections.Generic.IEnumerable%601>, può contenere elementi il cui valore è [Null](../language-reference/keywords/null.md).</span><span class="sxs-lookup"><span data-stu-id="b056e-105">An object collection such as an <xref:System.Collections.Generic.IEnumerable%601> can contain elements whose value is [null](../language-reference/keywords/null.md).</span></span> <span data-ttu-id="b056e-106">Se una raccolta di origine è Null o contiene un elemento il cui valore è Null e la query non gestisce valori Null, verrà generata un'eccezione <xref:System.NullReferenceException> quando si esegue la query.</span><span class="sxs-lookup"><span data-stu-id="b056e-106">If a source collection is null or contains an element whose value is null, and your query does not handle null values, a <xref:System.NullReferenceException> will be thrown when you execute the query.</span></span>

## <a name="example"></a><span data-ttu-id="b056e-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="b056e-107">Example</span></span>

<span data-ttu-id="b056e-108">È possibile codificare in modo sicuro per evitare un'eccezione di riferimento Null come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="b056e-108">You can code defensively to avoid a null reference exception as shown in the following example:</span></span>

[!code-csharp[csProgGuideLINQ#82](~/samples/snippets/csharp/concepts/linq/how-to-handle-null-values-in-query-expressions_1.cs)]

<span data-ttu-id="b056e-109">Nell'esempio precedente la clausola `where` esclude tutti gli elementi Null nella sequenza di categorie.</span><span class="sxs-lookup"><span data-stu-id="b056e-109">In the previous example, the `where` clause filters out all null elements in the categories sequence.</span></span> <span data-ttu-id="b056e-110">Questa tecnica è indipendente dal controllo Null nella clausola join.</span><span class="sxs-lookup"><span data-stu-id="b056e-110">This technique is independent of the null check in the join clause.</span></span> <span data-ttu-id="b056e-111">In questo esempio è possibile usare l'espressione condizionale con Null poiché `Products.CategoryID` è di tipo `int?`, vale a dire una sintassi abbreviata di `Nullable<int>`.</span><span class="sxs-lookup"><span data-stu-id="b056e-111">The conditional expression with null in this example works because `Products.CategoryID` is of type `int?` which is shorthand for `Nullable<int>`.</span></span>

## <a name="example"></a><span data-ttu-id="b056e-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="b056e-112">Example</span></span>

<span data-ttu-id="b056e-113">Se in una clausola join solo una delle chiavi di confronto è un tipo di valore nullable, è possibile eseguire il cast delle altre chiavi a un tipo nullable nell'espressione di query.</span><span class="sxs-lookup"><span data-stu-id="b056e-113">In a join clause, if only one of the comparison keys is a nullable value type, you can cast the other to a nullable type in the query expression.</span></span> <span data-ttu-id="b056e-114">Nell'esempio seguente si supponga che `EmployeeID` sia una colonna contenente valori di tipo `int?`:</span><span class="sxs-lookup"><span data-stu-id="b056e-114">In the following example, assume that `EmployeeID` is a column that contains values of type `int?`:</span></span>

[!code-csharp[csProgGuideLINQ#83](~/samples/snippets/csharp/concepts/linq/how-to-handle-null-values-in-query-expressions_2.cs)]

## <a name="see-also"></a><span data-ttu-id="b056e-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b056e-115">See also</span></span>

- <xref:System.Nullable%601>
- [<span data-ttu-id="b056e-116">Language Integrated Query (LINQ)</span><span class="sxs-lookup"><span data-stu-id="b056e-116">Language Integrated Query (LINQ)</span></span>](index.md)
- [<span data-ttu-id="b056e-117">tipi di valore nullable</span><span class="sxs-lookup"><span data-stu-id="b056e-117">Nullable value types</span></span>](../language-reference/builtin-types/nullable-value-types.md)
