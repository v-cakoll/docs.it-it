---
title: Metodo ICorDebugStackWalk::SetContext
ms.date: 03/30/2017
api_name:
- ICorDebugStackWalk.SetContext Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStackWalk::SetContext
helpviewer_keywords:
- SetContext method [.NET Framework debugging]
- ICorDebugStackWalk::SetContext method [.NET Framework debugging]
ms.assetid: bac0b156-31a3-4e7f-be4d-ab21789c81f1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 22eae4d59cbd6eba14e5784526c33774300a8367
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54493716"
---
# <a name="icordebugstackwalksetcontext-method"></a><span data-ttu-id="d58bb-102">Metodo ICorDebugStackWalk::SetContext</span><span class="sxs-lookup"><span data-stu-id="d58bb-102">ICorDebugStackWalk::SetContext Method</span></span>
<span data-ttu-id="d58bb-103">Imposta il [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) contesto corrente dell'oggetto a un contesto valido per il thread.</span><span class="sxs-lookup"><span data-stu-id="d58bb-103">Sets the [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) object’s current context to a valid context for the thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d58bb-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d58bb-104">Syntax</span></span>  
  
```  
HRESULT SetContext([in] CorDebugSetContextFlag flag,  
                   [in] ULONG32 contextSize,  
                   [in, size_is(contextSize)] BYTE context[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d58bb-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d58bb-105">Parameters</span></span>  
 `flag`  
 <span data-ttu-id="d58bb-106">[in] Oggetto [CorDebugSetContextFlag](../../../../docs/framework/unmanaged-api/debugging/cordebugsetcontextflag-enumeration.md) flag che indica se il contesto proviene dal frame attivo nello stack, o un contesto ottenuto dalla rimozione dello stack.</span><span class="sxs-lookup"><span data-stu-id="d58bb-106">[in] A [CorDebugSetContextFlag](../../../../docs/framework/unmanaged-api/debugging/cordebugsetcontextflag-enumeration.md) flag that indicates whether the context is from the active frame on the stack, or a context obtained by unwinding the stack.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="d58bb-107">[in] Le dimensioni allocate del `CONTEXT` buffer.</span><span class="sxs-lookup"><span data-stu-id="d58bb-107">[in] The allocated size of the `CONTEXT` buffer.</span></span>  
  
 `context`  
 <span data-ttu-id="d58bb-108">[in] Il `CONTEXT` buffer.</span><span class="sxs-lookup"><span data-stu-id="d58bb-108">[in] The `CONTEXT` buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d58bb-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="d58bb-109">Return Value</span></span>  
 <span data-ttu-id="d58bb-110">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="d58bb-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="d58bb-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d58bb-111">HRESULT</span></span>|<span data-ttu-id="d58bb-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d58bb-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d58bb-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="d58bb-113">S_OK</span></span>|<span data-ttu-id="d58bb-114">Il `ICorDebugStackWalk` contesto dell'oggetto è stato impostato correttamente.</span><span class="sxs-lookup"><span data-stu-id="d58bb-114">The `ICorDebugStackWalk` object's context was successfully set.</span></span>|  
|<span data-ttu-id="d58bb-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d58bb-115">E_FAIL</span></span>|<span data-ttu-id="d58bb-116">Il `ICorDebugStackWalk` contesto dell'oggetto non è stato impostato.</span><span class="sxs-lookup"><span data-stu-id="d58bb-116">The `ICorDebugStackWalk` object's context was not set.</span></span>|  
|<span data-ttu-id="d58bb-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="d58bb-117">E_INVALIDARG</span></span>|<span data-ttu-id="d58bb-118">Il contesto è null.</span><span class="sxs-lookup"><span data-stu-id="d58bb-118">The context is null.</span></span>|  
|<span data-ttu-id="d58bb-119">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span><span class="sxs-lookup"><span data-stu-id="d58bb-119">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span></span>|<span data-ttu-id="d58bb-120">Il buffer del contesto è troppo piccolo.</span><span class="sxs-lookup"><span data-stu-id="d58bb-120">The context buffer is too small.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="d58bb-121">Eccezioni</span><span class="sxs-lookup"><span data-stu-id="d58bb-121">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d58bb-122">Note</span><span class="sxs-lookup"><span data-stu-id="d58bb-122">Remarks</span></span>  
 <span data-ttu-id="d58bb-123">Questo metodo non modifica il contesto corrente del thread.</span><span class="sxs-lookup"><span data-stu-id="d58bb-123">This method does not alter the current context of the thread.</span></span>  
  
 <span data-ttu-id="d58bb-124">Impostazione del contesto corrente per un contesto non valido può causare risultati imprevedibili dal percorso chiamate dello stack.</span><span class="sxs-lookup"><span data-stu-id="d58bb-124">Setting the current context to an invalid context may cause unpredictable results from the stack walker.</span></span>  
  
 <span data-ttu-id="d58bb-125">È possibile recuperare una copia bit per bit esatta di questo contesto chiamando immediatamente la [ICorDebugStackWalk:: GetContext](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="d58bb-125">You can retrieve an exact bitwise copy of this context by immediately calling the [ICorDebugStackWalk::GetContext](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d58bb-126">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d58bb-126">Requirements</span></span>  
 <span data-ttu-id="d58bb-127">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d58bb-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d58bb-128">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d58bb-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d58bb-129">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d58bb-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d58bb-130">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d58bb-130">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d58bb-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d58bb-131">See also</span></span>
- [<span data-ttu-id="d58bb-132">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="d58bb-132">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="d58bb-133">Debug</span><span class="sxs-lookup"><span data-stu-id="d58bb-133">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
