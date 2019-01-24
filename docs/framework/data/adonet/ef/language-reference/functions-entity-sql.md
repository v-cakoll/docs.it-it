---
title: Funzioni (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 52b3d776-5acc-4f69-b614-5a43ce56ef9f
ms.openlocfilehash: 88029f22cc22594d26a05ad66051378a75a6e753
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54715595"
---
# <a name="functions-entity-sql"></a><span data-ttu-id="550ea-102">Funzioni (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="550ea-102">Functions (Entity SQL)</span></span>
<span data-ttu-id="550ea-103">Entity SQL supporta funzioni definite dall'utente, funzioni canoniche e funzioni specifiche del provider.</span><span class="sxs-lookup"><span data-stu-id="550ea-103">Entity SQL supports user-defined functions, canonical functions, and provider-specific functions.</span></span> <span data-ttu-id="550ea-104">Le funzioni definite dall'utente vengono specificate nel modello concettuale o inline nella query.</span><span class="sxs-lookup"><span data-stu-id="550ea-104">User-defined functions are specified in the conceptual model or inline in the query.</span></span> <span data-ttu-id="550ea-105">Per altre informazioni, vedere [funzioni definite dall'utente](../../../../../../docs/framework/data/adonet/ef/language-reference/user-defined-functions-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="550ea-105">For more information, see [User-Defined Functions](../../../../../../docs/framework/data/adonet/ef/language-reference/user-defined-functions-entity-sql.md).</span></span>  
  
 <span data-ttu-id="550ea-106">Le funzioni canoniche sono predefinite in Entity Framework e devono essere supportate dai provider di dati.</span><span class="sxs-lookup"><span data-stu-id="550ea-106">Canonical functions are predefined in the Entity Framework and should be supported by data providers.</span></span> <span data-ttu-id="550ea-107">Se un utente chiama una funzione che non è supportata da un provider, i comandi Entity SQL hanno esito negativo.</span><span class="sxs-lookup"><span data-stu-id="550ea-107">Entity SQL commands will fail if a user calls a function that is not supported by a provider.</span></span> <span data-ttu-id="550ea-108">Le funzioni canoniche vengono pertanto generalmente preferite alle funzioni specifiche dell'archivio, che sono incluse in uno spazio dei nomi specifico del provider.</span><span class="sxs-lookup"><span data-stu-id="550ea-108">Therefore, canonical functions are generally recommended over store-specific functions, which are in a provider-specific namespace.</span></span> <span data-ttu-id="550ea-109">Per altre informazioni, vedere [funzioni canoniche](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md).</span><span class="sxs-lookup"><span data-stu-id="550ea-109">For more information, see [Canonical Functions](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md).</span></span>  
  
 <span data-ttu-id="550ea-110">Il provider gestito del client Microsoft SQL fornisce un set di funzioni specifiche del provider.</span><span class="sxs-lookup"><span data-stu-id="550ea-110">The Microsoft SQL Client Managed Provider provides a set of provider-specific functions.</span></span> <span data-ttu-id="550ea-111">Per altre informazioni, vedere [SqlClient per funzioni Entity Framework](../../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md).</span><span class="sxs-lookup"><span data-stu-id="550ea-111">For more information, see [SqlClient for Entity Framework Functions](../../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="550ea-112">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="550ea-112">In This Section</span></span>  
 [<span data-ttu-id="550ea-113">Funzioni definite dall'utente</span><span class="sxs-lookup"><span data-stu-id="550ea-113">User-Defined Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/user-defined-functions-entity-sql.md)  
  
 [<span data-ttu-id="550ea-114">Risoluzione dell'overload della funzione</span><span class="sxs-lookup"><span data-stu-id="550ea-114">Function Overload Resolution</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/function-overload-resolution-entity-sql.md)  
  
 [<span data-ttu-id="550ea-115">Funzioni di aggregazione</span><span class="sxs-lookup"><span data-stu-id="550ea-115">Aggregate Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/aggregate-functions-sqlclient-for-entity-framework.md)  
  
## <a name="see-also"></a><span data-ttu-id="550ea-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="550ea-116">See also</span></span>
- [<span data-ttu-id="550ea-117">Panoramica di Entity SQL</span><span class="sxs-lookup"><span data-stu-id="550ea-117">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
