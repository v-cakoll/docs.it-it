---
title: Eseguire query in una raccolta di oggetti
description: Come eseguire una query nelle raccolte.
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 11/30/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.assetid: 87a76f8a-0b58-4791-90ea-2fe0a30416c9
ms.openlocfilehash: 74d6c1f080c3e70867f5d2f074315bd1d8486bf0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="query-a-collection-of-objects"></a><span data-ttu-id="0c955-104">Eseguire query in una raccolta di oggetti</span><span class="sxs-lookup"><span data-stu-id="0c955-104">Query a collection of objects</span></span>
<span data-ttu-id="0c955-105">In questo esempio viene illustrato come eseguire una query semplice su un elenco di oggetti `Student`.</span><span class="sxs-lookup"><span data-stu-id="0c955-105">This example shows how to perform a simple query over a list of `Student` objects.</span></span> <span data-ttu-id="0c955-106">Ogni oggetto `Student` contiene informazioni di base sullo studente e un elenco che rappresenta i voti dello studente in quattro esami.</span><span class="sxs-lookup"><span data-stu-id="0c955-106">Each `Student` object contains some basic information about the student, and a list that represents the student's scores on four examinations.</span></span>  
  
 <span data-ttu-id="0c955-107">Questa applicazione viene usata come framework per molti altri esempi di questa sezione che usano la stessa origine dati `students`.</span><span class="sxs-lookup"><span data-stu-id="0c955-107">This application serves as the framework for many other examples in this section that use the same `students` data source.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0c955-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="0c955-108">Example</span></span>  
 <span data-ttu-id="0c955-109">La query seguente restituisce gli studenti che hanno ricevuto un punteggio pari o superiore a 90 nel primo esame.</span><span class="sxs-lookup"><span data-stu-id="0c955-109">The following query returns the students who received a score of 90 or greater on their first exam.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#15](../../../samples/snippets/csharp/concepts/linq/how-to-query-a-collection-of-objects_1.cs)]  
  
 <span data-ttu-id="0c955-110">Questa query è volutamente semplice per consentire la sperimentazione.</span><span class="sxs-lookup"><span data-stu-id="0c955-110">This query is intentionally simple to enable you to experiment.</span></span> <span data-ttu-id="0c955-111">Ad esempio, è possibile provare altre condizioni nella clausola `where` oppure usare una clausola `orderby` per ordinare i risultati.</span><span class="sxs-lookup"><span data-stu-id="0c955-111">For example, you can try more conditions in the `where` clause, or use an `orderby` clause to sort the results.</span></span>  
  

## <a name="see-also"></a><span data-ttu-id="0c955-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0c955-112">See also</span></span>  
 [<span data-ttu-id="0c955-113">Espressioni di query LINQ</span><span class="sxs-lookup"><span data-stu-id="0c955-113">LINQ Query Expressions</span></span>](index.md)  
 [<span data-ttu-id="0c955-114">Stringhe interpolate</span><span class="sxs-lookup"><span data-stu-id="0c955-114">Interpolated Strings</span></span>](../language-reference/keywords/interpolated-strings.md)
