---
title: Interfaccia IMethodMalloc
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IMethodMalloc
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- IMethodMalloc
helpviewer_keywords:
- IMethodMalloc interface [.NET Framework profiling]
ms.assetid: 8c8ab5dc-557c-473a-82f2-6e403eca7dac
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1941a46a60219d9dd56d162f89baf268f220c102
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="imethodmalloc-interface"></a><span data-ttu-id="3de68-102">Interfaccia IMethodMalloc</span><span class="sxs-lookup"><span data-stu-id="3de68-102">IMethodMalloc Interface</span></span>
<span data-ttu-id="3de68-103">Fornisce un metodo per allocare memoria per un nuovo corpo della funzione Microsoft intermediate language (MSIL).</span><span class="sxs-lookup"><span data-stu-id="3de68-103">Provides a method to allocate memory for a new Microsoft intermediate language (MSIL) function body.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3de68-104">Il `IMethodMalloc` interfaccia è un semplice allocatore di memoria.</span><span class="sxs-lookup"><span data-stu-id="3de68-104">The `IMethodMalloc` interface is a simple memory allocator.</span></span> <span data-ttu-id="3de68-105">Consente di allocare memoria, ma non per liberarlo.</span><span class="sxs-lookup"><span data-stu-id="3de68-105">It allows you to allocate memory, but not to free it.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3de68-106">Metodi</span><span class="sxs-lookup"><span data-stu-id="3de68-106">Methods</span></span>  
  
|<span data-ttu-id="3de68-107">Metodo</span><span class="sxs-lookup"><span data-stu-id="3de68-107">Method</span></span>|<span data-ttu-id="3de68-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3de68-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3de68-109">Metodo Alloc</span><span class="sxs-lookup"><span data-stu-id="3de68-109">Alloc Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-alloc-method.md)|<span data-ttu-id="3de68-110">Tenta di allocare una quantità di memoria specificata per il corpo di una nuova funzione MSIL.</span><span class="sxs-lookup"><span data-stu-id="3de68-110">Attempts to allocate a specified amount of memory for a new MSIL function body.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3de68-111">Note</span><span class="sxs-lookup"><span data-stu-id="3de68-111">Remarks</span></span>  
 <span data-ttu-id="3de68-112">Ogni allocatore è specifico del modulo e assicura che il corpo della funzione sarà un offset positivo dalla base del modulo.</span><span class="sxs-lookup"><span data-stu-id="3de68-112">Each allocator is module-specific and ensures that the function body will be at a positive offset from the base of the module.</span></span> <span data-ttu-id="3de68-113">Memoria di sopra della base di un modulo può essere preziosa, pertanto l'allocatore deve essere utilizzata per allocare memoria solo per un corpo della funzione.</span><span class="sxs-lookup"><span data-stu-id="3de68-113">Memory above the base of a module can be precious, so the allocator should be used to allocate memory only for a function body.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3de68-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3de68-114">Requirements</span></span>  
 <span data-ttu-id="3de68-115">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3de68-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3de68-116">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3de68-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3de68-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3de68-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3de68-118">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3de68-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3de68-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3de68-119">See Also</span></span>  
 [<span data-ttu-id="3de68-120">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="3de68-120">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
