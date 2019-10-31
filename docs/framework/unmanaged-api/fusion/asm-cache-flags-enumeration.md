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
ms.openlocfilehash: 85ac976daec8fd76ee21012a30611235609f4b34
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73109485"
---
# <a name="asm_cache_flags-enumeration"></a><span data-ttu-id="b3cf9-102">Enumerazione ASM_CACHE_FLAGS</span><span class="sxs-lookup"><span data-stu-id="b3cf9-102">ASM_CACHE_FLAGS Enumeration</span></span>
<span data-ttu-id="b3cf9-103">Indica l'origine di un assembly rappresentato da [IAssemblyCacheItem](iassemblycacheitem-interface.md) nel Global assembly cache.</span><span class="sxs-lookup"><span data-stu-id="b3cf9-103">Indicates the source of an assembly that is represented by [IAssemblyCacheItem](iassemblycacheitem-interface.md) in the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b3cf9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b3cf9-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    ASM_CACHE_ZAP       = 0x01,  
    ASM_CACHE_GAC       = 0x02,  
    ASM_CACHE_DOWNLOAD  = 0x04,  
    ASM_CACHE_ROOT      = 0x08,  
    ASM_CACHE_ROOT_EX   = 0x80  
} ASM_CACHE_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="b3cf9-105">Members</span><span class="sxs-lookup"><span data-stu-id="b3cf9-105">Members</span></span>  
  
|<span data-ttu-id="b3cf9-106">Member</span><span class="sxs-lookup"><span data-stu-id="b3cf9-106">Member</span></span>|<span data-ttu-id="b3cf9-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b3cf9-107">Description</span></span>|  
|------------|-----------------|  
|`ASM_CACHE_ZAP`|<span data-ttu-id="b3cf9-108">Enumera la cache degli assembly precompilati utilizzando Ngen. exe.</span><span class="sxs-lookup"><span data-stu-id="b3cf9-108">Enumerates the cache of precompiled assemblies by using Ngen.exe.</span></span>|  
|`ASM_CACHE_GAC`|<span data-ttu-id="b3cf9-109">Enumera il Global Assembly Cache.</span><span class="sxs-lookup"><span data-stu-id="b3cf9-109">Enumerates the global assembly cache.</span></span>|  
|`ASM_CACHE_DOWNLOAD`|<span data-ttu-id="b3cf9-110">Enumera gli assembly scaricati su richiesta o di cui è stata eseguita la copia shadow.</span><span class="sxs-lookup"><span data-stu-id="b3cf9-110">Enumerates the assemblies that have been downloaded on demand or that have been shadow-copied.</span></span>|  
|`ASM_CACHE_ROOT`|<span data-ttu-id="b3cf9-111">Indica che la funzione [GetCachePath](getcachepath-function.md) deve restituire il percorso del Global assembly cache per la Common Language Runtime (CLR) versione 2,0.</span><span class="sxs-lookup"><span data-stu-id="b3cf9-111">Indicates that the [GetCachePath](getcachepath-function.md) function should return the path to the global assembly cache for the common language runtime (CLR) version 2.0.</span></span> <span data-ttu-id="b3cf9-112">Significativo solo nel contesto di una chiamata a [GetCachePath](getcachepath-function.md).</span><span class="sxs-lookup"><span data-stu-id="b3cf9-112">Meaningful only in the context of a call to [GetCachePath](getcachepath-function.md).</span></span>|  
|`ASM_CACHE_ROOT_EX`|<span data-ttu-id="b3cf9-113">Indica che la funzione [GetCachePath](getcachepath-function.md) deve restituire il percorso del Global assembly cache per CLR versione 4.</span><span class="sxs-lookup"><span data-stu-id="b3cf9-113">Indicates that the [GetCachePath](getcachepath-function.md) function should return the path to the global assembly cache for CLR version 4.</span></span> <span data-ttu-id="b3cf9-114">Significativo solo nel contesto di una chiamata a [GetCachePath](getcachepath-function.md).</span><span class="sxs-lookup"><span data-stu-id="b3cf9-114">Meaningful only in the context of a call to [GetCachePath](getcachepath-function.md).</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b3cf9-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b3cf9-115">Requirements</span></span>  
 <span data-ttu-id="b3cf9-116">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b3cf9-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b3cf9-117">**Intestazione:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="b3cf9-117">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="b3cf9-118">**Libreria:** Incluso come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="b3cf9-118">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b3cf9-119">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b3cf9-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3cf9-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b3cf9-120">See also</span></span>

- [<span data-ttu-id="b3cf9-121">Funzione GetCachePath</span><span class="sxs-lookup"><span data-stu-id="b3cf9-121">GetCachePath Function</span></span>](getcachepath-function.md)
- [<span data-ttu-id="b3cf9-122">Interfaccia IAssemblyCacheItem</span><span class="sxs-lookup"><span data-stu-id="b3cf9-122">IAssemblyCacheItem Interface</span></span>](iassemblycacheitem-interface.md)
- [<span data-ttu-id="b3cf9-123">Enumerazioni Fusion</span><span class="sxs-lookup"><span data-stu-id="b3cf9-123">Fusion Enumerations</span></span>](fusion-enumerations.md)
