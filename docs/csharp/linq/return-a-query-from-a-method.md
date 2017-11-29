---
title: Ottenere una query da un metodo
description: Come ottenere una query.
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 11/30/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.assetid: db220f79-c35b-41f2-886c-cd068672d42d
ms.openlocfilehash: c1b69e3f5f0cd2c50ae80d2454e6b7f13dc30344
ms.sourcegitcommit: 7e99f66ef09d2903e22c789c67ff5a10aa953b2f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/18/2017
---
# <a name="how-to-return-a-query-from-a-method-c-programming-guide"></a><span data-ttu-id="0103c-104">Procedura: ottenere una query da un metodo (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="0103c-104">How to: Return a Query from a Method (C# Programming Guide)</span></span>
<span data-ttu-id="0103c-105">In questo esempio viene illustrato come ottenere una query da un metodo come valore restituito e come parametro `out`.</span><span class="sxs-lookup"><span data-stu-id="0103c-105">This example shows how to return a query from a method as the return value and as an `out` parameter.</span></span>  
  
 <span data-ttu-id="0103c-106">Gli oggetti di query sono componibili, vale a dire che è possibile ottenere una query da un metodo.</span><span class="sxs-lookup"><span data-stu-id="0103c-106">Query objects are composable, meaning that you can return a query from a method.</span></span> <span data-ttu-id="0103c-107">Gli oggetti che rappresentano le query non memorizzano la raccolta risultante, ma piuttosto i passaggi da eseguire per ottenere i risultati quando necessario.</span><span class="sxs-lookup"><span data-stu-id="0103c-107">Objects that represent queries do not store the resulting collection, but rather the steps to produce the results when needed.</span></span> <span data-ttu-id="0103c-108">Il vantaggio di ottenere oggetti query dai metodi è che gli oggetti possono essere ulteriormente composti o modificati.</span><span class="sxs-lookup"><span data-stu-id="0103c-108">The advantage of returning query objects from methods is that they can be further composed or modified.</span></span> <span data-ttu-id="0103c-109">Di conseguenza, qualsiasi valore restituito o parametro `out` di un metodo che restituisce una query deve contenere anche quel tipo.</span><span class="sxs-lookup"><span data-stu-id="0103c-109">Therefore any return value or `out` parameter of a method that returns a query must also have that type.</span></span> <span data-ttu-id="0103c-110">Se un metodo materializza una query in un oggetto <xref:System.Collections.Generic.List%601> concreto o un tipo <xref:System.Array>, si ritiene che restituisca i risultati della query anziché la query stessa.</span><span class="sxs-lookup"><span data-stu-id="0103c-110">If a method materializes a query into a concrete <xref:System.Collections.Generic.List%601> or <xref:System.Array> type, it is considered to be returning the query results instead of the query itself.</span></span> <span data-ttu-id="0103c-111">Una variabile di query che viene restituita da un metodo può ancora essere composta o modificata.</span><span class="sxs-lookup"><span data-stu-id="0103c-111">A query variable that is returned from a method can still be composed or modified.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0103c-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="0103c-112">Example</span></span>  
 <span data-ttu-id="0103c-113">Nell'esempio seguente il primo metodo restituisce una query come valore restituito e il secondo metodo restituisce una query come parametro `out`.</span><span class="sxs-lookup"><span data-stu-id="0103c-113">In the following example, the first method returns a query as a return value, and the second method returns a query as an `out` parameter.</span></span> <span data-ttu-id="0103c-114">Notare che in entrambi i casi è una query che viene restituita, non i risultati della query.</span><span class="sxs-lookup"><span data-stu-id="0103c-114">Note that in both cases it is a query that is  returned, not query results.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#80](../../../samples/snippets/csharp/concepts/linq/how-to-return-a-query-from-a-method_1.cs)]  

## <a name="see-also"></a><span data-ttu-id="0103c-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0103c-115">See Also</span></span>  
 [<span data-ttu-id="0103c-116">Espressioni di query LINQ</span><span class="sxs-lookup"><span data-stu-id="0103c-116">LINQ Query Expressions</span></span>](index.md)
