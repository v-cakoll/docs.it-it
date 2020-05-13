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
ms.openlocfilehash: 896e797acc76e8d8034bd964e488317a62eed97b
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378770"
---
# <a name="icordebugstackwalksetcontext-method"></a><span data-ttu-id="ef1f0-102">Metodo ICorDebugStackWalk::SetContext</span><span class="sxs-lookup"><span data-stu-id="ef1f0-102">ICorDebugStackWalk::SetContext Method</span></span>
<span data-ttu-id="ef1f0-103">Imposta il contesto corrente dell'oggetto [ICorDebugStackWalk](icordebugstackwalk-interface.md) su un contesto valido per il thread.</span><span class="sxs-lookup"><span data-stu-id="ef1f0-103">Sets the [ICorDebugStackWalk](icordebugstackwalk-interface.md) object’s current context to a valid context for the thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef1f0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ef1f0-104">Syntax</span></span>  
  
```cpp  
HRESULT SetContext([in] CorDebugSetContextFlag flag,  
                   [in] ULONG32 contextSize,  
                   [in, size_is(contextSize)] BYTE context[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ef1f0-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ef1f0-105">Parameters</span></span>  
 `flag`  
 <span data-ttu-id="ef1f0-106">in Flag [CorDebugSetContextFlag](cordebugsetcontextflag-enumeration.md) che indica se il contesto è del frame attivo nello stack o un contesto ottenuto tramite la rimozione dello stack.</span><span class="sxs-lookup"><span data-stu-id="ef1f0-106">[in] A [CorDebugSetContextFlag](cordebugsetcontextflag-enumeration.md) flag that indicates whether the context is from the active frame on the stack, or a context obtained by unwinding the stack.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="ef1f0-107">in Dimensione allocata del `CONTEXT` buffer.</span><span class="sxs-lookup"><span data-stu-id="ef1f0-107">[in] The allocated size of the `CONTEXT` buffer.</span></span>  
  
 `context`  
 <span data-ttu-id="ef1f0-108">in `CONTEXT`Buffer.</span><span class="sxs-lookup"><span data-stu-id="ef1f0-108">[in] The `CONTEXT` buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ef1f0-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="ef1f0-109">Return Value</span></span>  
 <span data-ttu-id="ef1f0-110">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="ef1f0-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="ef1f0-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ef1f0-111">HRESULT</span></span>|<span data-ttu-id="ef1f0-112">Description</span><span class="sxs-lookup"><span data-stu-id="ef1f0-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ef1f0-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="ef1f0-113">S_OK</span></span>|<span data-ttu-id="ef1f0-114">Il `ICorDebugStackWalk` contesto dell'oggetto è stato impostato correttamente.</span><span class="sxs-lookup"><span data-stu-id="ef1f0-114">The `ICorDebugStackWalk` object's context was successfully set.</span></span>|  
|<span data-ttu-id="ef1f0-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ef1f0-115">E_FAIL</span></span>|<span data-ttu-id="ef1f0-116">Il `ICorDebugStackWalk` contesto dell'oggetto non è stato impostato.</span><span class="sxs-lookup"><span data-stu-id="ef1f0-116">The `ICorDebugStackWalk` object's context was not set.</span></span>|  
|<span data-ttu-id="ef1f0-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="ef1f0-117">E_INVALIDARG</span></span>|<span data-ttu-id="ef1f0-118">Il contesto è null.</span><span class="sxs-lookup"><span data-stu-id="ef1f0-118">The context is null.</span></span>|  
|<span data-ttu-id="ef1f0-119">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span><span class="sxs-lookup"><span data-stu-id="ef1f0-119">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span></span>|<span data-ttu-id="ef1f0-120">Il buffer del contesto è troppo piccolo.</span><span class="sxs-lookup"><span data-stu-id="ef1f0-120">The context buffer is too small.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="ef1f0-121">Eccezioni</span><span class="sxs-lookup"><span data-stu-id="ef1f0-121">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ef1f0-122">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="ef1f0-122">Remarks</span></span>  
 <span data-ttu-id="ef1f0-123">Questo metodo non modifica il contesto corrente del thread.</span><span class="sxs-lookup"><span data-stu-id="ef1f0-123">This method does not alter the current context of the thread.</span></span>  
  
 <span data-ttu-id="ef1f0-124">L'impostazione del contesto corrente su un contesto non valido può causare risultati imprevedibili dal camminatore dello stack.</span><span class="sxs-lookup"><span data-stu-id="ef1f0-124">Setting the current context to an invalid context may cause unpredictable results from the stack walker.</span></span>  
  
 <span data-ttu-id="ef1f0-125">È possibile recuperare un'esatta copia bit per bit di questo contesto chiamando immediatamente il metodo [ICorDebugStackWalk:: GetContext](icordebugstackwalk-getcontext-method.md) .</span><span class="sxs-lookup"><span data-stu-id="ef1f0-125">You can retrieve an exact bitwise copy of this context by immediately calling the [ICorDebugStackWalk::GetContext](icordebugstackwalk-getcontext-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ef1f0-126">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ef1f0-126">Requirements</span></span>  
 <span data-ttu-id="ef1f0-127">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ef1f0-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ef1f0-128">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ef1f0-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ef1f0-129">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ef1f0-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ef1f0-130">**Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ef1f0-130">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef1f0-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ef1f0-131">See also</span></span>

- [<span data-ttu-id="ef1f0-132">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="ef1f0-132">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="ef1f0-133">Debug</span><span class="sxs-lookup"><span data-stu-id="ef1f0-133">Debugging</span></span>](index.md)
