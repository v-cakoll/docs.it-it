---
title: Sintassi di espressione di query per operatori di query standard (C#)
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: e1e17ef2-68ff-4c26-b6e2-015668227fa5
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 30e994329234b8bd455f739694e50121bac63d5d
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="query-expression-syntax-for-standard-query-operators-c"></a><span data-ttu-id="db1fd-102">Sintassi di espressione di query per operatori di query standard (C#)</span><span class="sxs-lookup"><span data-stu-id="db1fd-102">Query Expression Syntax for Standard Query Operators (C#)</span></span>
<span data-ttu-id="db1fd-103">Alcuni degli operatori di query standard usati più di frequente dispongono di una sintassi dedicata delle parole chiave per i linguaggi C# che consente di chiamare gli operatori come parte di un'espressione di *query*.</span><span class="sxs-lookup"><span data-stu-id="db1fd-103">Some of the more frequently used standard query operators have dedicated C# language keyword syntax that enables them to be called as part of a *query expression*.</span></span> <span data-ttu-id="db1fd-104">Un'espressione di query rappresenta un modo diverso e più leggibile per esprimere una query rispetto alla sintassi equivalente *basata su metodo*.</span><span class="sxs-lookup"><span data-stu-id="db1fd-104">A query expression is a different, more readable form of expressing a query than its *method-based*  equivalent.</span></span> <span data-ttu-id="db1fd-105">Le clausole di espressione di query vengono convertite in chiamate ai metodi di query in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="db1fd-105">Query expression clauses are translated into calls to the query methods at compile time.</span></span>  
  
## <a name="query-expression-syntax-table"></a><span data-ttu-id="db1fd-106">Tabella della sintassi di espressione di query</span><span class="sxs-lookup"><span data-stu-id="db1fd-106">Query Expression Syntax Table</span></span>  
 <span data-ttu-id="db1fd-107">La tabella seguente elenca gli operatori di query standard che hanno clausole di espressione di query equivalenti.</span><span class="sxs-lookup"><span data-stu-id="db1fd-107">The following table lists the standard query operators that have equivalent query expression clauses.</span></span>  
  
|<span data-ttu-id="db1fd-108">Metodo</span><span class="sxs-lookup"><span data-stu-id="db1fd-108">Method</span></span>|<span data-ttu-id="db1fd-109">Sintassi di espressione della query C#</span><span class="sxs-lookup"><span data-stu-id="db1fd-109">C# Query Expression Syntax</span></span>|  
|------------|---------------------------------|  
|<xref:System.Linq.Enumerable.Cast%2A>|<span data-ttu-id="db1fd-110">Usare una variabile di intervallo tipizzata in modo esplicito, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="db1fd-110">Use an explicitly typed range variable, for example:</span></span><br /><br /> `from int i in numbers`<br /><br /> <span data-ttu-id="db1fd-111">Per altre informazioni, vedere [Clausola from](../../../../csharp/language-reference/keywords/from-clause.md).</span><span class="sxs-lookup"><span data-stu-id="db1fd-111">(For more information, see [from clause](../../../../csharp/language-reference/keywords/from-clause.md).)</span></span>|  
|<xref:System.Linq.Enumerable.GroupBy%2A>|`group … by`<br /><br /> <span data-ttu-id="db1fd-112">-oppure-</span><span class="sxs-lookup"><span data-stu-id="db1fd-112">-or-</span></span><br /><br /> `group … by … into …`<br /><br /> <span data-ttu-id="db1fd-113">Per altre informazioni, vedere [Clausola group](../../../../csharp/language-reference/keywords/group-clause.md).</span><span class="sxs-lookup"><span data-stu-id="db1fd-113">(For more information, see [group clause](../../../../csharp/language-reference/keywords/group-clause.md).)</span></span>|  
|<xref:System.Linq.Enumerable.GroupJoin%60%604%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Collections.Generic.IEnumerable%7B%60%601%7D%2CSystem.Func%7B%60%600%2C%60%602%7D%2CSystem.Func%7B%60%601%2C%60%602%7D%2CSystem.Func%7B%60%600%2CSystem.Collections.Generic.IEnumerable%7B%60%601%7D%2C%60%603%7D%29>|`join … in … on … equals … into …`<br /><br /> <span data-ttu-id="db1fd-114">Per altre informazioni, vedere [Clausola join](../../../../csharp/language-reference/keywords/join-clause.md).</span><span class="sxs-lookup"><span data-stu-id="db1fd-114">(For more information, see [join clause](../../../../csharp/language-reference/keywords/join-clause.md).)</span></span>|  
|<xref:System.Linq.Enumerable.Join%60%604%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Collections.Generic.IEnumerable%7B%60%601%7D%2CSystem.Func%7B%60%600%2C%60%602%7D%2CSystem.Func%7B%60%601%2C%60%602%7D%2CSystem.Func%7B%60%600%2C%60%601%2C%60%603%7D%29>|`join … in … on … equals …`<br /><br /> <span data-ttu-id="db1fd-115">Per altre informazioni, vedere [Clausola join](../../../../csharp/language-reference/keywords/join-clause.md).</span><span class="sxs-lookup"><span data-stu-id="db1fd-115">(For more information, see [join clause](../../../../csharp/language-reference/keywords/join-clause.md).)</span></span>|  
|<xref:System.Linq.Enumerable.OrderBy%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%29>|`orderby`<br /><br /> <span data-ttu-id="db1fd-116">Per altre informazioni, vedere [Clausola orderby](../../../../csharp/language-reference/keywords/orderby-clause.md).</span><span class="sxs-lookup"><span data-stu-id="db1fd-116">(For more information, see [orderby clause](../../../../csharp/language-reference/keywords/orderby-clause.md).)</span></span>|  
<xref:System.Linq.Enumerable.OrderByDescending%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%29>|`orderby … descending`<br /><br /> <span data-ttu-id="db1fd-117">Per altre informazioni, vedere [Clausola orderby](../../../../csharp/language-reference/keywords/orderby-clause.md).</span><span class="sxs-lookup"><span data-stu-id="db1fd-117">(For more information, see [orderby clause](../../../../csharp/language-reference/keywords/orderby-clause.md).)</span></span>|  
|<xref:System.Linq.Enumerable.Select%2A>|`select`<br /><br /> <span data-ttu-id="db1fd-118">Per altre informazioni, vedere [Clausola select](../../../../csharp/language-reference/keywords/select-clause.md).</span><span class="sxs-lookup"><span data-stu-id="db1fd-118">(For more information, see [select clause](../../../../csharp/language-reference/keywords/select-clause.md).)</span></span>|  
|<xref:System.Linq.Enumerable.SelectMany%2A>|<span data-ttu-id="db1fd-119">Più clausole `from`.</span><span class="sxs-lookup"><span data-stu-id="db1fd-119">Multiple `from` clauses.</span></span><br /><br /> <span data-ttu-id="db1fd-120">Per altre informazioni, vedere [Clausola from](../../../../csharp/language-reference/keywords/from-clause.md).</span><span class="sxs-lookup"><span data-stu-id="db1fd-120">(For more information, see [from clause](../../../../csharp/language-reference/keywords/from-clause.md).)</span></span>|  
|<xref:System.Linq.Enumerable.ThenBy%60%602%28System.Linq.IOrderedEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%29>|`orderby …, …`<br /><br /> <span data-ttu-id="db1fd-121">Per altre informazioni, vedere [Clausola orderby](../../../../csharp/language-reference/keywords/orderby-clause.md).</span><span class="sxs-lookup"><span data-stu-id="db1fd-121">(For more information, see [orderby clause](../../../../csharp/language-reference/keywords/orderby-clause.md).)</span></span>|  
|<xref:System.Linq.Enumerable.ThenByDescending%60%602%28System.Linq.IOrderedEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%29>|`orderby …, … descending`<br /><br /> <span data-ttu-id="db1fd-122">Per altre informazioni, vedere [Clausola orderby](../../../../csharp/language-reference/keywords/orderby-clause.md).</span><span class="sxs-lookup"><span data-stu-id="db1fd-122">(For more information, see [orderby clause](../../../../csharp/language-reference/keywords/orderby-clause.md).)</span></span>|  
|<xref:System.Linq.Enumerable.Where%2A>|`where`<br /><br /> <span data-ttu-id="db1fd-123">Per altre informazioni, vedere [Clausola where](../../../../csharp/language-reference/keywords/where-clause.md).</span><span class="sxs-lookup"><span data-stu-id="db1fd-123">(For more information, see [where clause](../../../../csharp/language-reference/keywords/where-clause.md).)</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="db1fd-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="db1fd-124">See Also</span></span>  
 <span data-ttu-id="db1fd-125"><xref:System.Linq.Enumerable></span><span class="sxs-lookup"><span data-stu-id="db1fd-125"><xref:System.Linq.Enumerable></span></span>   
 <span data-ttu-id="db1fd-126"><xref:System.Linq.Queryable></span><span class="sxs-lookup"><span data-stu-id="db1fd-126"><xref:System.Linq.Queryable></span></span>   
 <span data-ttu-id="db1fd-127">[Panoramica degli operatori query standard (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) </span><span class="sxs-lookup"><span data-stu-id="db1fd-127">[Standard Query Operators Overview (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) </span></span>  
 [<span data-ttu-id="db1fd-128">Classificazione degli operatori di query standard in base alla modalità di esecuzione (C#)</span><span class="sxs-lookup"><span data-stu-id="db1fd-128">Classification of Standard Query Operators by Manner of Execution (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/classification-of-standard-query-operators-by-manner-of-execution.md)

