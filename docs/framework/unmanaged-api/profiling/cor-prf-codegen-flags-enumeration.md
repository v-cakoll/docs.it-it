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
ms.openlocfilehash: 4dd4e39c9092d018f13e3bd2822e9492d71141ad
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76867295"
---
# <a name="cor_prf_codegen_flags-enumeration"></a><span data-ttu-id="b2452-102">Enumerazione COR_PRF_CODEGEN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="b2452-102">COR_PRF_CODEGEN_FLAGS Enumeration</span></span>
<span data-ttu-id="b2452-103">Definisce i flag di generazione del codice che possono essere impostati con il metodo [ICorProfilerFunctionControl:: SetCodegenFlags](icorprofilerfunctioncontrol-setcodegenflags-method.md) .</span><span class="sxs-lookup"><span data-stu-id="b2452-103">Defines the code generation flags that can be set with the [ICorProfilerFunctionControl::SetCodegenFlags](icorprofilerfunctioncontrol-setcodegenflags-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2452-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b2452-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_CODEGEN_DISABLE_INLINING =          0x0001,  
    COR_PRF_CODEGEN_DISABLE_ALL_OPTIMIZATIONS = 0x0002,  
} COR_PRF_CODEGEN_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="b2452-105">Membri</span><span class="sxs-lookup"><span data-stu-id="b2452-105">Members</span></span>  
  
|<span data-ttu-id="b2452-106">Member</span><span class="sxs-lookup"><span data-stu-id="b2452-106">Member</span></span>|<span data-ttu-id="b2452-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b2452-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_CODEGEN_DISABLE_INLINING`|<span data-ttu-id="b2452-108">Nessuna funzione verrà inline nel corpo di questa funzione.</span><span class="sxs-lookup"><span data-stu-id="b2452-108">No functions will be inlined into this function’s body.</span></span> <span data-ttu-id="b2452-109">Tuttavia, la funzione stessa può essere inline nei relativi chiamanti.</span><span class="sxs-lookup"><span data-stu-id="b2452-109">However, the function itself may be inlined into its callers.</span></span>|  
|`COR_PRF_CODEGEN_DISABLE_ALL_OPTIMIZATIONS`|<span data-ttu-id="b2452-110">Tutte le ottimizzazioni verranno disabilitate per il corpo di questa funzione.</span><span class="sxs-lookup"><span data-stu-id="b2452-110">All optimizations will be disabled for this function’s body.</span></span> <span data-ttu-id="b2452-111">Tuttavia, la funzione stessa può comunque essere inline nei relativi chiamanti.</span><span class="sxs-lookup"><span data-stu-id="b2452-111">However, the function itself may still be inlined into its callers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b2452-112">Note</span><span class="sxs-lookup"><span data-stu-id="b2452-112">Remarks</span></span>  
 <span data-ttu-id="b2452-113">L'enumerazione `COR_PRF_CODEGEN_FLAGS` viene usata dal metodo [ICorProfilerFunctionControl:: SetCodegenFlags](icorprofilerfunctioncontrol-setcodegenflags-method.md) per consentire al profiler di controllare la generazione del codice per la funzione ricompilata in JIT.</span><span class="sxs-lookup"><span data-stu-id="b2452-113">The `COR_PRF_CODEGEN_FLAGS` enumeration is used by the [ICorProfilerFunctionControl::SetCodegenFlags](icorprofilerfunctioncontrol-setcodegenflags-method.md) method to enable the profiler to control the code generation for the JIT-recompiled function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b2452-114">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="b2452-114">Requirements</span></span>  
 <span data-ttu-id="b2452-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b2452-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b2452-116">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b2452-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b2452-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b2452-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b2452-118">**Versioni .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b2452-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2452-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b2452-119">See also</span></span>

- [<span data-ttu-id="b2452-120">Enumerazioni di profilatura</span><span class="sxs-lookup"><span data-stu-id="b2452-120">Profiling Enumerations</span></span>](profiling-enumerations.md)
