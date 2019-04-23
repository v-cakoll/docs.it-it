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
ms.openlocfilehash: 253a25fdfc1f00adbc20388660caf6c227030a1b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59111241"
---
# <a name="icordebugstackwalkgetframe-method"></a><span data-ttu-id="14697-102">Metodo ICorDebugStackWalk::GetFrame</span><span class="sxs-lookup"><span data-stu-id="14697-102">ICorDebugStackWalk::GetFrame Method</span></span>
<span data-ttu-id="14697-103">Ottiene il frame corrente nella [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) oggetto.</span><span class="sxs-lookup"><span data-stu-id="14697-103">Gets the current frame in the [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="14697-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="14697-104">Syntax</span></span>  
  
```  
HRESULT GetFrame([out] ICorDebugFrame ** pFrame);  
```  
  
## <a name="parameters"></a><span data-ttu-id="14697-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="14697-105">Parameters</span></span>  
 `pFrame`  
 <span data-ttu-id="14697-106">[in] Un puntatore all'indirizzo dell'oggetto che rappresenta il frame corrente nello stack frame creato.</span><span class="sxs-lookup"><span data-stu-id="14697-106">[in] A pointer to the address of the created frame object that represents the current frame in the stack.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="14697-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="14697-107">Return Value</span></span>  
 <span data-ttu-id="14697-108">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="14697-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="14697-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="14697-109">HRESULT</span></span>|<span data-ttu-id="14697-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="14697-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="14697-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="14697-111">S_OK</span></span>|<span data-ttu-id="14697-112">Il runtime restituito correttamente il frame corrente.</span><span class="sxs-lookup"><span data-stu-id="14697-112">The runtime successfully returned the current frame.</span></span>|  
|<span data-ttu-id="14697-113">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="14697-113">E_FAIL</span></span>|<span data-ttu-id="14697-114">Il frame corrente non è stato restituito.</span><span class="sxs-lookup"><span data-stu-id="14697-114">The current frame was not returned.</span></span>|  
|<span data-ttu-id="14697-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="14697-115">S_FALSE</span></span>|<span data-ttu-id="14697-116">Il frame corrente è uno stack frame nativo.</span><span class="sxs-lookup"><span data-stu-id="14697-116">The current frame is a native stack frame.</span></span>|  
|<span data-ttu-id="14697-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="14697-117">E_INVALIDARG</span></span>|<span data-ttu-id="14697-118">`pFrame` è null.</span><span class="sxs-lookup"><span data-stu-id="14697-118">`pFrame` is null.</span></span>|  
|<span data-ttu-id="14697-119">CORDBG_E_PAST_END_OF_STACK</span><span class="sxs-lookup"><span data-stu-id="14697-119">CORDBG_E_PAST_END_OF_STACK</span></span>|<span data-ttu-id="14697-120">Puntatore ai frame è già alla fine dello stack. di conseguenza, nessun frame aggiuntivi sono accessibili.</span><span class="sxs-lookup"><span data-stu-id="14697-120">The frame pointer is already at the end of the stack; therefore, no additional frames can be accessed.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="14697-121">Eccezioni</span><span class="sxs-lookup"><span data-stu-id="14697-121">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="14697-122">Note</span><span class="sxs-lookup"><span data-stu-id="14697-122">Remarks</span></span>  
 <span data-ttu-id="14697-123">`ICorDebugStackWalk` Restituisce solo gli stack frame effettivi.</span><span class="sxs-lookup"><span data-stu-id="14697-123">`ICorDebugStackWalk` returns only actual stack frames.</span></span> <span data-ttu-id="14697-124">Usare la [ICorDebugThread3::GetActiveInternalFrames](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-getactiveinternalframes-method.md) metodo per restituire i frame interni.</span><span class="sxs-lookup"><span data-stu-id="14697-124">Use the [ICorDebugThread3::GetActiveInternalFrames](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-getactiveinternalframes-method.md) method to return internal frames.</span></span> <span data-ttu-id="14697-125">(Frame interni sono strutture di dati inserite nello stack dal runtime per archiviare dati temporanei).</span><span class="sxs-lookup"><span data-stu-id="14697-125">(Internal frames are data structures pushed onto the stack by the runtime to store temporary data.)</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="14697-126">Requisiti</span><span class="sxs-lookup"><span data-stu-id="14697-126">Requirements</span></span>  
 <span data-ttu-id="14697-127">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="14697-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="14697-128">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="14697-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="14697-129">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="14697-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="14697-130">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="14697-130">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14697-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="14697-131">See also</span></span>

- [<span data-ttu-id="14697-132">Interfaccia ICorDebugStackWalk</span><span class="sxs-lookup"><span data-stu-id="14697-132">ICorDebugStackWalk Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md)
- [<span data-ttu-id="14697-133">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="14697-133">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="14697-134">Debug</span><span class="sxs-lookup"><span data-stu-id="14697-134">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
