---
title: 'Procedura: chiamare funzioni di database'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 79038efa-15bf-464a-83e2-35fe145252ce
ms.openlocfilehash: 4a18bbad4bf38c69f86a320d95e893a7680315fb
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43499900"
---
# <a name="how-to-call-database-functions"></a><span data-ttu-id="820e5-102">Procedura: chiamare funzioni di database</span><span class="sxs-lookup"><span data-stu-id="820e5-102">How to: Call Database Functions</span></span>
<span data-ttu-id="820e5-103">La classe <xref:System.Data.Objects.SqlClient.SqlFunctions> contiene metodi che espongono funzioni SQL Server da usare nelle query LINQ to Entities.</span><span class="sxs-lookup"><span data-stu-id="820e5-103">The <xref:System.Data.Objects.SqlClient.SqlFunctions> class contains methods that expose SQL Server functions to use in LINQ to Entities queries.</span></span> <span data-ttu-id="820e5-104">Quando si usano metodi <xref:System.Data.Objects.SqlClient.SqlFunctions> nelle query LINQ to Entities, le funzioni di database corrispondenti vengono eseguite nel database.</span><span class="sxs-lookup"><span data-stu-id="820e5-104">When you use <xref:System.Data.Objects.SqlClient.SqlFunctions> methods in LINQ to Entities queries, the corresponding database functions are executed in the database.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="820e5-105">Le funzioni di database che eseguono un calcolo su un set di valori e restituiscono un valore singolo (anche note come funzioni di database di aggregazione) possono essere richiamate direttamente.</span><span class="sxs-lookup"><span data-stu-id="820e5-105">Database functions that perform a calculation on a set of values and return a single value (also known as aggregate database functions) can be directly invoked.</span></span> <span data-ttu-id="820e5-106">Altre funzioni canoniche possono essere chiamate solo come parte di una query LINQ to Entities.</span><span class="sxs-lookup"><span data-stu-id="820e5-106">Other canonical functions can only be called as part of a LINQ to Entities query.</span></span> <span data-ttu-id="820e5-107">Per chiamare direttamente una funzione di aggregazione, è necessario passare un oggetto <xref:System.Data.Objects.ObjectQuery%601> alla funzione.</span><span class="sxs-lookup"><span data-stu-id="820e5-107">To call an aggregate function directly, you must pass an <xref:System.Data.Objects.ObjectQuery%601> to the function.</span></span> <span data-ttu-id="820e5-108">Per altre informazioni, vedere il secondo esempio che segue.</span><span class="sxs-lookup"><span data-stu-id="820e5-108">For more information, see the second example below.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="820e5-109">Questi metodi nella classe <xref:System.Data.Objects.SqlClient.SqlFunctions> sono specifici delle funzioni SQL Server.</span><span class="sxs-lookup"><span data-stu-id="820e5-109">The methods in the <xref:System.Data.Objects.SqlClient.SqlFunctions> class are specific to SQL Server functions.</span></span> <span data-ttu-id="820e5-110">Classi simili che espongono funzioni di database possono essere disponibili tramite altri provider.</span><span class="sxs-lookup"><span data-stu-id="820e5-110">Similar classes that expose database functions may be available through other providers.</span></span>  
  
## <a name="example"></a><span data-ttu-id="820e5-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="820e5-111">Example</span></span>  
 <span data-ttu-id="820e5-112">L'esempio seguente usa il [modello Sales di AdventureWorks](https://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832).</span><span class="sxs-lookup"><span data-stu-id="820e5-112">The following example uses the [AdventureWorks Sales Model](https://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832).</span></span> <span data-ttu-id="820e5-113">Nell'esempio viene eseguita una query LINQ to Entities che usa il metodo <xref:System.Data.Objects.SqlClient.SqlFunctions.CharIndex%2A> per restituire tutti i contatti il cui cognome inizia con "Si":</span><span class="sxs-lookup"><span data-stu-id="820e5-113">The example executes a LINQ to Entities query that uses the <xref:System.Data.Objects.SqlClient.SqlFunctions.CharIndex%2A> method to return all contacts whose last name starts with "Si":</span></span>  
  
 [!code-csharp[DP L2E CanonicalAndStoreFunctions#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e canonicalandstorefunctions/cs/program.cs#3)]
 [!code-vb[DP L2E CanonicalAndStoreFunctions#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e canonicalandstorefunctions/vb/module1.vb#3)]  
  
## <a name="example"></a><span data-ttu-id="820e5-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="820e5-114">Example</span></span>  
 <span data-ttu-id="820e5-115">L'esempio seguente usa il [modello Sales di AdventureWorks](https://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832).</span><span class="sxs-lookup"><span data-stu-id="820e5-115">The following example uses the [AdventureWorks Sales Model](https://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832).</span></span> <span data-ttu-id="820e5-116">Nell'esempio viene chiamato direttamente il metodo di aggregazione <xref:System.Data.Objects.SqlClient.SqlFunctions.ChecksumAggregate%2A>.</span><span class="sxs-lookup"><span data-stu-id="820e5-116">The example calls the aggregate <xref:System.Data.Objects.SqlClient.SqlFunctions.ChecksumAggregate%2A> method directly.</span></span> <span data-ttu-id="820e5-117">Si noti che alla funzione viene passato un oggetto <xref:System.Data.Objects.ObjectQuery%601>, che consente alla funzione di essere chiamata senza essere parte di una query LINQ to Entities.</span><span class="sxs-lookup"><span data-stu-id="820e5-117">Note that an <xref:System.Data.Objects.ObjectQuery%601> is passed to the function, which allows it to be called without being part of a LINQ to Entities query.</span></span>  
  
 [!code-csharp[DP L2E CanonicalAndStoreFunctions#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e canonicalandstorefunctions/cs/program.cs#4)]
 [!code-vb[DP L2E CanonicalAndStoreFunctions#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e canonicalandstorefunctions/vb/module1.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="820e5-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="820e5-118">See Also</span></span>  
 [<span data-ttu-id="820e5-119">Chiamata di funzioni in query di LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="820e5-119">Calling Functions in LINQ to Entities Queries</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/calling-functions-in-linq-to-entities-queries.md)  
 [<span data-ttu-id="820e5-120">Query in LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="820e5-120">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
