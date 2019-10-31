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
ms.openlocfilehash: 90156152a2c133446dedbe22426785ab63f8dfb9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131806"
---
# <a name="icordebugstackwalksetcontext-method"></a><span data-ttu-id="7c943-102">Metodo ICorDebugStackWalk::SetContext</span><span class="sxs-lookup"><span data-stu-id="7c943-102">ICorDebugStackWalk::SetContext Method</span></span>
<span data-ttu-id="7c943-103">Imposta il contesto corrente dell'oggetto [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) su un contesto valido per il thread.</span><span class="sxs-lookup"><span data-stu-id="7c943-103">Sets the [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) object’s current context to a valid context for the thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c943-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7c943-104">Syntax</span></span>  
  
```cpp  
HRESULT SetContext([in] CorDebugSetContextFlag flag,  
                   [in] ULONG32 contextSize,  
                   [in, size_is(contextSize)] BYTE context[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7c943-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="7c943-105">Parameters</span></span>  
 `flag`  
 <span data-ttu-id="7c943-106">in Flag [CorDebugSetContextFlag](../../../../docs/framework/unmanaged-api/debugging/cordebugsetcontextflag-enumeration.md) che indica se il contesto è del frame attivo nello stack o un contesto ottenuto tramite la rimozione dello stack.</span><span class="sxs-lookup"><span data-stu-id="7c943-106">[in] A [CorDebugSetContextFlag](../../../../docs/framework/unmanaged-api/debugging/cordebugsetcontextflag-enumeration.md) flag that indicates whether the context is from the active frame on the stack, or a context obtained by unwinding the stack.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="7c943-107">in Dimensione allocata del buffer `CONTEXT`.</span><span class="sxs-lookup"><span data-stu-id="7c943-107">[in] The allocated size of the `CONTEXT` buffer.</span></span>  
  
 `context`  
 <span data-ttu-id="7c943-108">in Buffer `CONTEXT`.</span><span class="sxs-lookup"><span data-stu-id="7c943-108">[in] The `CONTEXT` buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7c943-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="7c943-109">Return Value</span></span>  
 <span data-ttu-id="7c943-110">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="7c943-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="7c943-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7c943-111">HRESULT</span></span>|<span data-ttu-id="7c943-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7c943-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7c943-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="7c943-113">S_OK</span></span>|<span data-ttu-id="7c943-114">Il contesto dell'oggetto `ICorDebugStackWalk` è stato impostato correttamente.</span><span class="sxs-lookup"><span data-stu-id="7c943-114">The `ICorDebugStackWalk` object's context was successfully set.</span></span>|  
|<span data-ttu-id="7c943-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7c943-115">E_FAIL</span></span>|<span data-ttu-id="7c943-116">Il contesto dell'oggetto `ICorDebugStackWalk` non è stato impostato.</span><span class="sxs-lookup"><span data-stu-id="7c943-116">The `ICorDebugStackWalk` object's context was not set.</span></span>|  
|<span data-ttu-id="7c943-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="7c943-117">E_INVALIDARG</span></span>|<span data-ttu-id="7c943-118">Il contesto è null.</span><span class="sxs-lookup"><span data-stu-id="7c943-118">The context is null.</span></span>|  
|<span data-ttu-id="7c943-119">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span><span class="sxs-lookup"><span data-stu-id="7c943-119">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span></span>|<span data-ttu-id="7c943-120">Il buffer del contesto è troppo piccolo.</span><span class="sxs-lookup"><span data-stu-id="7c943-120">The context buffer is too small.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="7c943-121">Eccezioni</span><span class="sxs-lookup"><span data-stu-id="7c943-121">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7c943-122">Note</span><span class="sxs-lookup"><span data-stu-id="7c943-122">Remarks</span></span>  
 <span data-ttu-id="7c943-123">Questo metodo non modifica il contesto corrente del thread.</span><span class="sxs-lookup"><span data-stu-id="7c943-123">This method does not alter the current context of the thread.</span></span>  
  
 <span data-ttu-id="7c943-124">L'impostazione del contesto corrente su un contesto non valido può causare risultati imprevedibili dal camminatore dello stack.</span><span class="sxs-lookup"><span data-stu-id="7c943-124">Setting the current context to an invalid context may cause unpredictable results from the stack walker.</span></span>  
  
 <span data-ttu-id="7c943-125">È possibile recuperare un'esatta copia bit per bit di questo contesto chiamando immediatamente il metodo [ICorDebugStackWalk:: GetContext](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md) .</span><span class="sxs-lookup"><span data-stu-id="7c943-125">You can retrieve an exact bitwise copy of this context by immediately calling the [ICorDebugStackWalk::GetContext](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7c943-126">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7c943-126">Requirements</span></span>  
 <span data-ttu-id="7c943-127">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7c943-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c943-128">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7c943-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7c943-129">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7c943-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7c943-130">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c943-130">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c943-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7c943-131">See also</span></span>

- [<span data-ttu-id="7c943-132">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="7c943-132">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="7c943-133">Debug</span><span class="sxs-lookup"><span data-stu-id="7c943-133">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
