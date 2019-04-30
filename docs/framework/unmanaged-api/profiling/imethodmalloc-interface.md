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
ms.openlocfilehash: ee825da1f3f0fd72a3b47b48783f0f344af99b65
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61969806"
---
# <a name="imethodmalloc-interface"></a><span data-ttu-id="27f31-102">Interfaccia IMethodMalloc</span><span class="sxs-lookup"><span data-stu-id="27f31-102">IMethodMalloc Interface</span></span>
<span data-ttu-id="27f31-103">Fornisce un metodo per allocare memoria per un nuovo corpo di funzione Microsoft intermediate language (MSIL).</span><span class="sxs-lookup"><span data-stu-id="27f31-103">Provides a method to allocate memory for a new Microsoft intermediate language (MSIL) function body.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="27f31-104">Il `IMethodMalloc` interfaccia è un allocatore di memoria semplice.</span><span class="sxs-lookup"><span data-stu-id="27f31-104">The `IMethodMalloc` interface is a simple memory allocator.</span></span> <span data-ttu-id="27f31-105">Consente di allocare la memoria, ma non per liberarlo.</span><span class="sxs-lookup"><span data-stu-id="27f31-105">It allows you to allocate memory, but not to free it.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="27f31-106">Metodi</span><span class="sxs-lookup"><span data-stu-id="27f31-106">Methods</span></span>  
  
|<span data-ttu-id="27f31-107">Metodo</span><span class="sxs-lookup"><span data-stu-id="27f31-107">Method</span></span>|<span data-ttu-id="27f31-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="27f31-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="27f31-109">Metodo Alloc</span><span class="sxs-lookup"><span data-stu-id="27f31-109">Alloc Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-alloc-method.md)|<span data-ttu-id="27f31-110">Tenta di allocare una quantità di memoria specificata per un nuovo corpo funzione MSIL.</span><span class="sxs-lookup"><span data-stu-id="27f31-110">Attempts to allocate a specified amount of memory for a new MSIL function body.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="27f31-111">Note</span><span class="sxs-lookup"><span data-stu-id="27f31-111">Remarks</span></span>  
 <span data-ttu-id="27f31-112">Ogni allocatore è specifico del modulo e assicura che il corpo della funzione sarà un offset dalla base del modulo positivo.</span><span class="sxs-lookup"><span data-stu-id="27f31-112">Each allocator is module-specific and ensures that the function body will be at a positive offset from the base of the module.</span></span> <span data-ttu-id="27f31-113">Memoria di sopra della base di un modulo può essere preziosa, in modo che l'allocatore dovrebbe essere utilizzato per allocare memoria solo per un corpo della funzione.</span><span class="sxs-lookup"><span data-stu-id="27f31-113">Memory above the base of a module can be precious, so the allocator should be used to allocate memory only for a function body.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="27f31-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="27f31-114">Requirements</span></span>  
 <span data-ttu-id="27f31-115">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="27f31-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="27f31-116">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="27f31-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="27f31-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="27f31-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="27f31-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="27f31-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27f31-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="27f31-119">See also</span></span>

- [<span data-ttu-id="27f31-120">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="27f31-120">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
