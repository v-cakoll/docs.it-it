---
title: Chiamata di funzioni in query di LINQ to Entities
description: Usare questi articoli per vedere come le classi EntityFunctions e SqlFunctions forniscono l'accesso alle funzioni canoniche e di database come parte del Entity Framework.
ms.date: 03/30/2017
ms.assetid: 12a525a9-727c-4464-a0c7-71a0ef541792
ms.openlocfilehash: faa6406713592f10e5e7371cd73f29bec4b03b7b
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286857"
---
# <a name="calling-functions-in-linq-to-entities-queries"></a><span data-ttu-id="8a775-103">Chiamata di funzioni in query di LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="8a775-103">Calling Functions in LINQ to Entities Queries</span></span>
<span data-ttu-id="8a775-104">Negli argomenti di questa sezione viene illustrato come chiamare le funzioni nelle LINQ to Entities.</span><span class="sxs-lookup"><span data-stu-id="8a775-104">The topics in this section describe how to call functions in LINQ to Entities queries.</span></span>  
  
 <span data-ttu-id="8a775-105">Le classi <xref:System.Data.Objects.EntityFunctions> e <xref:System.Data.Objects.SqlClient.SqlFunctions> forniscono l'accesso alle funzioni canoniche e di database come parte di Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="8a775-105">The <xref:System.Data.Objects.EntityFunctions> and <xref:System.Data.Objects.SqlClient.SqlFunctions> classes provide access to canonical and database functions as part of the Entity Framework.</span></span> <span data-ttu-id="8a775-106">Per altre informazioni, vedere [procedura: chiamare funzioni canoniche](how-to-call-canonical-functions.md) e [procedura: chiamare funzioni di database](how-to-call-database-functions.md).</span><span class="sxs-lookup"><span data-stu-id="8a775-106">For more information, see [How to: Call Canonical Functions](how-to-call-canonical-functions.md) and [How to: Call Database Functions](how-to-call-database-functions.md).</span></span>  
  
 <span data-ttu-id="8a775-107">Il processo per la chiamata di una funzione personalizzata richiede tre passaggi di base:</span><span class="sxs-lookup"><span data-stu-id="8a775-107">The process for calling a custom function requires three basic steps:</span></span>  
  
1. <span data-ttu-id="8a775-108">Definire una funzione nel modello concettuale o dichiarare una funzione nel modello di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="8a775-108">Define a function in your conceptual model or declare a function in your storage model.</span></span>  
  
2. <span data-ttu-id="8a775-109">Aggiungere un metodo all'applicazione ed eseguirne il mapping alla funzione nel modello con un oggetto <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute>.</span><span class="sxs-lookup"><span data-stu-id="8a775-109">Add a method to your application and map it to the function in the model with an <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute>.</span></span>  
  
3. <span data-ttu-id="8a775-110">Chiamare la funzione in una query LINQ to Entities.</span><span class="sxs-lookup"><span data-stu-id="8a775-110">Call the function in a LINQ to Entities query.</span></span>  
  
 <span data-ttu-id="8a775-111">Per altre informazioni, vedere gli argomenti in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="8a775-111">For more information, see the topics in this section.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8a775-112">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="8a775-112">In This Section</span></span>  
 [<span data-ttu-id="8a775-113">Procedura: chiamare funzioni canoniche</span><span class="sxs-lookup"><span data-stu-id="8a775-113">How to: Call Canonical Functions</span></span>](how-to-call-canonical-functions.md)  
  
 [<span data-ttu-id="8a775-114">Procedura: chiamare funzioni di database</span><span class="sxs-lookup"><span data-stu-id="8a775-114">How to: Call Database Functions</span></span>](how-to-call-database-functions.md)  
  
 [<span data-ttu-id="8a775-115">Procedura: chiamare funzioni di database personalizzate</span><span class="sxs-lookup"><span data-stu-id="8a775-115">How to: Call Custom Database Functions</span></span>](how-to-call-custom-database-functions.md)  
  
 [<span data-ttu-id="8a775-116">Procedura: Chiamare funzioni definite dal modello in query</span><span class="sxs-lookup"><span data-stu-id="8a775-116">How to: Call Model-Defined Functions in Queries</span></span>](how-to-call-model-defined-functions-in-queries.md)  
  
 [<span data-ttu-id="8a775-117">Procedura: Chiamare funzioni definite dal modello come metodi di oggetto</span><span class="sxs-lookup"><span data-stu-id="8a775-117">How to: Call Model-Defined Functions as Object Methods</span></span>](how-to-call-model-defined-functions-as-object-methods.md)  
  
## <a name="see-also"></a><span data-ttu-id="8a775-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8a775-118">See also</span></span>

- [<span data-ttu-id="8a775-119">Query in LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="8a775-119">Queries in LINQ to Entities</span></span>](queries-in-linq-to-entities.md)
- [<span data-ttu-id="8a775-120">Funzioni canoniche</span><span class="sxs-lookup"><span data-stu-id="8a775-120">Canonical Functions</span></span>](canonical-functions.md)
- <span data-ttu-id="8a775-121">[Panoramica sui file con estensione edmx](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="8a775-121">[.edmx File Overview](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100))</span></span>
- <span data-ttu-id="8a775-122">[Procedura: definire funzioni personalizzate nel modello concettuale](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd456812(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="8a775-122">[How to: Define Custom Functions in the Conceptual Model](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd456812(v=vs.100))</span></span>
