---
title: Metodo ICorDebugNativeFrame2::GetStackParameterSize
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame2.GetStackParameterSize Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame2::GetStackParameterSize
helpviewer_keywords:
- ICorDebugNativeFrame2::GetStackParameterSize method [.NET Framework debugging]
- GetStackParameterSize method [.NET Framework debugging]
ms.assetid: f6a449c8-a941-43ba-9a90-c98b29ae3c36
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 47968d7550c3d16d201680caab705c0d7c85c784
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59200142"
---
# <a name="icordebugnativeframe2getstackparametersize-method"></a><span data-ttu-id="26b95-102">Metodo ICorDebugNativeFrame2::GetStackParameterSize</span><span class="sxs-lookup"><span data-stu-id="26b95-102">ICorDebugNativeFrame2::GetStackParameterSize Method</span></span>
<span data-ttu-id="26b95-103">Restituisce la dimensione complessiva di parametri nello stack di su sistemi operativi x86.</span><span class="sxs-lookup"><span data-stu-id="26b95-103">Returns the cumulative size of the parameters on the stack on x86 operating systems.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26b95-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="26b95-104">Syntax</span></span>  
  
```  
HRESULT GetStackParameterSize([out] ULONG32 * pSize)  
```  
  
## <a name="parameters"></a><span data-ttu-id="26b95-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="26b95-105">Parameters</span></span>  
 `pSize`  
 <span data-ttu-id="26b95-106">[out] Puntatore alle dimensioni cumulative dei parametri nello stack.</span><span class="sxs-lookup"><span data-stu-id="26b95-106">[out] A pointer to the cumulative size of the parameters on the stack.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="26b95-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="26b95-107">Return Value</span></span>  
 <span data-ttu-id="26b95-108">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="26b95-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="26b95-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="26b95-109">HRESULT</span></span>|<span data-ttu-id="26b95-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="26b95-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="26b95-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="26b95-111">S_OK</span></span>|<span data-ttu-id="26b95-112">La dimensione dello stack è stata restituita correttamente.</span><span class="sxs-lookup"><span data-stu-id="26b95-112">The stack size was successfully returned.</span></span>|  
|<span data-ttu-id="26b95-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="26b95-113">S_FALSE</span></span>|<span data-ttu-id="26b95-114">`GetStackParameterSize` è stato chiamato su una piattaforma non x86.</span><span class="sxs-lookup"><span data-stu-id="26b95-114">`GetStackParameterSize` was called on a non-x86 platform.</span></span>|  
|<span data-ttu-id="26b95-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="26b95-115">E_FAIL</span></span>|<span data-ttu-id="26b95-116">`The size of the parameters could not be returned`.</span><span class="sxs-lookup"><span data-stu-id="26b95-116">`The size of the parameters could not be returned`.</span></span>|  
|<span data-ttu-id="26b95-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="26b95-117">E_INVALIDARG</span></span>|<span data-ttu-id="26b95-118">`pSize` è `null`.</span><span class="sxs-lookup"><span data-stu-id="26b95-118">`pSize` Is `null`.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="26b95-119">Eccezioni</span><span class="sxs-lookup"><span data-stu-id="26b95-119">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="26b95-120">Note</span><span class="sxs-lookup"><span data-stu-id="26b95-120">Remarks</span></span>  
 <span data-ttu-id="26b95-121">Il [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) metodi non regolano il puntatore dello stack per i parametri che vengono inseriti nello stack.</span><span class="sxs-lookup"><span data-stu-id="26b95-121">The [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) methods do not adjust the stack pointer for parameters that are pushed on the stack.</span></span> <span data-ttu-id="26b95-122">In alternativa, è possibile usare il valore restituito da `GetStackParameterSize` per regolare il puntatore dello stack per l'inizializzazione di un agente di rimozione nativa, che viene adattata per i parametri.</span><span class="sxs-lookup"><span data-stu-id="26b95-122">Instead, you can use the value returned by `GetStackParameterSize` to adjust the stack pointer to seed a native unwinder, which does adjust for the parameters.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="26b95-123">Requisiti</span><span class="sxs-lookup"><span data-stu-id="26b95-123">Requirements</span></span>  
 <span data-ttu-id="26b95-124">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="26b95-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="26b95-125">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="26b95-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="26b95-126">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="26b95-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="26b95-127">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="26b95-127">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26b95-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="26b95-128">See also</span></span>

- [<span data-ttu-id="26b95-129">Interfaccia ICorDebugNativeFrame2</span><span class="sxs-lookup"><span data-stu-id="26b95-129">ICorDebugNativeFrame2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-interface.md)
- [<span data-ttu-id="26b95-130">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="26b95-130">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="26b95-131">Debug</span><span class="sxs-lookup"><span data-stu-id="26b95-131">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
