---
title: Funzione GetCachePath
ms.date: 03/30/2017
api_name:
- GetCachePath
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- GetCachePath
helpviewer_keywords:
- GetCachePath function [.NET Framework fusion]
ms.assetid: d977ad29-6619-42e1-b0be-bc25ea950e80
topic_type:
- apiref
ms.openlocfilehash: 13e1468ef5a48f18910c1f8082cdd7c4849da14a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132675"
---
# <a name="getcachepath-function"></a><span data-ttu-id="42ff3-102">Funzione GetCachePath</span><span class="sxs-lookup"><span data-stu-id="42ff3-102">GetCachePath Function</span></span>
<span data-ttu-id="42ff3-103">Ottiene il percorso dell'assembly memorizzato nella cache, usando i flag specificati.</span><span class="sxs-lookup"><span data-stu-id="42ff3-103">Gets the path to the cached assembly, using the specified flags.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42ff3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="42ff3-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCachePath (  
    [in]      ASM_CACHE_FLAGS  dwCacheFlags,  
    [in]      LPWSTR           pwzCachePath,  
    [in, out] PDWORD           pcchPath  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="42ff3-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="42ff3-105">Parameters</span></span>  
 `dwCacheFlags`  
 <span data-ttu-id="42ff3-106">in Valore [ASM_CACHE_FLAGS](asm-cache-flags-enumeration.md) che indica l'origine dell'assembly memorizzato nella cache.</span><span class="sxs-lookup"><span data-stu-id="42ff3-106">[in] An [ASM_CACHE_FLAGS](asm-cache-flags-enumeration.md) value that indicates the source of the cached assembly.</span></span>  
  
 `pwzCachePath`  
 <span data-ttu-id="42ff3-107">out Puntatore restituito al percorso.</span><span class="sxs-lookup"><span data-stu-id="42ff3-107">[out] The returned pointer to the path.</span></span>  
  
 `pcchPath`  
 <span data-ttu-id="42ff3-108">[in, out] La lunghezza massima richiesta di `pwzCachePath`e, al ritorno, la lunghezza effettiva del `pwzCachePath`.</span><span class="sxs-lookup"><span data-stu-id="42ff3-108">[in, out] The requested maximum length of `pwzCachePath`, and upon return, the actual length of `pwzCachePath`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="42ff3-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="42ff3-109">Requirements</span></span>  
 <span data-ttu-id="42ff3-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="42ff3-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="42ff3-111">**Intestazione:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="42ff3-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="42ff3-112">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="42ff3-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42ff3-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="42ff3-113">See also</span></span>

- [<span data-ttu-id="42ff3-114">Enumerazione ASM_CACHE_FLAGS</span><span class="sxs-lookup"><span data-stu-id="42ff3-114">ASM_CACHE_FLAGS Enumeration</span></span>](asm-cache-flags-enumeration.md)
- [<span data-ttu-id="42ff3-115">Funzioni statiche globali Fusion</span><span class="sxs-lookup"><span data-stu-id="42ff3-115">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
