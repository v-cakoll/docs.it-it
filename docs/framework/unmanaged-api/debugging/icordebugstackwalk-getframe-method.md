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
ms.openlocfilehash: 89576e2b3d5fb4df0cccfdd28c80a5cb67331597
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791892"
---
# <a name="icordebugstackwalkgetframe-method"></a><span data-ttu-id="668dc-102">Metodo ICorDebugStackWalk::GetFrame</span><span class="sxs-lookup"><span data-stu-id="668dc-102">ICorDebugStackWalk::GetFrame Method</span></span>
<span data-ttu-id="668dc-103">Ottiene il frame corrente nell'oggetto [ICorDebugStackWalk](icordebugstackwalk-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="668dc-103">Gets the current frame in the [ICorDebugStackWalk](icordebugstackwalk-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="668dc-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="668dc-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFrame([out] ICorDebugFrame ** pFrame);  
```  
  
## <a name="parameters"></a><span data-ttu-id="668dc-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="668dc-105">Parameters</span></span>  
 `pFrame`  
 <span data-ttu-id="668dc-106">in Puntatore all'indirizzo dell'oggetto frame creato che rappresenta il frame corrente nello stack.</span><span class="sxs-lookup"><span data-stu-id="668dc-106">[in] A pointer to the address of the created frame object that represents the current frame in the stack.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="668dc-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="668dc-107">Return Value</span></span>  
 <span data-ttu-id="668dc-108">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="668dc-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="668dc-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="668dc-109">HRESULT</span></span>|<span data-ttu-id="668dc-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="668dc-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="668dc-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="668dc-111">S_OK</span></span>|<span data-ttu-id="668dc-112">Il runtime ha restituito correttamente il frame corrente.</span><span class="sxs-lookup"><span data-stu-id="668dc-112">The runtime successfully returned the current frame.</span></span>|  
|<span data-ttu-id="668dc-113">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="668dc-113">E_FAIL</span></span>|<span data-ttu-id="668dc-114">Il frame corrente non è stato restituito.</span><span class="sxs-lookup"><span data-stu-id="668dc-114">The current frame was not returned.</span></span>|  
|<span data-ttu-id="668dc-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="668dc-115">S_FALSE</span></span>|<span data-ttu-id="668dc-116">Il frame corrente è un stack frame nativo.</span><span class="sxs-lookup"><span data-stu-id="668dc-116">The current frame is a native stack frame.</span></span>|  
|<span data-ttu-id="668dc-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="668dc-117">E_INVALIDARG</span></span>|<span data-ttu-id="668dc-118">`pFrame` è null.</span><span class="sxs-lookup"><span data-stu-id="668dc-118">`pFrame` is null.</span></span>|  
|<span data-ttu-id="668dc-119">CORDBG_E_PAST_END_OF_STACK</span><span class="sxs-lookup"><span data-stu-id="668dc-119">CORDBG_E_PAST_END_OF_STACK</span></span>|<span data-ttu-id="668dc-120">Il puntatore al frame è già alla fine dello stack. non è pertanto possibile accedere a nessun frame aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="668dc-120">The frame pointer is already at the end of the stack; therefore, no additional frames can be accessed.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="668dc-121">Eccezioni</span><span class="sxs-lookup"><span data-stu-id="668dc-121">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="668dc-122">Note</span><span class="sxs-lookup"><span data-stu-id="668dc-122">Remarks</span></span>  
 <span data-ttu-id="668dc-123">`ICorDebugStackWalk` restituisce solo stack frame effettivi.</span><span class="sxs-lookup"><span data-stu-id="668dc-123">`ICorDebugStackWalk` returns only actual stack frames.</span></span> <span data-ttu-id="668dc-124">Usare il metodo [ICorDebugThread3:: GetActiveInternalFrames](icordebugthread3-getactiveinternalframes-method.md) per restituire frame interni.</span><span class="sxs-lookup"><span data-stu-id="668dc-124">Use the [ICorDebugThread3::GetActiveInternalFrames](icordebugthread3-getactiveinternalframes-method.md) method to return internal frames.</span></span> <span data-ttu-id="668dc-125">(I frame interni sono strutture di dati inserite nello stack dal runtime per archiviare i dati temporanei).</span><span class="sxs-lookup"><span data-stu-id="668dc-125">(Internal frames are data structures pushed onto the stack by the runtime to store temporary data.)</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="668dc-126">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="668dc-126">Requirements</span></span>  
 <span data-ttu-id="668dc-127">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="668dc-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="668dc-128">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="668dc-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="668dc-129">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="668dc-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="668dc-130">**Versioni .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="668dc-130">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="668dc-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="668dc-131">See also</span></span>

- [<span data-ttu-id="668dc-132">Interfaccia ICorDebugStackWalk</span><span class="sxs-lookup"><span data-stu-id="668dc-132">ICorDebugStackWalk Interface</span></span>](icordebugstackwalk-interface.md)
- [<span data-ttu-id="668dc-133">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="668dc-133">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="668dc-134">Debug</span><span class="sxs-lookup"><span data-stu-id="668dc-134">Debugging</span></span>](index.md)
