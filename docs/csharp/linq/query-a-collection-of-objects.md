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
ms.openlocfilehash: a62e5c6324d15376f1b42ad078eeb883b05ef14f
ms.sourcegitcommit: 935d5267c44f9bce801468ef95f44572f1417e8c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/28/2018
---
# <a name="query-a-collection-of-objects"></a><span data-ttu-id="fa6f4-104">Eseguire query in una raccolta di oggetti</span><span class="sxs-lookup"><span data-stu-id="fa6f4-104">Query a collection of objects</span></span>
<span data-ttu-id="fa6f4-105">In questo esempio viene illustrato come eseguire una query semplice su un elenco di oggetti `Student`.</span><span class="sxs-lookup"><span data-stu-id="fa6f4-105">This example shows how to perform a simple query over a list of `Student` objects.</span></span> <span data-ttu-id="fa6f4-106">Ogni oggetto `Student` contiene informazioni di base sullo studente e un elenco che rappresenta i voti dello studente in quattro esami.</span><span class="sxs-lookup"><span data-stu-id="fa6f4-106">Each `Student` object contains some basic information about the student, and a list that represents the student's scores on four examinations.</span></span>  
  
 <span data-ttu-id="fa6f4-107">Questa applicazione viene usata come framework per molti altri esempi di questa sezione che usano la stessa origine dati `students`.</span><span class="sxs-lookup"><span data-stu-id="fa6f4-107">This application serves as the framework for many other examples in this section that use the same `students` data source.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fa6f4-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="fa6f4-108">Example</span></span>  
 <span data-ttu-id="fa6f4-109">La query seguente restituisce gli studenti che hanno ricevuto un punteggio pari o superiore a 90 nel primo esame.</span><span class="sxs-lookup"><span data-stu-id="fa6f4-109">The following query returns the students who received a score of 90 or greater on their first exam.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#15](../../../samples/snippets/csharp/concepts/linq/how-to-query-a-collection-of-objects_1.cs)]  
  
 <span data-ttu-id="fa6f4-110">Questa query è volutamente semplice per consentire la sperimentazione.</span><span class="sxs-lookup"><span data-stu-id="fa6f4-110">This query is intentionally simple to enable you to experiment.</span></span> <span data-ttu-id="fa6f4-111">Ad esempio, è possibile provare altre condizioni nella clausola `where` oppure usare una clausola `orderby` per ordinare i risultati.</span><span class="sxs-lookup"><span data-stu-id="fa6f4-111">For example, you can try more conditions in the `where` clause, or use an `orderby` clause to sort the results.</span></span>  
  

## <a name="see-also"></a><span data-ttu-id="fa6f4-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fa6f4-112">See also</span></span>  
 [<span data-ttu-id="fa6f4-113">Espressioni di query LINQ</span><span class="sxs-lookup"><span data-stu-id="fa6f4-113">LINQ Query Expressions</span></span>](index.md)  
 [<span data-ttu-id="fa6f4-114">Interpolazione di stringhe</span><span class="sxs-lookup"><span data-stu-id="fa6f4-114">String interpolation</span></span>](../language-reference/tokens/interpolated.md)
