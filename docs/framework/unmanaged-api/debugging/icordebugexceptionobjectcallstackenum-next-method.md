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
ms.openlocfilehash: 6fce9f61e222d0fc1763495de162a94a7fc22689
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/08/2020
ms.locfileid: "82975979"
---
# <a name="icordebugexceptionobjectcallstackenumnext-method"></a><span data-ttu-id="983d5-102">Metodo ICorDebugExceptionObjectCallStackEnum::Next</span><span class="sxs-lookup"><span data-stu-id="983d5-102">ICorDebugExceptionObjectCallStackEnum::Next Method</span></span>
<span data-ttu-id="983d5-103">Ottiene il numero specificato di istanze di [CorDebugExceptionObjectStackFrame](cordebugexceptionobjectstackframe-structure.md) che contengono informazioni dallo stack di chiamate di un oggetto eccezione.</span><span class="sxs-lookup"><span data-stu-id="983d5-103">Gets the specified number of [CorDebugExceptionObjectStackFrame](cordebugexceptionobjectstackframe-structure.md) instances that contain information from an exception object's call stack.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="983d5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="983d5-104">Syntax</span></span>  
  
```cpp  
HRESULT Next(  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)] CorDebugExceptionObjectStackFrame values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="983d5-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="983d5-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="983d5-106">in Numero di istanze di [CorDebugExceptionObjectStackFrame](cordebugexceptionobjectstackframe-structure.md) da recuperare.</span><span class="sxs-lookup"><span data-stu-id="983d5-106">[in] The number of [CorDebugExceptionObjectStackFrame](cordebugexceptionobjectstackframe-structure.md) instances to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="983d5-107">out Matrice di puntatori, ciascuno dei quali punta a un oggetto [CorDebugExceptionObjectStackFrame](cordebugexceptionobjectstackframe-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="983d5-107">[out] An array of pointers, each of which points to a [CorDebugExceptionObjectStackFrame](cordebugexceptionobjectstackframe-structure.md) object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="983d5-108">out Puntatore al numero di istanze di [CorDebugExceptionObjectStackFrame](cordebugexceptionobjectstackframe-structure.md) effettivamente restituite.</span><span class="sxs-lookup"><span data-stu-id="983d5-108">[out] A pointer to the number of [CorDebugExceptionObjectStackFrame](cordebugexceptionobjectstackframe-structure.md) instances actually returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="983d5-109">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="983d5-109">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="983d5-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="983d5-110">Requirements</span></span>  
 <span data-ttu-id="983d5-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="983d5-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="983d5-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="983d5-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="983d5-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="983d5-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="983d5-114">**Versioni .NET Framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="983d5-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="983d5-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="983d5-115">See also</span></span>

- [<span data-ttu-id="983d5-116">Interfaccia ICorDebugExceptionObjectCallStackEnum</span><span class="sxs-lookup"><span data-stu-id="983d5-116">ICorDebugExceptionObjectCallStackEnum Interface</span></span>](icordebugexceptionobjectcallstackenum-interface.md)
- [<span data-ttu-id="983d5-117">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="983d5-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
