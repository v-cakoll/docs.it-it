---
title: Struttura COR_PRF_FUNCTION_ARGUMENT_RANGE
ms.date: 03/30/2017
api_name:
- COR_PRF_FUNCTION_ARGUMENT_RANGE
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_FUNCTION_ARGUMENT_RANGE
helpviewer_keywords:
- COR_PRF_FUNCTION_ARGUMENT_RANGE structure [.NET Framework profiling'
ms.assetid: 9f469eac-ac66-419b-8668-fe705bc1a51f
topic_type:
- apiref
ms.openlocfilehash: 8b3785955ec138bbf898e84aa4deb5ed2a6e6b53
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500949"
---
# <a name="cor_prf_function_argument_range-structure"></a><span data-ttu-id="c190c-102">Struttura COR_PRF_FUNCTION_ARGUMENT_RANGE</span><span class="sxs-lookup"><span data-stu-id="c190c-102">COR_PRF_FUNCTION_ARGUMENT_RANGE Structure</span></span>
<span data-ttu-id="c190c-103">Rappresenta un blocco di argomenti della funzione archiviati in modo contiguo da sinistra a destra in memoria.</span><span class="sxs-lookup"><span data-stu-id="c190c-103">Represents a block of function arguments stored contiguously in left-to-right order in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c190c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c190c-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_PRF_FUNCTION_ARGUMENT_RANGE {  
    UINT_PTR startAddress;  
    ULONG length;  
} COR_PRF_FUNCTION_ARGUMENT_RANGE;  
```  
  
## <a name="members"></a><span data-ttu-id="c190c-105">Membri</span><span class="sxs-lookup"><span data-stu-id="c190c-105">Members</span></span>  
  
|<span data-ttu-id="c190c-106">Membri</span><span class="sxs-lookup"><span data-stu-id="c190c-106">Members</span></span>|<span data-ttu-id="c190c-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c190c-107">Description</span></span>|  
|-------------|-----------------|  
|`startAddress`|<span data-ttu-id="c190c-108">Indirizzo iniziale del blocco.</span><span class="sxs-lookup"><span data-stu-id="c190c-108">The starting address of the block.</span></span>|  
|`length`|<span data-ttu-id="c190c-109">Lunghezza del blocco contiguo.</span><span class="sxs-lookup"><span data-stu-id="c190c-109">The length of the contiguous block.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c190c-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c190c-110">Requirements</span></span>  
 <span data-ttu-id="c190c-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c190c-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c190c-112">**Intestazione:** CorProf. idl</span><span class="sxs-lookup"><span data-stu-id="c190c-112">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="c190c-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c190c-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c190c-114">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c190c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c190c-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c190c-115">See also</span></span>

- [<span data-ttu-id="c190c-116">Strutture di profilatura</span><span class="sxs-lookup"><span data-stu-id="c190c-116">Profiling Structures</span></span>](profiling-structures.md)
