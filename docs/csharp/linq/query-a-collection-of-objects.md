---
title: Eseguire query in una raccolta di oggetti
description: Come eseguire una query nelle raccolte.
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 11/30/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 87a76f8a-0b58-4791-90ea-2fe0a30416c9
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 9e08f2e5877ffe24f5a238ab19abb9760cb442f2
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="query-a-collection-of-objects"></a><span data-ttu-id="efaf6-104">Eseguire query in una raccolta di oggetti</span><span class="sxs-lookup"><span data-stu-id="efaf6-104">Query a collection of objects</span></span>
<span data-ttu-id="efaf6-105">In questo esempio viene illustrato come eseguire una query semplice su un elenco di oggetti `Student`.</span><span class="sxs-lookup"><span data-stu-id="efaf6-105">This example shows how to perform a simple query over a list of `Student` objects.</span></span> <span data-ttu-id="efaf6-106">Ogni oggetto `Student` contiene informazioni di base sullo studente e un elenco che rappresenta i voti dello studente in quattro esami.</span><span class="sxs-lookup"><span data-stu-id="efaf6-106">Each `Student` object contains some basic information about the student, and a list that represents the student's scores on four examinations.</span></span>  
  
 <span data-ttu-id="efaf6-107">Questa applicazione viene usata come framework per molti altri esempi di questa sezione che usano la stessa origine dati `students`.</span><span class="sxs-lookup"><span data-stu-id="efaf6-107">This application serves as the framework for many other examples in this section that use the same `students` data source.</span></span>  
  
## <a name="example"></a><span data-ttu-id="efaf6-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="efaf6-108">Example</span></span>  
 <span data-ttu-id="efaf6-109">La query seguente restituisce gli studenti che hanno ricevuto un punteggio pari o superiore a 90 nel primo esame.</span><span class="sxs-lookup"><span data-stu-id="efaf6-109">The following query returns the students who received a score of 90 or greater on their first exam.</span></span>  
  
 <span data-ttu-id="efaf6-110">[!code-cs[csProgGuideLINQ#15](../../../samples/snippets/csharp/concepts/linq/how-to-query-a-collection-of-objects_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="efaf6-110">[!code-cs[csProgGuideLINQ#15](../../../samples/snippets/csharp/concepts/linq/how-to-query-a-collection-of-objects_1.cs)]</span></span>  
  
 <span data-ttu-id="efaf6-111">Questa query è volutamente semplice per consentire la sperimentazione.</span><span class="sxs-lookup"><span data-stu-id="efaf6-111">This query is intentionally simple to enable you to experiment.</span></span> <span data-ttu-id="efaf6-112">Ad esempio, è possibile provare altre condizioni nella clausola `where` oppure usare una clausola `orderby` per ordinare i risultati.</span><span class="sxs-lookup"><span data-stu-id="efaf6-112">For example, you can try more conditions in the `where` clause, or use an `orderby` clause to sort the results.</span></span>  
  

## <a name="see-also"></a><span data-ttu-id="efaf6-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="efaf6-113">See also</span></span>  
 [<span data-ttu-id="efaf6-114">Espressioni di query LINQ</span><span class="sxs-lookup"><span data-stu-id="efaf6-114">LINQ Query Expressions</span></span>](index.md)

