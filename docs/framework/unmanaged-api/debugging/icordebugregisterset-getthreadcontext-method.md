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
ms.openlocfilehash: 04ae3c4dd663351eaf1a58646e24e8ae95aeb9ad
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378287"
---
# <a name="icordebugregistersetgetthreadcontext-method"></a><span data-ttu-id="d3d0c-102">Metodo ICorDebugRegisterSet::GetThreadContext</span><span class="sxs-lookup"><span data-stu-id="d3d0c-102">ICorDebugRegisterSet::GetThreadContext Method</span></span>
<span data-ttu-id="d3d0c-103">Ottiene il contesto del thread corrente.</span><span class="sxs-lookup"><span data-stu-id="d3d0c-103">Gets the context of the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3d0c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d3d0c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadContext(  
    [in] ULONG32 contextSize,  
    [in, out, length_is(contextSize),  
        size_is(contextSize)] BYTE context[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d3d0c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d3d0c-105">Parameters</span></span>  
 `contextSize`  
 <span data-ttu-id="d3d0c-106">in Dimensione, in byte, della `context` matrice.</span><span class="sxs-lookup"><span data-stu-id="d3d0c-106">[in] The size, in bytes, of the `context` array.</span></span>  
  
 `context`  
 <span data-ttu-id="d3d0c-107">[in, out] Matrice di byte che compongono la `CONTEXT` struttura Win32 per la piattaforma corrente.</span><span class="sxs-lookup"><span data-stu-id="d3d0c-107">[in, out] An array of bytes that compose the Win32 `CONTEXT` structure for the current platform.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d3d0c-108">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="d3d0c-108">Remarks</span></span>  
 <span data-ttu-id="d3d0c-109">Il debugger deve chiamare questa funzione al posto della `GetThreadContext` funzione Win32, perché il thread potrebbe trovarsi in uno stato di "Hijack" in cui il contesto è stato modificato temporaneamente.</span><span class="sxs-lookup"><span data-stu-id="d3d0c-109">The debugger should call this function instead of the Win32 `GetThreadContext` function, because the thread may be in a "hijacked" state where its context has been temporarily changed.</span></span> <span data-ttu-id="d3d0c-110">I dati restituiti sono una `CONTEXT` struttura Win32 per la piattaforma corrente.</span><span class="sxs-lookup"><span data-stu-id="d3d0c-110">The data returned is a Win32 `CONTEXT` structure for the current platform.</span></span>  
  
 <span data-ttu-id="d3d0c-111">Per i frame non foglia, i client devono verificare quali registri sono validi usando [ICorDebugRegisterSet:: GetRegistersAvailable](icordebugregisterset-getregistersavailable-method.md).</span><span class="sxs-lookup"><span data-stu-id="d3d0c-111">For non-leaf frames, clients should check which registers are valid by using [ICorDebugRegisterSet::GetRegistersAvailable](icordebugregisterset-getregistersavailable-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d3d0c-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d3d0c-112">Requirements</span></span>  
 <span data-ttu-id="d3d0c-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d3d0c-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d3d0c-114">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d3d0c-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d3d0c-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d3d0c-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d3d0c-116">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d3d0c-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3d0c-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d3d0c-117">See also</span></span>

- [<span data-ttu-id="d3d0c-118">Interfaccia ICorDebugRegisterSet</span><span class="sxs-lookup"><span data-stu-id="d3d0c-118">ICorDebugRegisterSet Interface</span></span>](icordebugregisterset-interface.md)
- [<span data-ttu-id="d3d0c-119">Interfaccia ICorDebugRegisterSet2</span><span class="sxs-lookup"><span data-stu-id="d3d0c-119">ICorDebugRegisterSet2 Interface</span></span>](icordebugregisterset2-interface.md)
