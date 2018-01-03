---
title: Chiamata di funzioni in query di LINQ to Entities
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 12a525a9-727c-4464-a0c7-71a0ef541792
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: b4989fcce44f6081dba52cd17d0349c87197d508
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="calling-functions-in-linq-to-entities-queries"></a><span data-ttu-id="bc69e-102">Chiamata di funzioni in query di LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="bc69e-102">Calling Functions in LINQ to Entities Queries</span></span>
<span data-ttu-id="bc69e-103">Negli argomenti di questa sezione viene illustrato come chiamare le funzioni nelle LINQ to Entities.</span><span class="sxs-lookup"><span data-stu-id="bc69e-103">The topics in this section describe how to call functions in LINQ to Entities queries.</span></span>  
  
 <span data-ttu-id="bc69e-104">Le classi <xref:System.Data.Objects.EntityFunctions> e <xref:System.Data.Objects.SqlClient.SqlFunctions> forniscono l'accesso alle funzioni canoniche e di database come parte di Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="bc69e-104">The <xref:System.Data.Objects.EntityFunctions> and <xref:System.Data.Objects.SqlClient.SqlFunctions> classes provide access to canonical and database functions as part of the Entity Framework.</span></span> <span data-ttu-id="bc69e-105">Per ulteriori informazioni, vedere [procedura: chiamare funzioni canoniche](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-canonical-functions.md) e [procedura: chiamare funzioni di Database](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-database-functions.md).</span><span class="sxs-lookup"><span data-stu-id="bc69e-105">For more information, see [How to: Call Canonical Functions](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-canonical-functions.md) and [How to: Call Database Functions](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-database-functions.md).</span></span>  
  
 <span data-ttu-id="bc69e-106">Il processo per la chiamata di una funzione personalizzata richiede tre passaggi di base:</span><span class="sxs-lookup"><span data-stu-id="bc69e-106">The process for calling a custom function requires three basic steps:</span></span>  
  
1.  <span data-ttu-id="bc69e-107">Definire una funzione nel modello concettuale o dichiarare una funzione nel modello di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="bc69e-107">Define a function in your conceptual model or declare a function in your storage model.</span></span>  
  
2.  <span data-ttu-id="bc69e-108">Aggiungere un metodo all'applicazione ed eseguirne il mapping alla funzione nel modello con un oggetto <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute>.</span><span class="sxs-lookup"><span data-stu-id="bc69e-108">Add a method to your application and map it to the function in the model with an <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute>.</span></span>  
  
3.  <span data-ttu-id="bc69e-109">Chiamare la funzione in una query LINQ to Entities.</span><span class="sxs-lookup"><span data-stu-id="bc69e-109">Call the function in a LINQ to Entities query.</span></span>  
  
 <span data-ttu-id="bc69e-110">Per altre informazioni, vedere gli argomenti in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="bc69e-110">For more information, see the topics in this section.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="bc69e-111">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="bc69e-111">In This Section</span></span>  
 [<span data-ttu-id="bc69e-112">Procedura: Chiamare funzioni canoniche</span><span class="sxs-lookup"><span data-stu-id="bc69e-112">How to: Call Canonical Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-canonical-functions.md)  
  
 [<span data-ttu-id="bc69e-113">Procedura: Chiamare funzioni di database</span><span class="sxs-lookup"><span data-stu-id="bc69e-113">How to: Call Database Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-database-functions.md)  
  
 [<span data-ttu-id="bc69e-114">Procedura: Chiamare funzioni di database personalizzate</span><span class="sxs-lookup"><span data-stu-id="bc69e-114">How to: Call Custom Database Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-custom-database-functions.md)  
  
 [<span data-ttu-id="bc69e-115">Procedura: Chiamare funzioni definite dal modello in query</span><span class="sxs-lookup"><span data-stu-id="bc69e-115">How to: Call Model-Defined Functions in Queries</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-model-defined-functions-in-queries.md)  
  
 [<span data-ttu-id="bc69e-116">Procedura: Chiamare funzioni definite dal modello come metodi di oggetto</span><span class="sxs-lookup"><span data-stu-id="bc69e-116">How to: Call Model-Defined Functions as Object Methods</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-model-defined-functions-as-object-methods.md)  
  
## <a name="see-also"></a><span data-ttu-id="bc69e-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bc69e-117">See Also</span></span>  
 [<span data-ttu-id="bc69e-118">Query in LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="bc69e-118">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)  
 [<span data-ttu-id="bc69e-119">Funzioni canoniche</span><span class="sxs-lookup"><span data-stu-id="bc69e-119">Canonical Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md)  
 [<span data-ttu-id="bc69e-120">Cenni preliminari sui file con estensione edmx</span><span class="sxs-lookup"><span data-stu-id="bc69e-120">.edmx File Overview</span></span>](http://msdn.microsoft.com/en-us/f4c8e7ce-1db6-417e-9759-15f8b55155d4)  
 [<span data-ttu-id="bc69e-121">Procedura: definire le funzioni personalizzate nel modello concettuale</span><span class="sxs-lookup"><span data-stu-id="bc69e-121">How to: Define Custom Functions in the Conceptual Model</span></span>](http://msdn.microsoft.com/en-us/0dad7b8b-58f6-4271-b238-f34810d68e5f)
