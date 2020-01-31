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
ms.openlocfilehash: 8137d5477b75b864e223852cf524ac8c5b6c0f2b
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792084"
---
# <a name="icordebugregistersetgetthreadcontext-method"></a><span data-ttu-id="07bca-102">Metodo ICorDebugRegisterSet::GetThreadContext</span><span class="sxs-lookup"><span data-stu-id="07bca-102">ICorDebugRegisterSet::GetThreadContext Method</span></span>
<span data-ttu-id="07bca-103">Ottiene il contesto del thread corrente.</span><span class="sxs-lookup"><span data-stu-id="07bca-103">Gets the context of the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="07bca-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="07bca-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadContext(  
    [in] ULONG32 contextSize,  
    [in, out, length_is(contextSize),  
        size_is(contextSize)] BYTE context[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="07bca-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="07bca-105">Parameters</span></span>  
 `contextSize`  
 <span data-ttu-id="07bca-106">in Dimensione, in byte, della matrice `context`.</span><span class="sxs-lookup"><span data-stu-id="07bca-106">[in] The size, in bytes, of the `context` array.</span></span>  
  
 `context`  
 <span data-ttu-id="07bca-107">[in, out] Matrice di byte che compongono la struttura di `CONTEXT` Win32 per la piattaforma corrente.</span><span class="sxs-lookup"><span data-stu-id="07bca-107">[in, out] An array of bytes that compose the Win32 `CONTEXT` structure for the current platform.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="07bca-108">Note</span><span class="sxs-lookup"><span data-stu-id="07bca-108">Remarks</span></span>  
 <span data-ttu-id="07bca-109">Il debugger deve chiamare questa funzione al posto della funzione Win32 `GetThreadContext`, perché il thread potrebbe trovarsi in uno stato di "Hijack" in cui il contesto è stato modificato temporaneamente.</span><span class="sxs-lookup"><span data-stu-id="07bca-109">The debugger should call this function instead of the Win32 `GetThreadContext` function, because the thread may be in a "hijacked" state where its context has been temporarily changed.</span></span> <span data-ttu-id="07bca-110">I dati restituiti sono una struttura di `CONTEXT` Win32 per la piattaforma corrente.</span><span class="sxs-lookup"><span data-stu-id="07bca-110">The data returned is a Win32 `CONTEXT` structure for the current platform.</span></span>  
  
 <span data-ttu-id="07bca-111">Per i frame non foglia, i client devono verificare quali registri sono validi usando [ICorDebugRegisterSet:: GetRegistersAvailable](icordebugregisterset-getregistersavailable-method.md).</span><span class="sxs-lookup"><span data-stu-id="07bca-111">For non-leaf frames, clients should check which registers are valid by using [ICorDebugRegisterSet::GetRegistersAvailable](icordebugregisterset-getregistersavailable-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="07bca-112">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="07bca-112">Requirements</span></span>  
 <span data-ttu-id="07bca-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="07bca-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="07bca-114">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="07bca-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="07bca-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="07bca-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="07bca-116">**Versioni .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="07bca-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07bca-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="07bca-117">See also</span></span>

- [<span data-ttu-id="07bca-118">Interfaccia ICorDebugRegisterSet</span><span class="sxs-lookup"><span data-stu-id="07bca-118">ICorDebugRegisterSet Interface</span></span>](icordebugregisterset-interface.md)
- [<span data-ttu-id="07bca-119">Interfaccia ICorDebugRegisterSet2</span><span class="sxs-lookup"><span data-stu-id="07bca-119">ICorDebugRegisterSet2 Interface</span></span>](icordebugregisterset2-interface.md)
