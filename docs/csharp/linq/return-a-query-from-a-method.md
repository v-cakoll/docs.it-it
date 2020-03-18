---
title: Ottenere una query da un metodo
description: Come ottenere una query.
ms.date: 11/30/2016
ms.assetid: db220f79-c35b-41f2-886c-cd068672d42d
ms.openlocfilehash: 1df533770f76301432b104d6f8398f1687750cce
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "73972518"
---
# <a name="how-to-return-a-query-from-a-method-c-programming-guide"></a><span data-ttu-id="b938b-103">Come restituire una query da un metodo (Guida per programmatori C</span><span class="sxs-lookup"><span data-stu-id="b938b-103">How to return a query from a method (C# Programming Guide)</span></span>
<span data-ttu-id="b938b-104">In questo esempio viene illustrato come ottenere una query da un metodo come valore restituito e come parametro `out`.</span><span class="sxs-lookup"><span data-stu-id="b938b-104">This example shows how to return a query from a method as the return value and as an `out` parameter.</span></span>  
  
 <span data-ttu-id="b938b-105">Gli oggetti di query sono componibili, vale a dire che è possibile ottenere una query da un metodo.</span><span class="sxs-lookup"><span data-stu-id="b938b-105">Query objects are composable, meaning that you can return a query from a method.</span></span> <span data-ttu-id="b938b-106">Gli oggetti che rappresentano le query non memorizzano la raccolta risultante, ma piuttosto i passaggi da eseguire per ottenere i risultati quando necessario.</span><span class="sxs-lookup"><span data-stu-id="b938b-106">Objects that represent queries do not store the resulting collection, but rather the steps to produce the results when needed.</span></span> <span data-ttu-id="b938b-107">Il vantaggio di ottenere oggetti query dai metodi è che gli oggetti possono essere ulteriormente composti o modificati.</span><span class="sxs-lookup"><span data-stu-id="b938b-107">The advantage of returning query objects from methods is that they can be further composed or modified.</span></span> <span data-ttu-id="b938b-108">Di conseguenza, qualsiasi valore restituito o parametro `out` di un metodo che restituisce una query deve contenere anche quel tipo.</span><span class="sxs-lookup"><span data-stu-id="b938b-108">Therefore any return value or `out` parameter of a method that returns a query must also have that type.</span></span> <span data-ttu-id="b938b-109">Se un metodo materializza una query in un oggetto <xref:System.Collections.Generic.List%601> concreto o un tipo <xref:System.Array>, si ritiene che restituisca i risultati della query anziché la query stessa.</span><span class="sxs-lookup"><span data-stu-id="b938b-109">If a method materializes a query into a concrete <xref:System.Collections.Generic.List%601> or <xref:System.Array> type, it is considered to be returning the query results instead of the query itself.</span></span> <span data-ttu-id="b938b-110">Una variabile di query che viene restituita da un metodo può ancora essere composta o modificata.</span><span class="sxs-lookup"><span data-stu-id="b938b-110">A query variable that is returned from a method can still be composed or modified.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b938b-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="b938b-111">Example</span></span>  
 <span data-ttu-id="b938b-112">Nell'esempio seguente il primo metodo restituisce una query come valore restituito e il secondo metodo restituisce una query come parametro `out`.</span><span class="sxs-lookup"><span data-stu-id="b938b-112">In the following example, the first method returns a query as a return value, and the second method returns a query as an `out` parameter.</span></span> <span data-ttu-id="b938b-113">Notare che in entrambi i casi è una query che viene restituita, non i risultati della query.</span><span class="sxs-lookup"><span data-stu-id="b938b-113">Note that in both cases it is a query that is  returned, not query results.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#80](~/samples/snippets/csharp/concepts/linq/how-to-return-a-query-from-a-method_1.cs)]  

## <a name="see-also"></a><span data-ttu-id="b938b-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b938b-114">See also</span></span>

- [<span data-ttu-id="b938b-115">Language Integrated Query (LINQ)</span><span class="sxs-lookup"><span data-stu-id="b938b-115">Language Integrated Query (LINQ)</span></span>](index.md)
