---
title: Metodo ICorDebugStackWalk::GetContext
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugStackWalk.GetContext Method
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugStackWalk::GetContext
helpviewer_keywords:
- GetContext method, ICorDebugStackWalk interface [.NET Framework debugging]
- ICorDebugStackWalk::GetContext method [.NET Framework debugging]
ms.assetid: 081d1c95-152b-4797-8552-18453eb7b14b
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2bdd910862e7198d616e79ec732708f708959d26
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugstackwalkgetcontext-method"></a><span data-ttu-id="4ed72-102">Metodo ICorDebugStackWalk::GetContext</span><span class="sxs-lookup"><span data-stu-id="4ed72-102">ICorDebugStackWalk::GetContext Method</span></span>
<span data-ttu-id="4ed72-103">Restituisce il contesto per il fotogramma corrente il [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) oggetto.</span><span class="sxs-lookup"><span data-stu-id="4ed72-103">Returns the context for the current frame in the [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ed72-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4ed72-104">Syntax</span></span>  
  
```  
HRESULT GetContext([in]  ULONG32 contextFlags,  
                   [in]  ULONG32 contextBufSize,  
                   [out] ULONG32* contextSize,  
                   [out, size_is(contextBufSize)] BYTE contextBuf[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4ed72-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="4ed72-105">Parameters</span></span>  
 `contextFlags`  
 <span data-ttu-id="4ed72-106">[in] Flag che indicano il contenuto del buffer del contesto (definito in Winnt. H) richiesto.</span><span class="sxs-lookup"><span data-stu-id="4ed72-106">[in] Flags that indicate the requested contents of the context buffer (defined in WinNT.h).</span></span>  
  
 `contextBufSize`  
 <span data-ttu-id="4ed72-107">[in] Le dimensioni allocate del buffer del contesto.</span><span class="sxs-lookup"><span data-stu-id="4ed72-107">[in] The allocated size of the context buffer.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="4ed72-108">[out] Le dimensioni effettive del contesto.</span><span class="sxs-lookup"><span data-stu-id="4ed72-108">[out] The actual size of the context.</span></span> <span data-ttu-id="4ed72-109">Questo valore deve essere minore o uguale alla dimensione del buffer del contesto.</span><span class="sxs-lookup"><span data-stu-id="4ed72-109">This value must be less than or equal to the size of the context buffer.</span></span>  
  
 `contextBuf`  
 <span data-ttu-id="4ed72-110">[out] Il buffer del contesto.</span><span class="sxs-lookup"><span data-stu-id="4ed72-110">[out] The context buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4ed72-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="4ed72-111">Return Value</span></span>  
 <span data-ttu-id="4ed72-112">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="4ed72-112">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="4ed72-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4ed72-113">HRESULT</span></span>|<span data-ttu-id="4ed72-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4ed72-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4ed72-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="4ed72-115">S_OK</span></span>|<span data-ttu-id="4ed72-116">Il contesto per il frame corrente è stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="4ed72-116">The context for the current frame was successfully returned.</span></span>|  
|<span data-ttu-id="4ed72-117">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4ed72-117">E_FAIL</span></span>|<span data-ttu-id="4ed72-118">Non è stato possibile restituire il contesto.</span><span class="sxs-lookup"><span data-stu-id="4ed72-118">The context could not be returned.</span></span>|  
|<span data-ttu-id="4ed72-119">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT BUFFER)</span><span class="sxs-lookup"><span data-stu-id="4ed72-119">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT BUFFER)</span></span>|<span data-ttu-id="4ed72-120">Il buffer del contesto è troppo piccolo.</span><span class="sxs-lookup"><span data-stu-id="4ed72-120">The context buffer is too small.</span></span>|  
|<span data-ttu-id="4ed72-121">CORDBG_E_PAST_END_OF_STACK</span><span class="sxs-lookup"><span data-stu-id="4ed72-121">CORDBG_E_PAST_END_OF_STACK</span></span>|<span data-ttu-id="4ed72-122">Puntatore ai frame è già alla fine dello stack. Pertanto, non è possibile accedere ulteriori frame.</span><span class="sxs-lookup"><span data-stu-id="4ed72-122">The frame pointer is already at the end of the stack; therefore, no additional frames can be accessed.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="4ed72-123">Eccezioni</span><span class="sxs-lookup"><span data-stu-id="4ed72-123">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4ed72-124">Note</span><span class="sxs-lookup"><span data-stu-id="4ed72-124">Remarks</span></span>  
 <span data-ttu-id="4ed72-125">Poiché la rimozione Ripristina solo un subset dei registri, ad esempio registri non volatili, il contesto potrebbe non corrispondere esattamente allo stato del registro al momento della chiamata.</span><span class="sxs-lookup"><span data-stu-id="4ed72-125">Because unwinding restores only a subset of the registers, such as non-volatile registers, the context may not exactly match the register state at the time of the call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4ed72-126">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4ed72-126">Requirements</span></span>  
 <span data-ttu-id="4ed72-127">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4ed72-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4ed72-128">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="4ed72-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4ed72-129">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4ed72-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4ed72-130">**Versioni di .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4ed72-130">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ed72-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4ed72-131">See Also</span></span>  
 [<span data-ttu-id="4ed72-132">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="4ed72-132">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="4ed72-133">Debug</span><span class="sxs-lookup"><span data-stu-id="4ed72-133">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
