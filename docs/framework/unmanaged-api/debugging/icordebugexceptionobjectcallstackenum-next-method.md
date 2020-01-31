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
ms.openlocfilehash: 38de810509f15cf93475eb000837892b99684fc9
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76782755"
---
# <a name="icordebugexceptionobjectcallstackenumnext-method"></a><span data-ttu-id="a0a80-102">Metodo ICorDebugExceptionObjectCallStackEnum::Next</span><span class="sxs-lookup"><span data-stu-id="a0a80-102">ICorDebugExceptionObjectCallStackEnum::Next Method</span></span>
<span data-ttu-id="a0a80-103">Ottiene il numero specificato di istanze di [CorDebugExceptionObjectStackFrame](cordebugexceptionobjectstackframe-structure.md) che contengono informazioni dallo stack di chiamate di un oggetto eccezione.</span><span class="sxs-lookup"><span data-stu-id="a0a80-103">Gets the specified number of [CorDebugExceptionObjectStackFrame](cordebugexceptionobjectstackframe-structure.md) instances that contain information from an exception object's call stack.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0a80-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a0a80-104">Syntax</span></span>  
  
```cpp  
HRESULT Next(  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)] CorDebugExceptionObjectStackFrame values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a0a80-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a0a80-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="a0a80-106">in Numero di istanze di [CorDebugExceptionObjectStackFrame](cordebugexceptionobjectstackframe-structure.md) da recuperare.</span><span class="sxs-lookup"><span data-stu-id="a0a80-106">[in] The number of [CorDebugExceptionObjectStackFrame](cordebugexceptionobjectstackframe-structure.md) instances to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="a0a80-107">out Matrice di puntatori, ciascuno dei quali punta a un oggetto [CorDebugExceptionObjectStackFrame](cordebugexceptionobjectstackframe-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="a0a80-107">[out] An array of pointers, each of which points to a [CorDebugExceptionObjectStackFrame](cordebugexceptionobjectstackframe-structure.md) object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="a0a80-108">out Puntatore al numero di istanze di [CorDebugExceptionObjectStackFrame](cordebugexceptionobjectstackframe-structure.md) effettivamente restituite.</span><span class="sxs-lookup"><span data-stu-id="a0a80-108">[out] A pointer to the number of [CorDebugExceptionObjectStackFrame](cordebugexceptionobjectstackframe-structure.md) instances actually returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a0a80-109">Note</span><span class="sxs-lookup"><span data-stu-id="a0a80-109">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a0a80-110">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="a0a80-110">Requirements</span></span>  
 <span data-ttu-id="a0a80-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a0a80-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a0a80-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a0a80-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a0a80-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a0a80-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a0a80-114">**Versioni .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a0a80-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0a80-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a0a80-115">See also</span></span>

- [<span data-ttu-id="a0a80-116">Interfaccia ICorDebugExceptionObjectCallStackEnum</span><span class="sxs-lookup"><span data-stu-id="a0a80-116">ICorDebugExceptionObjectCallStackEnum Interface</span></span>](icordebugexceptionobjectcallstackenum-interface.md)
- [<span data-ttu-id="a0a80-117">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="a0a80-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
