---
title: Interfaccia IMethodMalloc
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c67ce15175f8667139f99cec1ed17531eab473e1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69935653"
---
# <a name="imethodmalloc-interface"></a><span data-ttu-id="df0c4-102">Interfaccia IMethodMalloc</span><span class="sxs-lookup"><span data-stu-id="df0c4-102">IMethodMalloc Interface</span></span>
<span data-ttu-id="df0c4-103">Fornisce un metodo per allocare memoria per un nuovo corpo della funzione MSIL (Microsoft Intermediate Language).</span><span class="sxs-lookup"><span data-stu-id="df0c4-103">Provides a method to allocate memory for a new Microsoft intermediate language (MSIL) function body.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="df0c4-104">L' `IMethodMalloc` interfaccia è un semplice allocatore di memoria.</span><span class="sxs-lookup"><span data-stu-id="df0c4-104">The `IMethodMalloc` interface is a simple memory allocator.</span></span> <span data-ttu-id="df0c4-105">Consente di allocare memoria, ma non di liberarla.</span><span class="sxs-lookup"><span data-stu-id="df0c4-105">It allows you to allocate memory, but not to free it.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="df0c4-106">Metodi</span><span class="sxs-lookup"><span data-stu-id="df0c4-106">Methods</span></span>  
  
|<span data-ttu-id="df0c4-107">Metodo</span><span class="sxs-lookup"><span data-stu-id="df0c4-107">Method</span></span>|<span data-ttu-id="df0c4-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="df0c4-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="df0c4-109">Metodo Alloc</span><span class="sxs-lookup"><span data-stu-id="df0c4-109">Alloc Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-alloc-method.md)|<span data-ttu-id="df0c4-110">Tenta di allocare una quantità specificata di memoria per un nuovo corpo della funzione MSIL.</span><span class="sxs-lookup"><span data-stu-id="df0c4-110">Attempts to allocate a specified amount of memory for a new MSIL function body.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="df0c4-111">Note</span><span class="sxs-lookup"><span data-stu-id="df0c4-111">Remarks</span></span>  
 <span data-ttu-id="df0c4-112">Ogni allocatore è specifico del modulo e garantisce che il corpo della funzione si trovi in corrispondenza di un offset positivo rispetto alla base del modulo.</span><span class="sxs-lookup"><span data-stu-id="df0c4-112">Each allocator is module-specific and ensures that the function body will be at a positive offset from the base of the module.</span></span> <span data-ttu-id="df0c4-113">La memoria al di sopra della base di un modulo può essere preziosa, quindi l'allocatore deve essere usato per allocare memoria solo per il corpo di una funzione.</span><span class="sxs-lookup"><span data-stu-id="df0c4-113">Memory above the base of a module can be precious, so the allocator should be used to allocate memory only for a function body.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="df0c4-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="df0c4-114">Requirements</span></span>  
 <span data-ttu-id="df0c4-115">**Piattaforme** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="df0c4-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="df0c4-116">**Intestazione:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="df0c4-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="df0c4-117">**Libreria** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="df0c4-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="df0c4-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="df0c4-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df0c4-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="df0c4-119">See also</span></span>

- [<span data-ttu-id="df0c4-120">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="df0c4-120">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
