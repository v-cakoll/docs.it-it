---
title: Eseguire query in una raccolta di oggetti (LINQ in C#)
description: Informazioni su come eseguire query in una raccolta usando LINQ in C#.
ms.date: 11/30/2016
ms.assetid: 87a76f8a-0b58-4791-90ea-2fe0a30416c9
ms.openlocfilehash: 7bc59e7009f9ae8d8f66c24e9519d9100404c9c4
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2018
ms.locfileid: "42935541"
---
# <a name="query-a-collection-of-objects"></a><span data-ttu-id="c2992-103">Eseguire query in una raccolta di oggetti</span><span class="sxs-lookup"><span data-stu-id="c2992-103">Query a collection of objects</span></span>

<span data-ttu-id="c2992-104">In questo esempio viene illustrato come eseguire una query semplice su un elenco di oggetti `Student`.</span><span class="sxs-lookup"><span data-stu-id="c2992-104">This example shows how to perform a simple query over a list of `Student` objects.</span></span> <span data-ttu-id="c2992-105">Ogni oggetto `Student` contiene informazioni di base sullo studente e un elenco che rappresenta i voti dello studente in quattro esami.</span><span class="sxs-lookup"><span data-stu-id="c2992-105">Each `Student` object contains some basic information about the student, and a list that represents the student's scores on four examinations.</span></span>  
  
<span data-ttu-id="c2992-106">Questa applicazione viene usata come framework per molti altri esempi di questa sezione che usano la stessa origine dati `students`.</span><span class="sxs-lookup"><span data-stu-id="c2992-106">This application serves as the framework for many other examples in this section that use the same `students` data source.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c2992-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="c2992-107">Example</span></span>

<span data-ttu-id="c2992-108">La query seguente restituisce gli studenti che hanno ricevuto un punteggio pari o superiore a 90 nel primo esame.</span><span class="sxs-lookup"><span data-stu-id="c2992-108">The following query returns the students who received a score of 90 or greater on their first exam.</span></span>  
  
[!code-csharp[csProgGuideLINQ#15](~/samples/snippets/csharp/concepts/linq/how-to-query-a-collection-of-objects_1.cs)]  
  
<span data-ttu-id="c2992-109">Questa query è volutamente semplice per consentire la sperimentazione.</span><span class="sxs-lookup"><span data-stu-id="c2992-109">This query is intentionally simple to enable you to experiment.</span></span> <span data-ttu-id="c2992-110">Ad esempio, è possibile provare altre condizioni nella clausola `where` oppure usare una clausola `orderby` per ordinare i risultati.</span><span class="sxs-lookup"><span data-stu-id="c2992-110">For example, you can try more conditions in the `where` clause, or use an `orderby` clause to sort the results.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2992-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c2992-111">See also</span></span>

- [<span data-ttu-id="c2992-112">LINQ (Language-Integrated Query)</span><span class="sxs-lookup"><span data-stu-id="c2992-112">Language Integrated Query (LINQ)</span></span>](index.md)  
- [<span data-ttu-id="c2992-113">Interpolazione di stringhe</span><span class="sxs-lookup"><span data-stu-id="c2992-113">String interpolation</span></span>](../language-reference/tokens/interpolated.md)