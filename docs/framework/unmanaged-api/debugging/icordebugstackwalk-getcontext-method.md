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
ms.openlocfilehash: 743b0c8016ca5c0401046166a770d857215429a3
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379212"
---
# <a name="icordebugstackwalkgetcontext-method"></a><span data-ttu-id="8d8d0-102">Metodo ICorDebugStackWalk::GetContext</span><span class="sxs-lookup"><span data-stu-id="8d8d0-102">ICorDebugStackWalk::GetContext Method</span></span>
<span data-ttu-id="8d8d0-103">Restituisce il contesto per il frame corrente nell'oggetto [ICorDebugStackWalk](icordebugstackwalk-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="8d8d0-103">Returns the context for the current frame in the [ICorDebugStackWalk](icordebugstackwalk-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d8d0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8d8d0-104">Syntax</span></span>  
  
```cpp  
HRESULT GetContext([in]  ULONG32 contextFlags,  
                   [in]  ULONG32 contextBufSize,  
                   [out] ULONG32* contextSize,  
                   [out, size_is(contextBufSize)] BYTE contextBuf[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8d8d0-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="8d8d0-105">Parameters</span></span>  
 `contextFlags`  
 <span data-ttu-id="8d8d0-106">in Flag che indicano il contenuto richiesto del buffer del contesto (definito in WinNT. h).</span><span class="sxs-lookup"><span data-stu-id="8d8d0-106">[in] Flags that indicate the requested contents of the context buffer (defined in WinNT.h).</span></span>  
  
 `contextBufSize`  
 <span data-ttu-id="8d8d0-107">in Dimensione allocata del buffer del contesto.</span><span class="sxs-lookup"><span data-stu-id="8d8d0-107">[in] The allocated size of the context buffer.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="8d8d0-108">out Dimensioni effettive del contesto.</span><span class="sxs-lookup"><span data-stu-id="8d8d0-108">[out] The actual size of the context.</span></span> <span data-ttu-id="8d8d0-109">Questo valore deve essere minore o uguale alla dimensione del buffer del contesto.</span><span class="sxs-lookup"><span data-stu-id="8d8d0-109">This value must be less than or equal to the size of the context buffer.</span></span>  
  
 `contextBuf`  
 <span data-ttu-id="8d8d0-110">out Buffer del contesto.</span><span class="sxs-lookup"><span data-stu-id="8d8d0-110">[out] The context buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8d8d0-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="8d8d0-111">Return Value</span></span>  
 <span data-ttu-id="8d8d0-112">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="8d8d0-112">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="8d8d0-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8d8d0-113">HRESULT</span></span>|<span data-ttu-id="8d8d0-114">Description</span><span class="sxs-lookup"><span data-stu-id="8d8d0-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8d8d0-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="8d8d0-115">S_OK</span></span>|<span data-ttu-id="8d8d0-116">Il contesto per il frame corrente è stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="8d8d0-116">The context for the current frame was successfully returned.</span></span>|  
|<span data-ttu-id="8d8d0-117">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8d8d0-117">E_FAIL</span></span>|<span data-ttu-id="8d8d0-118">Non è stato possibile restituire il contesto.</span><span class="sxs-lookup"><span data-stu-id="8d8d0-118">The context could not be returned.</span></span>|  
|<span data-ttu-id="8d8d0-119">HRESULT_FROM_WIN32 (BUFFER ERROR_INSUFFICIENT)</span><span class="sxs-lookup"><span data-stu-id="8d8d0-119">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT BUFFER)</span></span>|<span data-ttu-id="8d8d0-120">Il buffer del contesto è troppo piccolo.</span><span class="sxs-lookup"><span data-stu-id="8d8d0-120">The context buffer is too small.</span></span>|  
|<span data-ttu-id="8d8d0-121">CORDBG_E_PAST_END_OF_STACK</span><span class="sxs-lookup"><span data-stu-id="8d8d0-121">CORDBG_E_PAST_END_OF_STACK</span></span>|<span data-ttu-id="8d8d0-122">Il puntatore al frame è già alla fine dello stack. non è pertanto possibile accedere a nessun frame aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="8d8d0-122">The frame pointer is already at the end of the stack; therefore, no additional frames can be accessed.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="8d8d0-123">Eccezioni</span><span class="sxs-lookup"><span data-stu-id="8d8d0-123">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8d8d0-124">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="8d8d0-124">Remarks</span></span>  
 <span data-ttu-id="8d8d0-125">Poiché la rimozione ripristina solo un subset dei registri, ad esempio i registri non volatili, il contesto potrebbe non corrispondere esattamente allo stato del registro al momento della chiamata.</span><span class="sxs-lookup"><span data-stu-id="8d8d0-125">Because unwinding restores only a subset of the registers, such as non-volatile registers, the context may not exactly match the register state at the time of the call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8d8d0-126">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8d8d0-126">Requirements</span></span>  
 <span data-ttu-id="8d8d0-127">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8d8d0-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8d8d0-128">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8d8d0-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8d8d0-129">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8d8d0-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8d8d0-130">**Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8d8d0-130">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d8d0-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8d8d0-131">See also</span></span>

- [<span data-ttu-id="8d8d0-132">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="8d8d0-132">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="8d8d0-133">Debug</span><span class="sxs-lookup"><span data-stu-id="8d8d0-133">Debugging</span></span>](index.md)
