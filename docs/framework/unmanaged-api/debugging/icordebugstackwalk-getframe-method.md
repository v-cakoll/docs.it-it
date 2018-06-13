---
title: Metodo ICorDebugStackWalk::GetFrame
ms.date: 03/30/2017
api_name:
- ICorDebugStackWalk.GetFrame Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStackWalk::GetFrame
helpviewer_keywords:
- GetFrame method [.NET Framework debugging]
- ICorDebugStackWalk::GetFrame method [.NET Framework debugging]
ms.assetid: 4083b505-5b59-44fb-8c5d-129db6a96c10
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 548a8a7743c02be5734b677010627f847c5bc4b0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33421987"
---
# <a name="icordebugstackwalkgetframe-method"></a><span data-ttu-id="80c6c-102">Metodo ICorDebugStackWalk::GetFrame</span><span class="sxs-lookup"><span data-stu-id="80c6c-102">ICorDebugStackWalk::GetFrame Method</span></span>
<span data-ttu-id="80c6c-103">Ottiene il frame corrente [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) oggetto.</span><span class="sxs-lookup"><span data-stu-id="80c6c-103">Gets the current frame in the [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80c6c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="80c6c-104">Syntax</span></span>  
  
```  
HRESULT GetFrame([out] ICorDebugFrame ** pFrame);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="80c6c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="80c6c-105">Parameters</span></span>  
 `pFrame`  
 <span data-ttu-id="80c6c-106">[in] Un puntatore all'indirizzo dell'oggetto che rappresenta il frame corrente nello stack frame creato.</span><span class="sxs-lookup"><span data-stu-id="80c6c-106">[in] A pointer to the address of the created frame object that represents the current frame in the stack.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="80c6c-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="80c6c-107">Return Value</span></span>  
 <span data-ttu-id="80c6c-108">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="80c6c-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="80c6c-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="80c6c-109">HRESULT</span></span>|<span data-ttu-id="80c6c-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="80c6c-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="80c6c-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="80c6c-111">S_OK</span></span>|<span data-ttu-id="80c6c-112">Il runtime restituito correttamente il frame corrente.</span><span class="sxs-lookup"><span data-stu-id="80c6c-112">The runtime successfully returned the current frame.</span></span>|  
|<span data-ttu-id="80c6c-113">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="80c6c-113">E_FAIL</span></span>|<span data-ttu-id="80c6c-114">Non è stato restituito il frame corrente.</span><span class="sxs-lookup"><span data-stu-id="80c6c-114">The current frame was not returned.</span></span>|  
|<span data-ttu-id="80c6c-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="80c6c-115">S_FALSE</span></span>|<span data-ttu-id="80c6c-116">Il frame corrente è un frame dello stack nativo.</span><span class="sxs-lookup"><span data-stu-id="80c6c-116">The current frame is a native stack frame.</span></span>|  
|<span data-ttu-id="80c6c-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="80c6c-117">E_INVALIDARG</span></span>|<span data-ttu-id="80c6c-118">`pFrame` è null.</span><span class="sxs-lookup"><span data-stu-id="80c6c-118">`pFrame` is null.</span></span>|  
|<span data-ttu-id="80c6c-119">CORDBG_E_PAST_END_OF_STACK</span><span class="sxs-lookup"><span data-stu-id="80c6c-119">CORDBG_E_PAST_END_OF_STACK</span></span>|<span data-ttu-id="80c6c-120">Puntatore ai frame è già alla fine dello stack. Pertanto, non è possibile accedere ulteriori frame.</span><span class="sxs-lookup"><span data-stu-id="80c6c-120">The frame pointer is already at the end of the stack; therefore, no additional frames can be accessed.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="80c6c-121">Eccezioni</span><span class="sxs-lookup"><span data-stu-id="80c6c-121">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="80c6c-122">Note</span><span class="sxs-lookup"><span data-stu-id="80c6c-122">Remarks</span></span>  
 <span data-ttu-id="80c6c-123">`ICorDebugStackWalk` Restituisce solo gli stack frame effettivi.</span><span class="sxs-lookup"><span data-stu-id="80c6c-123">`ICorDebugStackWalk` returns only actual stack frames.</span></span> <span data-ttu-id="80c6c-124">Utilizzare il [ICorDebugThread3:: GetActiveInternalFrames](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-getactiveinternalframes-method.md) per restituire i frame interni.</span><span class="sxs-lookup"><span data-stu-id="80c6c-124">Use the [ICorDebugThread3::GetActiveInternalFrames](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-getactiveinternalframes-method.md) method to return internal frames.</span></span> <span data-ttu-id="80c6c-125">I frame interni sono strutture di dati nello stack dal runtime per archiviare dati temporanei.</span><span class="sxs-lookup"><span data-stu-id="80c6c-125">(Internal frames are data structures pushed onto the stack by the runtime to store temporary data.)</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="80c6c-126">Requisiti</span><span class="sxs-lookup"><span data-stu-id="80c6c-126">Requirements</span></span>  
 <span data-ttu-id="80c6c-127">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="80c6c-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="80c6c-128">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="80c6c-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="80c6c-129">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="80c6c-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="80c6c-130">**Versioni di .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="80c6c-130">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80c6c-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="80c6c-131">See Also</span></span>  
 [<span data-ttu-id="80c6c-132">Interfaccia ICorDebugStackWalk</span><span class="sxs-lookup"><span data-stu-id="80c6c-132">ICorDebugStackWalk Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md)  
 [<span data-ttu-id="80c6c-133">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="80c6c-133">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="80c6c-134">Debug</span><span class="sxs-lookup"><span data-stu-id="80c6c-134">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
