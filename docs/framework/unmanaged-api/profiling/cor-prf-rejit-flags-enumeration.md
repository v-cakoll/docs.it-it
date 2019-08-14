---
title: Enumerazione COR_PRF_REJIT_FLAGS
ms.date: 08/06/2019
api_name:
- COR_PRF_REJIT_FLAGS Enumeration
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_REJIT_FLAGS
helpviewer_keywords:
- COR_PRF_REJIT_FLAGS enumeration [.NET Framework profiling]
topic_type:
- apiref
author: davmason
ms.author: davmason
ms.openlocfilehash: c616cb45eadab3a55aa76526d530cb2841e6d5fa
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/13/2019
ms.locfileid: "68974111"
---
# <a name="cor_prf_rejit_flags-enumeration"></a><span data-ttu-id="3182d-102">Enumerazione COR_PRF_REJIT_FLAGS</span><span class="sxs-lookup"><span data-stu-id="3182d-102">COR_PRF_REJIT_FLAGS Enumeration</span></span>
<span data-ttu-id="3182d-103">Contiene valori che indicano il comportamento dell'API [ICorProfilerInfo10:: RequestReJITWithInliners](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-requestrejitwithinliners-method.md) .</span><span class="sxs-lookup"><span data-stu-id="3182d-103">Contains values that indicate how the [ICorProfilerInfo10::RequestReJITWithInliners](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-requestrejitwithinliners-method.md) API should behave.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3182d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3182d-104">Syntax</span></span>  
  
```cpp  
typedef enum  
{      
    COR_PRF_REJIT_BLOCK_INLINING = 0x1,
    COR_PRF_REJIT_INLINING_CALLBACKS    = 0x2
} COR_PRF_REJIT_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="3182d-105">Members</span><span class="sxs-lookup"><span data-stu-id="3182d-105">Members</span></span>  
  
|<span data-ttu-id="3182d-106">Member</span><span class="sxs-lookup"><span data-stu-id="3182d-106">Member</span></span>|<span data-ttu-id="3182d-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3182d-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_REJIT_BLOCK_INLINING`| <span data-ttu-id="3182d-108">I metodi ReJITted verranno bloccati in altri metodi.</span><span class="sxs-lookup"><span data-stu-id="3182d-108">ReJITted methods will be blocked from being inlined in other methods.</span></span> |  
|`COR_PRF_REJIT_INLINING_CALLBACKS`| <span data-ttu-id="3182d-109">Ricevere `GetFunctionParameters` callback per tutti i metodi che incorporano i metodi richiesti per essere ReJITted.</span><span class="sxs-lookup"><span data-stu-id="3182d-109">Receive `GetFunctionParameters` callbacks for any methods that inline the methods requested to be ReJITted.</span></span> |  

## <a name="requirements"></a><span data-ttu-id="3182d-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3182d-110">Requirements</span></span>  
 <span data-ttu-id="3182d-111">**Piattaforme** Vedere [sistemi operativi supportati da .NET Core](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).</span><span class="sxs-lookup"><span data-stu-id="3182d-111">**Platforms:** See [.NET Core supported operating systems](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).</span></span>  
  
 <span data-ttu-id="3182d-112">**Intestazione:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="3182d-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3182d-113">**Libreria** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3182d-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3182d-114">**Versioni di .NET Framework:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3182d-114">**.NET Framework Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="3182d-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3182d-115">See also</span></span>

- [<span data-ttu-id="3182d-116">Enumerazioni di profilatura</span><span class="sxs-lookup"><span data-stu-id="3182d-116">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
