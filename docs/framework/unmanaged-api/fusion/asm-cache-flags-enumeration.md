---
title: Enumerazione ASM_CACHE_FLAGS
ms.date: 03/30/2017
api_name:
- ASM_CACHE_FLAGS
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- ASM_CACHE_FLAGS
helpviewer_keywords:
- ASM_CACHE_FLAGS enumeration [.NET Framework fusion]
ms.assetid: 82e9a7da-321b-48b8-b239-52eaffda6be8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5b712c6ae5978e83dab085f48dd1fd572757384a
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2018
ms.locfileid: "47107896"
---
# <a name="asmcacheflags-enumeration"></a><span data-ttu-id="bc5be-102">Enumerazione ASM_CACHE_FLAGS</span><span class="sxs-lookup"><span data-stu-id="bc5be-102">ASM_CACHE_FLAGS Enumeration</span></span>
<span data-ttu-id="bc5be-103">Indica l'origine di un assembly rappresentato da [IAssemblyCacheItem](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md) nella global assembly cache.</span><span class="sxs-lookup"><span data-stu-id="bc5be-103">Indicates the source of an assembly that is represented by [IAssemblyCacheItem](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md) in the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc5be-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bc5be-104">Syntax</span></span>  
  
```  
typedef enum {  
    ASM_CACHE_ZAP       = 0x01,  
    ASM_CACHE_GAC       = 0x02,  
    ASM_CACHE_DOWNLOAD  = 0x04,  
    ASM_CACHE_ROOT      = 0x08,  
    ASM_CACHE_ROOT_EX   = 0x80  
} ASM_CACHE_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="bc5be-105">Membri</span><span class="sxs-lookup"><span data-stu-id="bc5be-105">Members</span></span>  
  
|<span data-ttu-id="bc5be-106">Membro</span><span class="sxs-lookup"><span data-stu-id="bc5be-106">Member</span></span>|<span data-ttu-id="bc5be-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bc5be-107">Description</span></span>|  
|------------|-----------------|  
|`ASM_CACHE_ZAP`|<span data-ttu-id="bc5be-108">Enumera la cache di assembly precompilati usando Ngen.exe.</span><span class="sxs-lookup"><span data-stu-id="bc5be-108">Enumerates the cache of precompiled assemblies by using Ngen.exe.</span></span>|  
|`ASM_CACHE_GAC`|<span data-ttu-id="bc5be-109">Enumera la global assembly cache.</span><span class="sxs-lookup"><span data-stu-id="bc5be-109">Enumerates the global assembly cache.</span></span>|  
|`ASM_CACHE_DOWNLOAD`|<span data-ttu-id="bc5be-110">Enumera gli assembly che sono stati scaricati su richiesta o che sono stati replicati.</span><span class="sxs-lookup"><span data-stu-id="bc5be-110">Enumerates the assemblies that have been downloaded on demand or that have been shadow-copied.</span></span>|  
|`ASM_CACHE_ROOT`|<span data-ttu-id="bc5be-111">Indica che il [GetCachePath](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md) funzione deve restituire il percorso alla global assembly cache per common language runtime (CLR) versione 2.0.</span><span class="sxs-lookup"><span data-stu-id="bc5be-111">Indicates that the [GetCachePath](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md) function should return the path to the global assembly cache for the common language runtime (CLR) version 2.0.</span></span> <span data-ttu-id="bc5be-112">Significativo solo nel contesto di una chiamata a [GetCachePath](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md).</span><span class="sxs-lookup"><span data-stu-id="bc5be-112">Meaningful only in the context of a call to [GetCachePath](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md).</span></span>|  
|`ASM_CACHE_ROOT_EX`|<span data-ttu-id="bc5be-113">Indica che il [GetCachePath](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md) funzione deve restituire il percorso alla global assembly cache per la versione 4 di CLR.</span><span class="sxs-lookup"><span data-stu-id="bc5be-113">Indicates that the [GetCachePath](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md) function should return the path to the global assembly cache for CLR version 4.</span></span> <span data-ttu-id="bc5be-114">Significativo solo nel contesto di una chiamata a [GetCachePath](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md).</span><span class="sxs-lookup"><span data-stu-id="bc5be-114">Meaningful only in the context of a call to [GetCachePath](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md).</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="bc5be-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="bc5be-115">Requirements</span></span>  
 <span data-ttu-id="bc5be-116">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bc5be-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bc5be-117">**Intestazione:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="bc5be-117">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="bc5be-118">**Libreria:** inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="bc5be-118">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="bc5be-119">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bc5be-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc5be-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bc5be-120">See Also</span></span>  
 [<span data-ttu-id="bc5be-121">Funzione GetCachePath</span><span class="sxs-lookup"><span data-stu-id="bc5be-121">GetCachePath Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md)  
 [<span data-ttu-id="bc5be-122">Interfaccia IAssemblyCacheItem</span><span class="sxs-lookup"><span data-stu-id="bc5be-122">IAssemblyCacheItem Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md)  
 [<span data-ttu-id="bc5be-123">Enumerazioni Fusion</span><span class="sxs-lookup"><span data-stu-id="bc5be-123">Fusion Enumerations</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-enumerations.md)
