---
title: Metodo ICorDebugNativeFrame2::IsMatchingParentFrame
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame2.IsMatchingParentFrame Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame2::IsMatchingParentFrame
helpviewer_keywords:
- IsMatchingParentFrame method [.NET Framework debugging]
- ICorDebugNativeFrame2::IsMatchingParentFrame method [.NET Framework debugging]
ms.assetid: d2ca20db-df22-4528-a0dd-a09ea62c8998
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 56d2c28529d3f3ee87fe3fdedd91634133ebf864
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57492205"
---
# <a name="icordebugnativeframe2ismatchingparentframe-method"></a><span data-ttu-id="eb65f-102">Metodo ICorDebugNativeFrame2::IsMatchingParentFrame</span><span class="sxs-lookup"><span data-stu-id="eb65f-102">ICorDebugNativeFrame2::IsMatchingParentFrame Method</span></span>
<span data-ttu-id="eb65f-103">Determina se l'intervallo specificato è l'elemento padre del frame corrente.</span><span class="sxs-lookup"><span data-stu-id="eb65f-103">Determines whether the specified frame is the parent of the current frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb65f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="eb65f-104">Syntax</span></span>  
  
```  
HRESULT IsMatchingParentFrame([in] ICorDebugNativeFrame2  
                                      *pPotentialParentFrame,  
                              [out] BOOL *pIsParent);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eb65f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="eb65f-105">Parameters</span></span>  
 `pPotentialParentFrame`  
 <span data-ttu-id="eb65f-106">[in] Un puntatore all'oggetto frame che si vuole valutare lo stato di padre.</span><span class="sxs-lookup"><span data-stu-id="eb65f-106">[in] A pointer to the frame object that you want to evaluate for parent status.</span></span>  
  
 `pIsParent`  
 <span data-ttu-id="eb65f-107">[out] `true` se `pPotentialParentFrame` è padre del frame corrente; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="eb65f-107">[out] `true` if `pPotentialParentFrame` is the current frame’s parent; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="eb65f-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="eb65f-108">Return Value</span></span>  
 <span data-ttu-id="eb65f-109">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="eb65f-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="eb65f-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="eb65f-110">HRESULT</span></span>|<span data-ttu-id="eb65f-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="eb65f-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="eb65f-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="eb65f-112">S_OK</span></span>|<span data-ttu-id="eb65f-113">Lo stato dell'elemento padre è stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="eb65f-113">The parent status was successfully returned.</span></span>|  
|<span data-ttu-id="eb65f-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="eb65f-114">E_FAIL</span></span>|<span data-ttu-id="eb65f-115">Lo stato dell'elemento padre non può essere restituito.</span><span class="sxs-lookup"><span data-stu-id="eb65f-115">The parent status could not be returned.</span></span>|  
|<span data-ttu-id="eb65f-116">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="eb65f-116">E_INVALIDARG</span></span>|<span data-ttu-id="eb65f-117">`pPotentialParentFrame` o `pIsParent` è null.</span><span class="sxs-lookup"><span data-stu-id="eb65f-117">`pPotentialParentFrame` or `pIsParent` is null.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="eb65f-118">Eccezioni</span><span class="sxs-lookup"><span data-stu-id="eb65f-118">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="eb65f-119">Note</span><span class="sxs-lookup"><span data-stu-id="eb65f-119">Remarks</span></span>  
 <span data-ttu-id="eb65f-120">`IsMatchingParentFrame` Restituisce `true` se l'oggetto cornice passa al metodo è l'elemento padre dell'oggetto frame sul quale è stato chiamato il metodo.</span><span class="sxs-lookup"><span data-stu-id="eb65f-120">`IsMatchingParentFrame` returns `true` if the frame object you pass to the method is the parent of the frame object on which the method was called.</span></span> <span data-ttu-id="eb65f-121">Se si chiama il metodo su un frame che non è un figlio del frame specificato, viene restituito un errore.</span><span class="sxs-lookup"><span data-stu-id="eb65f-121">If you call the method on a frame that is not a child of the specified frame, it returns an error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eb65f-122">Requisiti</span><span class="sxs-lookup"><span data-stu-id="eb65f-122">Requirements</span></span>  
 <span data-ttu-id="eb65f-123">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eb65f-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eb65f-124">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="eb65f-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="eb65f-125">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="eb65f-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="eb65f-126">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eb65f-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb65f-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="eb65f-127">See also</span></span>
- [<span data-ttu-id="eb65f-128">Interfaccia ICorDebugNativeFrame2</span><span class="sxs-lookup"><span data-stu-id="eb65f-128">ICorDebugNativeFrame2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-interface.md)
- [<span data-ttu-id="eb65f-129">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="eb65f-129">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="eb65f-130">Debug</span><span class="sxs-lookup"><span data-stu-id="eb65f-130">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
