---
title: Metodo ICorDebugStackWalk::GetContext
ms.date: 03/30/2017
api_name:
- ICorDebugStackWalk.GetContext Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStackWalk::GetContext
helpviewer_keywords:
- GetContext method, ICorDebugStackWalk interface [.NET Framework debugging]
- ICorDebugStackWalk::GetContext method [.NET Framework debugging]
ms.assetid: 081d1c95-152b-4797-8552-18453eb7b14b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bba1e6c113fb4caa0db8963e238d3eceba0cc8ce
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61782746"
---
# <a name="icordebugstackwalkgetcontext-method"></a><span data-ttu-id="4b6e8-102">Metodo ICorDebugStackWalk::GetContext</span><span class="sxs-lookup"><span data-stu-id="4b6e8-102">ICorDebugStackWalk::GetContext Method</span></span>
<span data-ttu-id="4b6e8-103">Restituisce il contesto per il fotogramma corrente di [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) oggetto.</span><span class="sxs-lookup"><span data-stu-id="4b6e8-103">Returns the context for the current frame in the [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b6e8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4b6e8-104">Syntax</span></span>  
  
```  
HRESULT GetContext([in]  ULONG32 contextFlags,  
                   [in]  ULONG32 contextBufSize,  
                   [out] ULONG32* contextSize,  
                   [out, size_is(contextBufSize)] BYTE contextBuf[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4b6e8-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="4b6e8-105">Parameters</span></span>  
 `contextFlags`  
 <span data-ttu-id="4b6e8-106">[in] Flag che indicano il contenuto richiesto del buffer del contesto (definite in Winnt. H).</span><span class="sxs-lookup"><span data-stu-id="4b6e8-106">[in] Flags that indicate the requested contents of the context buffer (defined in WinNT.h).</span></span>  
  
 `contextBufSize`  
 <span data-ttu-id="4b6e8-107">[in] La dimensione allocata del buffer del contesto.</span><span class="sxs-lookup"><span data-stu-id="4b6e8-107">[in] The allocated size of the context buffer.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="4b6e8-108">[out] Le dimensioni effettive del contesto.</span><span class="sxs-lookup"><span data-stu-id="4b6e8-108">[out] The actual size of the context.</span></span> <span data-ttu-id="4b6e8-109">Questo valore deve essere minore o uguale alla dimensione del buffer del contesto.</span><span class="sxs-lookup"><span data-stu-id="4b6e8-109">This value must be less than or equal to the size of the context buffer.</span></span>  
  
 `contextBuf`  
 <span data-ttu-id="4b6e8-110">[out] Il buffer del contesto.</span><span class="sxs-lookup"><span data-stu-id="4b6e8-110">[out] The context buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4b6e8-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="4b6e8-111">Return Value</span></span>  
 <span data-ttu-id="4b6e8-112">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="4b6e8-112">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="4b6e8-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4b6e8-113">HRESULT</span></span>|<span data-ttu-id="4b6e8-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4b6e8-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4b6e8-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="4b6e8-115">S_OK</span></span>|<span data-ttu-id="4b6e8-116">Il contesto per il fotogramma corrente è stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="4b6e8-116">The context for the current frame was successfully returned.</span></span>|  
|<span data-ttu-id="4b6e8-117">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4b6e8-117">E_FAIL</span></span>|<span data-ttu-id="4b6e8-118">Il contesto non può essere restituito.</span><span class="sxs-lookup"><span data-stu-id="4b6e8-118">The context could not be returned.</span></span>|  
|<span data-ttu-id="4b6e8-119">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT BUFFER)</span><span class="sxs-lookup"><span data-stu-id="4b6e8-119">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT BUFFER)</span></span>|<span data-ttu-id="4b6e8-120">Il buffer del contesto è troppo piccolo.</span><span class="sxs-lookup"><span data-stu-id="4b6e8-120">The context buffer is too small.</span></span>|  
|<span data-ttu-id="4b6e8-121">CORDBG_E_PAST_END_OF_STACK</span><span class="sxs-lookup"><span data-stu-id="4b6e8-121">CORDBG_E_PAST_END_OF_STACK</span></span>|<span data-ttu-id="4b6e8-122">Puntatore ai frame è già alla fine dello stack. di conseguenza, nessun frame aggiuntivi sono accessibili.</span><span class="sxs-lookup"><span data-stu-id="4b6e8-122">The frame pointer is already at the end of the stack; therefore, no additional frames can be accessed.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="4b6e8-123">Eccezioni</span><span class="sxs-lookup"><span data-stu-id="4b6e8-123">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4b6e8-124">Note</span><span class="sxs-lookup"><span data-stu-id="4b6e8-124">Remarks</span></span>  
 <span data-ttu-id="4b6e8-125">Poiché la rimozione Ripristina solo un subset dei registri, ad esempio registri non volatili, il contesto potrebbe non corrispondere esattamente allo stato del registro al momento della chiamata.</span><span class="sxs-lookup"><span data-stu-id="4b6e8-125">Because unwinding restores only a subset of the registers, such as non-volatile registers, the context may not exactly match the register state at the time of the call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4b6e8-126">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4b6e8-126">Requirements</span></span>  
 <span data-ttu-id="4b6e8-127">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4b6e8-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4b6e8-128">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4b6e8-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4b6e8-129">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4b6e8-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4b6e8-130">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4b6e8-130">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b6e8-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4b6e8-131">See also</span></span>

- [<span data-ttu-id="4b6e8-132">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="4b6e8-132">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="4b6e8-133">Debug</span><span class="sxs-lookup"><span data-stu-id="4b6e8-133">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
