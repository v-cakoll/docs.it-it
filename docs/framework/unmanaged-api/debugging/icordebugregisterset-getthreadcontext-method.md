---
title: Metodo ICorDebugRegisterSet::GetThreadContext
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet.GetThreadContext
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet::GetThreadContext
helpviewer_keywords:
- GetThreadContext method, ICorDebugRegisterSet interface [.NET Framework debugging]
- ICorDebugRegisterSet::GetThreadContext method [.NET Framework debugging]
ms.assetid: 0f63400b-dc1c-48d6-b51a-75c3f7f28e03
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c1ee576f41d20fdf4523fb4b566c3f2ce870d62c
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57469092"
---
# <a name="icordebugregistersetgetthreadcontext-method"></a><span data-ttu-id="d6ba2-102">Metodo ICorDebugRegisterSet::GetThreadContext</span><span class="sxs-lookup"><span data-stu-id="d6ba2-102">ICorDebugRegisterSet::GetThreadContext Method</span></span>
<span data-ttu-id="d6ba2-103">Ottiene il contesto del thread corrente.</span><span class="sxs-lookup"><span data-stu-id="d6ba2-103">Gets the context of the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6ba2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d6ba2-104">Syntax</span></span>  
  
```  
HRESULT GetThreadContext(  
    [in] ULONG32 contextSize,  
    [in, out, length_is(contextSize),  
        size_is(contextSize)] BYTE context[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d6ba2-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d6ba2-105">Parameters</span></span>  
 `contextSize`  
 <span data-ttu-id="d6ba2-106">[in] Le dimensioni, in byte, del `context` matrice.</span><span class="sxs-lookup"><span data-stu-id="d6ba2-106">[in] The size, in bytes, of the `context` array.</span></span>  
  
 `context`  
 <span data-ttu-id="d6ba2-107">[in, out] Una matrice di byte che compongono Win32 `CONTEXT` struttura per la piattaforma corrente.</span><span class="sxs-lookup"><span data-stu-id="d6ba2-107">[in, out] An array of bytes that compose the Win32 `CONTEXT` structure for the current platform.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d6ba2-108">Note</span><span class="sxs-lookup"><span data-stu-id="d6ba2-108">Remarks</span></span>  
 <span data-ttu-id="d6ba2-109">Il debugger deve chiamare questa funzione anziché Win32 `GetThreadContext` funzionare, perché il thread potrebbe essere in uno stato "cui" in cui il contesto è stato modificato temporaneamente.</span><span class="sxs-lookup"><span data-stu-id="d6ba2-109">The debugger should call this function instead of the Win32 `GetThreadContext` function, because the thread may be in a "hijacked" state where its context has been temporarily changed.</span></span> <span data-ttu-id="d6ba2-110">I dati restituiti sono Win32 `CONTEXT` struttura per la piattaforma corrente.</span><span class="sxs-lookup"><span data-stu-id="d6ba2-110">The data returned is a Win32 `CONTEXT` structure for the current platform.</span></span>  
  
 <span data-ttu-id="d6ba2-111">Per i frame foglia, i client devono controllare i registri che sono validi con [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getregistersavailable-method.md).</span><span class="sxs-lookup"><span data-stu-id="d6ba2-111">For non-leaf frames, clients should check which registers are valid by using [ICorDebugRegisterSet::GetRegistersAvailable](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getregistersavailable-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d6ba2-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d6ba2-112">Requirements</span></span>  
 <span data-ttu-id="d6ba2-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d6ba2-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d6ba2-114">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d6ba2-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d6ba2-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d6ba2-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d6ba2-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d6ba2-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6ba2-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d6ba2-117">See also</span></span>
- [<span data-ttu-id="d6ba2-118">Interfaccia ICorDebugRegisterSet</span><span class="sxs-lookup"><span data-stu-id="d6ba2-118">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)
- [<span data-ttu-id="d6ba2-119">Interfaccia ICorDebugRegisterSet2</span><span class="sxs-lookup"><span data-stu-id="d6ba2-119">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
