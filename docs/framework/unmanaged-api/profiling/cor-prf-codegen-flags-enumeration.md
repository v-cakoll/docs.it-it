---
title: Enumerazione COR_PRF_CODEGEN_FLAGS
ms.date: 03/30/2017
api_name:
- COR_PRF_CODEGEN_FLAGS
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_CODEGEN_FLAGS
helpviewer_keywords:
- COR_PRF_CODEGEN_FLAGS enumeration [.NET Framework profiling]
ms.assetid: 3e184022-0247-4824-a23d-6b29593d8d01
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 321318b63368ed6e57d235cf97d94485352f8686
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61775128"
---
# <a name="corprfcodegenflags-enumeration"></a><span data-ttu-id="bf76e-102">Enumerazione COR_PRF_CODEGEN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="bf76e-102">COR_PRF_CODEGEN_FLAGS Enumeration</span></span>
<span data-ttu-id="bf76e-103">Definisce i flag di generazione di codice che possono essere impostati con il [icorprofilerfunctioncontrol:: Setcodegenflags](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="bf76e-103">Defines the code generation flags that can be set with the [ICorProfilerFunctionControl::SetCodegenFlags](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf76e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bf76e-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PRF_CODEGEN_DISABLE_INLINING =          0x0001,  
    COR_PRF_CODEGEN_DISABLE_ALL_OPTIMIZATIONS = 0x0002,  
} COR_PRF_CODEGEN_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="bf76e-105">Membri</span><span class="sxs-lookup"><span data-stu-id="bf76e-105">Members</span></span>  
  
|<span data-ttu-id="bf76e-106">Member</span><span class="sxs-lookup"><span data-stu-id="bf76e-106">Member</span></span>|<span data-ttu-id="bf76e-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bf76e-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_CODEGEN_DISABLE_INLINING`|<span data-ttu-id="bf76e-108">Nessuna funzione verranno resa inline nel corpo della funzione.</span><span class="sxs-lookup"><span data-stu-id="bf76e-108">No functions will be inlined into this function’s body.</span></span> <span data-ttu-id="bf76e-109">Tuttavia, la funzione stessa può essere impostato come inline nei relativi chiamanti.</span><span class="sxs-lookup"><span data-stu-id="bf76e-109">However, the function itself may be inlined into its callers.</span></span>|  
|`COR_PRF_CODEGEN_DISABLE_ALL_OPTIMIZATIONS`|<span data-ttu-id="bf76e-110">Tutte le ottimizzazioni verranno disabilitate per il corpo della funzione.</span><span class="sxs-lookup"><span data-stu-id="bf76e-110">All optimizations will be disabled for this function’s body.</span></span> <span data-ttu-id="bf76e-111">Tuttavia, la funzione in sé può rivelarsi ancora implementazione inline nei relativi chiamanti.</span><span class="sxs-lookup"><span data-stu-id="bf76e-111">However, the function itself may still be inlined into its callers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bf76e-112">Note</span><span class="sxs-lookup"><span data-stu-id="bf76e-112">Remarks</span></span>  
 <span data-ttu-id="bf76e-113">Il `COR_PRF_CODEGEN_FLAGS` enumerazione viene utilizzata per il [icorprofilerfunctioncontrol:: Setcodegenflags](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md) metodo per abilitare il profiler controllare la generazione del codice della funzione ricompilata in JIT.</span><span class="sxs-lookup"><span data-stu-id="bf76e-113">The `COR_PRF_CODEGEN_FLAGS` enumeration is used by the [ICorProfilerFunctionControl::SetCodegenFlags](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md) method to enable the profiler to control the code generation for the JIT-recompiled function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bf76e-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="bf76e-114">Requirements</span></span>  
 <span data-ttu-id="bf76e-115">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bf76e-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bf76e-116">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="bf76e-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="bf76e-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bf76e-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bf76e-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bf76e-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf76e-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bf76e-119">See also</span></span>

- [<span data-ttu-id="bf76e-120">Enumerazioni di profilatura</span><span class="sxs-lookup"><span data-stu-id="bf76e-120">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
