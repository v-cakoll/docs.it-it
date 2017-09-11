---
title: Ottenere una query da un metodo
description: Come ottenere una query.
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 11/30/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: db220f79-c35b-41f2-886c-cd068672d42d
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 747345f0a765bc6cbe947a2b0c7bc025eb599550
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-return-a-query-from-a-method-c-programming-guide"></a><span data-ttu-id="ac2b9-104">Procedura: ottenere una query da un metodo (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="ac2b9-104">How to: Return a Query from a Method (C# Programming Guide)</span></span>
<span data-ttu-id="ac2b9-105">In questo esempio viene illustrato come ottenere una query da un metodo come valore restituito e come parametro `out`.</span><span class="sxs-lookup"><span data-stu-id="ac2b9-105">This example shows how to return a query from a method as the return value and as an `out` parameter.</span></span>  
  
 <span data-ttu-id="ac2b9-106">Gli oggetti di query sono componibili, vale a dire che è possibile ottenere una query da un metodo.</span><span class="sxs-lookup"><span data-stu-id="ac2b9-106">Query objects are composable, meaning that you can return a query from a method.</span></span> <span data-ttu-id="ac2b9-107">Gli oggetti che rappresentano le query non memorizzano la raccolta risultante, ma piuttosto i passaggi da eseguire per ottenere i risultati quando necessario.</span><span class="sxs-lookup"><span data-stu-id="ac2b9-107">Objects that represent queries do not store the resulting collection, but rather the steps to produce the results when needed.</span></span> <span data-ttu-id="ac2b9-108">Il vantaggio di ottenere oggetti query dai metodi è che gli oggetti possono essere ulteriormente composti o modificati.</span><span class="sxs-lookup"><span data-stu-id="ac2b9-108">The advantage of returning query objects from methods is that they can be further composed or modified.</span></span> <span data-ttu-id="ac2b9-109">Di conseguenza, qualsiasi valore restituito o parametro `out` di un metodo che restituisce una query deve contenere anche quel tipo.</span><span class="sxs-lookup"><span data-stu-id="ac2b9-109">Therefore any return value or `out` parameter of a method that returns a query must also have that type.</span></span> <span data-ttu-id="ac2b9-110">Se un metodo materializza una query in un oggetto <xref:System.Collections.Generic.List%601> concreto o un tipo <xref:System.Array>, si ritiene che restituisca i risultati della query anziché la query stessa.</span><span class="sxs-lookup"><span data-stu-id="ac2b9-110">If a method materializes a query into a concrete <xref:System.Collections.Generic.List%601> or <xref:System.Array> type, it is considered to be returning the query results instead of the query itself.</span></span> <span data-ttu-id="ac2b9-111">Una variabile di query che viene restituita da un metodo può ancora essere composta o modificata.</span><span class="sxs-lookup"><span data-stu-id="ac2b9-111">A query variable that is returned from a method can still be composed or modified.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ac2b9-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="ac2b9-112">Example</span></span>  
 <span data-ttu-id="ac2b9-113">Nell'esempio seguente il primo metodo restituisce una query come valore restituito e il secondo metodo restituisce una query come parametro `out`.</span><span class="sxs-lookup"><span data-stu-id="ac2b9-113">In the following example, the first method returns a query as a return value, and the second method returns a query as an `out` parameter.</span></span> <span data-ttu-id="ac2b9-114">Notare che in entrambi i casi è una query che viene restituita, non i risultati della query.</span><span class="sxs-lookup"><span data-stu-id="ac2b9-114">Note that in both cases it is a query that is  returned, not query results.</span></span>  
  
 <span data-ttu-id="ac2b9-115">[!code-cs[csProgGuideLINQ#80](../../../samples/snippets/csharp/concepts/linq/how-to-return-a-query-from-a-method_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="ac2b9-115">[!code-cs[csProgGuideLINQ#80](../../../samples/snippets/csharp/concepts/linq/how-to-return-a-query-from-a-method_1.cs)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="ac2b9-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ac2b9-116">See Also</span></span>  
 [<span data-ttu-id="ac2b9-117">Espressioni di query LINQ</span><span class="sxs-lookup"><span data-stu-id="ac2b9-117">LINQ Query Expressions</span></span>](index.md)

