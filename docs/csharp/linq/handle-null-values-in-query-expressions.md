---
title: Gestire i valori Null nelle espressioni di query
description: Come gestire i valori Null nelle espressioni di query.
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 12/1/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: ac63ae8b-724d-4251-9334-528f4e884ae7
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: f4f189504c57c9c01268b10bc96ad3c9af49ddbd
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="handle-null-values-in-query-expressions"></a><span data-ttu-id="bc9f2-104">Gestire i valori Null nelle espressioni di query</span><span class="sxs-lookup"><span data-stu-id="bc9f2-104">Handle null values in query expressions</span></span>

<span data-ttu-id="bc9f2-105">In questo esempio viene illustrato come gestire i possibili valori Null nelle raccolte di origine.</span><span class="sxs-lookup"><span data-stu-id="bc9f2-105">This example shows how to handle possible null values in source collections.</span></span> <span data-ttu-id="bc9f2-106">Una raccolta di oggetti, ad esempio <xref:System.Collections.Generic.IEnumerable%601>, può contenere elementi il cui valore è [Null](../language-reference/keywords/null.md).</span><span class="sxs-lookup"><span data-stu-id="bc9f2-106">An object collection such as an <xref:System.Collections.Generic.IEnumerable%601> can contain elements whose value is [null](../language-reference/keywords/null.md).</span></span> <span data-ttu-id="bc9f2-107">Se una raccolta di origine è Null o contiene un elemento il cui valore è Null e la query non gestisce valori Null, verrà generata un'eccezione <xref:System.NullReferenceException> quando si esegue la query.</span><span class="sxs-lookup"><span data-stu-id="bc9f2-107">If a source collection is null or contains an element whose value is null, and your query does not handle null values, a <xref:System.NullReferenceException> will be thrown when you execute the query.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bc9f2-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="bc9f2-108">Example</span></span>

 <span data-ttu-id="bc9f2-109">È possibile codificare in modo sicuro per evitare un'eccezione di riferimento Null come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="bc9f2-109">You can code defensively to avoid a null reference exception as shown in the following example:</span></span>  
  
 <span data-ttu-id="bc9f2-110">[!code-cs[csProgGuideLINQ#82](../../../samples/snippets/csharp/concepts/linq/how-to-handle-null-values-in-query-expressions_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="bc9f2-110">[!code-cs[csProgGuideLINQ#82](../../../samples/snippets/csharp/concepts/linq/how-to-handle-null-values-in-query-expressions_1.cs)]</span></span>  
  
 <span data-ttu-id="bc9f2-111">Nell'esempio precedente la clausola `where` esclude tutti gli elementi Null nella sequenza di categorie.</span><span class="sxs-lookup"><span data-stu-id="bc9f2-111">In the previous example, the `where` clause filters out all null elements in the categories sequence.</span></span> <span data-ttu-id="bc9f2-112">Questa tecnica è indipendente dal controllo Null nella clausola join.</span><span class="sxs-lookup"><span data-stu-id="bc9f2-112">This technique is independent of the null check in the join clause.</span></span> <span data-ttu-id="bc9f2-113">In questo esempio è possibile usare l'espressione condizionale con Null poiché `Products.CategoryID` è di tipo `int?`, vale a dire una sintassi abbreviata di `Nullable<int>`.</span><span class="sxs-lookup"><span data-stu-id="bc9f2-113">The conditional expression with null in this example works because `Products.CategoryID` is of type `int?` which is shorthand for `Nullable<int>`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bc9f2-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="bc9f2-114">Example</span></span>

 <span data-ttu-id="bc9f2-115">Se in una clausola join solo una delle chiavi di confronto è un tipo di valore nullable, è possibile eseguire il cast delle altre chiavi a un tipo nullable nell'espressione di query.</span><span class="sxs-lookup"><span data-stu-id="bc9f2-115">In a join clause, if only one of the comparison keys is a nullable value type, you can cast the other to a nullable type in the query expression.</span></span> <span data-ttu-id="bc9f2-116">Nell'esempio seguente si supponga che `EmployeeID` sia una colonna contenente valori di tipo `int?`:</span><span class="sxs-lookup"><span data-stu-id="bc9f2-116">In the following example, assume that `EmployeeID` is a column that contains values of type `int?`:</span></span>  
  
 <span data-ttu-id="bc9f2-117">[!code-cs[csProgGuideLINQ#83](../../../samples/snippets/csharp/concepts/linq/how-to-handle-null-values-in-query-expressions_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="bc9f2-117">[!code-cs[csProgGuideLINQ#83](../../../samples/snippets/csharp/concepts/linq/how-to-handle-null-values-in-query-expressions_2.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc9f2-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bc9f2-118">See also</span></span>  
 <span data-ttu-id="bc9f2-119"><xref:System.Nullable%601></span><span class="sxs-lookup"><span data-stu-id="bc9f2-119"><xref:System.Nullable%601></span></span>   
 <span data-ttu-id="bc9f2-120">[Espressioni di query LINQ](index.md) </span><span class="sxs-lookup"><span data-stu-id="bc9f2-120">[LINQ query expressions](index.md) </span></span>  
 [<span data-ttu-id="bc9f2-121">Tipi nullable</span><span class="sxs-lookup"><span data-stu-id="bc9f2-121">Nullable types</span></span>](../programming-guide/nullable-types/index.md)

