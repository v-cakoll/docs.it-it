---
title: Funzioni (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 52b3d776-5acc-4f69-b614-5a43ce56ef9f
ms.openlocfilehash: ec94a0f16fb3b836297f6675cc938a711816555b
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70250913"
---
# <a name="functions-entity-sql"></a><span data-ttu-id="abdd4-102">Funzioni (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="abdd4-102">Functions (Entity SQL)</span></span>
<span data-ttu-id="abdd4-103">Entity SQL supporta funzioni definite dall'utente, funzioni canoniche e funzioni specifiche del provider.</span><span class="sxs-lookup"><span data-stu-id="abdd4-103">Entity SQL supports user-defined functions, canonical functions, and provider-specific functions.</span></span> <span data-ttu-id="abdd4-104">Le funzioni definite dall'utente vengono specificate nel modello concettuale o inline nella query.</span><span class="sxs-lookup"><span data-stu-id="abdd4-104">User-defined functions are specified in the conceptual model or inline in the query.</span></span> <span data-ttu-id="abdd4-105">Per ulteriori informazioni, vedere [funzioni definite dall'utente](user-defined-functions-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="abdd4-105">For more information, see [User-Defined Functions](user-defined-functions-entity-sql.md).</span></span>  
  
 <span data-ttu-id="abdd4-106">Le funzioni canoniche sono predefinite in Entity Framework e devono essere supportate dai provider di dati.</span><span class="sxs-lookup"><span data-stu-id="abdd4-106">Canonical functions are predefined in the Entity Framework and should be supported by data providers.</span></span> <span data-ttu-id="abdd4-107">Se un utente chiama una funzione che non è supportata da un provider, i comandi Entity SQL hanno esito negativo.</span><span class="sxs-lookup"><span data-stu-id="abdd4-107">Entity SQL commands will fail if a user calls a function that is not supported by a provider.</span></span> <span data-ttu-id="abdd4-108">Le funzioni canoniche vengono pertanto generalmente preferite alle funzioni specifiche dell'archivio, che sono incluse in uno spazio dei nomi specifico del provider.</span><span class="sxs-lookup"><span data-stu-id="abdd4-108">Therefore, canonical functions are generally recommended over store-specific functions, which are in a provider-specific namespace.</span></span> <span data-ttu-id="abdd4-109">Per altre informazioni, vedere [funzioni canoniche](canonical-functions.md).</span><span class="sxs-lookup"><span data-stu-id="abdd4-109">For more information, see [Canonical Functions](canonical-functions.md).</span></span>  
  
 <span data-ttu-id="abdd4-110">Il provider gestito del client Microsoft SQL fornisce un set di funzioni specifiche del provider.</span><span class="sxs-lookup"><span data-stu-id="abdd4-110">The Microsoft SQL Client Managed Provider provides a set of provider-specific functions.</span></span> <span data-ttu-id="abdd4-111">Per ulteriori informazioni, vedere [SqlClient per le funzioni Entity Framework](../sqlclient-for-ef-functions.md).</span><span class="sxs-lookup"><span data-stu-id="abdd4-111">For more information, see [SqlClient for Entity Framework Functions](../sqlclient-for-ef-functions.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="abdd4-112">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="abdd4-112">In This Section</span></span>  
 [<span data-ttu-id="abdd4-113">Funzioni definite dall'utente</span><span class="sxs-lookup"><span data-stu-id="abdd4-113">User-Defined Functions</span></span>](user-defined-functions-entity-sql.md)  
  
 [<span data-ttu-id="abdd4-114">Risoluzione dell'overload della funzione</span><span class="sxs-lookup"><span data-stu-id="abdd4-114">Function Overload Resolution</span></span>](function-overload-resolution-entity-sql.md)  
  
 [<span data-ttu-id="abdd4-115">Funzioni di aggregazione</span><span class="sxs-lookup"><span data-stu-id="abdd4-115">Aggregate Functions</span></span>](../aggregate-functions-sqlclient-for-entity-framework.md)  
  
## <a name="see-also"></a><span data-ttu-id="abdd4-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="abdd4-116">See also</span></span>

- [<span data-ttu-id="abdd4-117">Panoramica di Entity SQL</span><span class="sxs-lookup"><span data-stu-id="abdd4-117">Entity SQL Overview</span></span>](entity-sql-overview.md)
