---
title: Metodo ICorDebugExceptionObjectCallStackEnum::Next
ms.date: 03/30/2017
api_name:
- ICorDebugExceptionObjectCallStackEnum::Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugExceptionObjectCallStackEnum::Next
helpviewer_keywords:
- ICorDebugExceptionObjectCallStackEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugExceptionObjectCallStackEnum interface [.NET Framework debugging]
ms.assetid: 3328a2c0-1e48-4a54-802a-9b474cf82c21
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7c33f76b5eaa87c0b69497547732564921f662d5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59099469"
---
# <a name="icordebugexceptionobjectcallstackenumnext-method"></a><span data-ttu-id="3cfaf-102">Metodo ICorDebugExceptionObjectCallStackEnum::Next</span><span class="sxs-lookup"><span data-stu-id="3cfaf-102">ICorDebugExceptionObjectCallStackEnum::Next Method</span></span>
<span data-ttu-id="3cfaf-103">Ottiene il numero specificato di [CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) istanze che contengono informazioni dallo stack di chiamate di un oggetto eccezione.</span><span class="sxs-lookup"><span data-stu-id="3cfaf-103">Gets the specified number of [CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) instances that contain information from an exception object's call stack.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3cfaf-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3cfaf-104">Syntax</span></span>  
  
```  
HRESULT Next(  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)] CorDebugExceptionObjectStackFrame values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3cfaf-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="3cfaf-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="3cfaf-106">[in] I numerosi [CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) istanze da recuperare.</span><span class="sxs-lookup"><span data-stu-id="3cfaf-106">[in] The number of [CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) instances to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="3cfaf-107">[out] Una matrice di puntatori, ognuno dei quali punta a un [CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) oggetto.</span><span class="sxs-lookup"><span data-stu-id="3cfaf-107">[out] An array of pointers, each of which points to a [CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="3cfaf-108">[out] Un puntatore al numero di [CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) istanze effettivamente restituite.</span><span class="sxs-lookup"><span data-stu-id="3cfaf-108">[out] A pointer to the number of [CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) instances actually returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3cfaf-109">Note</span><span class="sxs-lookup"><span data-stu-id="3cfaf-109">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3cfaf-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3cfaf-110">Requirements</span></span>  
 <span data-ttu-id="3cfaf-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3cfaf-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3cfaf-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3cfaf-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3cfaf-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3cfaf-113">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="3cfaf-114">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="3cfaf-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3cfaf-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3cfaf-115">See also</span></span>

- [<span data-ttu-id="3cfaf-116">Interfaccia ICorDebugExceptionObjectCallStackEnum</span><span class="sxs-lookup"><span data-stu-id="3cfaf-116">ICorDebugExceptionObjectCallStackEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md)
- [<span data-ttu-id="3cfaf-117">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="3cfaf-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
