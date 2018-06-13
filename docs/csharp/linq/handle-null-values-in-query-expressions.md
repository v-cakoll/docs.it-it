---
title: Gestire i valori Null nelle espressioni di query
description: Come gestire i valori Null nelle espressioni di query.
ms.date: 12/1/2016
ms.assetid: ac63ae8b-724d-4251-9334-528f4e884ae7
ms.openlocfilehash: ecd174462ef51a6dd7b7696abb9e111fc32d9ec7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33272387"
---
# <a name="handle-null-values-in-query-expressions"></a><span data-ttu-id="4f508-103">Gestire i valori Null nelle espressioni di query</span><span class="sxs-lookup"><span data-stu-id="4f508-103">Handle null values in query expressions</span></span>

<span data-ttu-id="4f508-104">In questo esempio viene illustrato come gestire i possibili valori Null nelle raccolte di origine.</span><span class="sxs-lookup"><span data-stu-id="4f508-104">This example shows how to handle possible null values in source collections.</span></span> <span data-ttu-id="4f508-105">Una raccolta di oggetti, ad esempio <xref:System.Collections.Generic.IEnumerable%601>, può contenere elementi il cui valore è [Null](../language-reference/keywords/null.md).</span><span class="sxs-lookup"><span data-stu-id="4f508-105">An object collection such as an <xref:System.Collections.Generic.IEnumerable%601> can contain elements whose value is [null](../language-reference/keywords/null.md).</span></span> <span data-ttu-id="4f508-106">Se una raccolta di origine è Null o contiene un elemento il cui valore è Null e la query non gestisce valori Null, verrà generata un'eccezione <xref:System.NullReferenceException> quando si esegue la query.</span><span class="sxs-lookup"><span data-stu-id="4f508-106">If a source collection is null or contains an element whose value is null, and your query does not handle null values, a <xref:System.NullReferenceException> will be thrown when you execute the query.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4f508-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="4f508-107">Example</span></span>

 <span data-ttu-id="4f508-108">È possibile codificare in modo sicuro per evitare un'eccezione di riferimento Null come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="4f508-108">You can code defensively to avoid a null reference exception as shown in the following example:</span></span>  
  
 [!code-csharp[csProgGuideLINQ#82](../../../samples/snippets/csharp/concepts/linq/how-to-handle-null-values-in-query-expressions_1.cs)]  
  
 <span data-ttu-id="4f508-109">Nell'esempio precedente la clausola `where` esclude tutti gli elementi Null nella sequenza di categorie.</span><span class="sxs-lookup"><span data-stu-id="4f508-109">In the previous example, the `where` clause filters out all null elements in the categories sequence.</span></span> <span data-ttu-id="4f508-110">Questa tecnica è indipendente dal controllo Null nella clausola join.</span><span class="sxs-lookup"><span data-stu-id="4f508-110">This technique is independent of the null check in the join clause.</span></span> <span data-ttu-id="4f508-111">In questo esempio è possibile usare l'espressione condizionale con Null poiché `Products.CategoryID` è di tipo `int?`, vale a dire una sintassi abbreviata di `Nullable<int>`.</span><span class="sxs-lookup"><span data-stu-id="4f508-111">The conditional expression with null in this example works because `Products.CategoryID` is of type `int?` which is shorthand for `Nullable<int>`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4f508-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="4f508-112">Example</span></span>

 <span data-ttu-id="4f508-113">Se in una clausola join solo una delle chiavi di confronto è un tipo di valore nullable, è possibile eseguire il cast delle altre chiavi a un tipo nullable nell'espressione di query.</span><span class="sxs-lookup"><span data-stu-id="4f508-113">In a join clause, if only one of the comparison keys is a nullable value type, you can cast the other to a nullable type in the query expression.</span></span> <span data-ttu-id="4f508-114">Nell'esempio seguente si supponga che `EmployeeID` sia una colonna contenente valori di tipo `int?`:</span><span class="sxs-lookup"><span data-stu-id="4f508-114">In the following example, assume that `EmployeeID` is a column that contains values of type `int?`:</span></span>  
  
 [!code-csharp[csProgGuideLINQ#83](../../../samples/snippets/csharp/concepts/linq/how-to-handle-null-values-in-query-expressions_2.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="4f508-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4f508-115">See also</span></span>  
 <xref:System.Nullable%601>  
 [<span data-ttu-id="4f508-116">Espressioni di query LINQ</span><span class="sxs-lookup"><span data-stu-id="4f508-116">LINQ query expressions</span></span>](index.md)  
 [<span data-ttu-id="4f508-117">Tipi nullable</span><span class="sxs-lookup"><span data-stu-id="4f508-117">Nullable types</span></span>](../programming-guide/nullable-types/index.md)
