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
ms.openlocfilehash: 23ad8882ad97e5ceaeb690dfae08a6be55b85f64
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791849"
---
# <a name="icordebugstackwalksetcontext-method"></a><span data-ttu-id="f1448-102">Metodo ICorDebugStackWalk::SetContext</span><span class="sxs-lookup"><span data-stu-id="f1448-102">ICorDebugStackWalk::SetContext Method</span></span>
<span data-ttu-id="f1448-103">Imposta il contesto corrente dell'oggetto [ICorDebugStackWalk](icordebugstackwalk-interface.md) su un contesto valido per il thread.</span><span class="sxs-lookup"><span data-stu-id="f1448-103">Sets the [ICorDebugStackWalk](icordebugstackwalk-interface.md) object’s current context to a valid context for the thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1448-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f1448-104">Syntax</span></span>  
  
```cpp  
HRESULT SetContext([in] CorDebugSetContextFlag flag,  
                   [in] ULONG32 contextSize,  
                   [in, size_is(contextSize)] BYTE context[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f1448-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f1448-105">Parameters</span></span>  
 `flag`  
 <span data-ttu-id="f1448-106">in Flag [CorDebugSetContextFlag](cordebugsetcontextflag-enumeration.md) che indica se il contesto è del frame attivo nello stack o un contesto ottenuto tramite la rimozione dello stack.</span><span class="sxs-lookup"><span data-stu-id="f1448-106">[in] A [CorDebugSetContextFlag](cordebugsetcontextflag-enumeration.md) flag that indicates whether the context is from the active frame on the stack, or a context obtained by unwinding the stack.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="f1448-107">in Dimensione allocata del buffer `CONTEXT`.</span><span class="sxs-lookup"><span data-stu-id="f1448-107">[in] The allocated size of the `CONTEXT` buffer.</span></span>  
  
 `context`  
 <span data-ttu-id="f1448-108">in Buffer `CONTEXT`.</span><span class="sxs-lookup"><span data-stu-id="f1448-108">[in] The `CONTEXT` buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f1448-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="f1448-109">Return Value</span></span>  
 <span data-ttu-id="f1448-110">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="f1448-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="f1448-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f1448-111">HRESULT</span></span>|<span data-ttu-id="f1448-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f1448-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f1448-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="f1448-113">S_OK</span></span>|<span data-ttu-id="f1448-114">Il contesto dell'oggetto `ICorDebugStackWalk` è stato impostato correttamente.</span><span class="sxs-lookup"><span data-stu-id="f1448-114">The `ICorDebugStackWalk` object's context was successfully set.</span></span>|  
|<span data-ttu-id="f1448-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f1448-115">E_FAIL</span></span>|<span data-ttu-id="f1448-116">Il contesto dell'oggetto `ICorDebugStackWalk` non è stato impostato.</span><span class="sxs-lookup"><span data-stu-id="f1448-116">The `ICorDebugStackWalk` object's context was not set.</span></span>|  
|<span data-ttu-id="f1448-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="f1448-117">E_INVALIDARG</span></span>|<span data-ttu-id="f1448-118">Il contesto è null.</span><span class="sxs-lookup"><span data-stu-id="f1448-118">The context is null.</span></span>|  
|<span data-ttu-id="f1448-119">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span><span class="sxs-lookup"><span data-stu-id="f1448-119">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span></span>|<span data-ttu-id="f1448-120">Il buffer del contesto è troppo piccolo.</span><span class="sxs-lookup"><span data-stu-id="f1448-120">The context buffer is too small.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="f1448-121">Eccezioni</span><span class="sxs-lookup"><span data-stu-id="f1448-121">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f1448-122">Note</span><span class="sxs-lookup"><span data-stu-id="f1448-122">Remarks</span></span>  
 <span data-ttu-id="f1448-123">Questo metodo non modifica il contesto corrente del thread.</span><span class="sxs-lookup"><span data-stu-id="f1448-123">This method does not alter the current context of the thread.</span></span>  
  
 <span data-ttu-id="f1448-124">L'impostazione del contesto corrente su un contesto non valido può causare risultati imprevedibili dal camminatore dello stack.</span><span class="sxs-lookup"><span data-stu-id="f1448-124">Setting the current context to an invalid context may cause unpredictable results from the stack walker.</span></span>  
  
 <span data-ttu-id="f1448-125">È possibile recuperare un'esatta copia bit per bit di questo contesto chiamando immediatamente il metodo [ICorDebugStackWalk:: GetContext](icordebugstackwalk-getcontext-method.md) .</span><span class="sxs-lookup"><span data-stu-id="f1448-125">You can retrieve an exact bitwise copy of this context by immediately calling the [ICorDebugStackWalk::GetContext](icordebugstackwalk-getcontext-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f1448-126">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="f1448-126">Requirements</span></span>  
 <span data-ttu-id="f1448-127">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f1448-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f1448-128">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f1448-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f1448-129">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f1448-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f1448-130">**Versioni .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f1448-130">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1448-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f1448-131">See also</span></span>

- [<span data-ttu-id="f1448-132">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="f1448-132">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="f1448-133">Debug</span><span class="sxs-lookup"><span data-stu-id="f1448-133">Debugging</span></span>](index.md)
