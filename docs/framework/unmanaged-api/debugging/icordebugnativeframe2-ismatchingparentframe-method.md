---
title: Metodo ICorDebugNativeFrame2::IsMatchingParentFrame
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugNativeFrame2.IsMatchingParentFrame Method
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugNativeFrame2::IsMatchingParentFrame
helpviewer_keywords:
- IsMatchingParentFrame method [.NET Framework debugging]
- ICorDebugNativeFrame2::IsMatchingParentFrame method [.NET Framework debugging]
ms.assetid: d2ca20db-df22-4528-a0dd-a09ea62c8998
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: fc2d8eacb05e861290ad19a34c261943dc2959a1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugnativeframe2ismatchingparentframe-method"></a><span data-ttu-id="0bb7d-102">Metodo ICorDebugNativeFrame2::IsMatchingParentFrame</span><span class="sxs-lookup"><span data-stu-id="0bb7d-102">ICorDebugNativeFrame2::IsMatchingParentFrame Method</span></span>
<span data-ttu-id="0bb7d-103">Determina se l'intervallo specificato è l'elemento padre del frame corrente.</span><span class="sxs-lookup"><span data-stu-id="0bb7d-103">Determines whether the specified frame is the parent of the current frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0bb7d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0bb7d-104">Syntax</span></span>  
  
```  
HRESULT IsMatchingParentFrame([in] ICorDebugNativeFrame2  
                                      *pPotentialParentFrame,  
                              [out] BOOL *pIsParent);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0bb7d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="0bb7d-105">Parameters</span></span>  
 `pPotentialParentFrame`  
 <span data-ttu-id="0bb7d-106">[in] Un puntatore all'oggetto frame che si desidera valutare lo stato di padre.</span><span class="sxs-lookup"><span data-stu-id="0bb7d-106">[in] A pointer to the frame object that you want to evaluate for parent status.</span></span>  
  
 `pIsParent`  
 <span data-ttu-id="0bb7d-107">[out] `true` se `pPotentialParentFrame` padre del frame corrente; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="0bb7d-107">[out] `true` if `pPotentialParentFrame` is the current frame’s parent; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0bb7d-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="0bb7d-108">Return Value</span></span>  
 <span data-ttu-id="0bb7d-109">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="0bb7d-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="0bb7d-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0bb7d-110">HRESULT</span></span>|<span data-ttu-id="0bb7d-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0bb7d-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0bb7d-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="0bb7d-112">S_OK</span></span>|<span data-ttu-id="0bb7d-113">Lo stato dell'elemento padre è stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="0bb7d-113">The parent status was successfully returned.</span></span>|  
|<span data-ttu-id="0bb7d-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0bb7d-114">E_FAIL</span></span>|<span data-ttu-id="0bb7d-115">Non è stato possibile restituire lo stato dell'elemento padre.</span><span class="sxs-lookup"><span data-stu-id="0bb7d-115">The parent status could not be returned.</span></span>|  
|<span data-ttu-id="0bb7d-116">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="0bb7d-116">E_INVALIDARG</span></span>|<span data-ttu-id="0bb7d-117">`pPotentialParentFrame` o `pIsParent` è null.</span><span class="sxs-lookup"><span data-stu-id="0bb7d-117">`pPotentialParentFrame` or `pIsParent` is null.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="0bb7d-118">Eccezioni</span><span class="sxs-lookup"><span data-stu-id="0bb7d-118">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0bb7d-119">Note</span><span class="sxs-lookup"><span data-stu-id="0bb7d-119">Remarks</span></span>  
 <span data-ttu-id="0bb7d-120">`IsMatchingParentFrame`Restituisce `true` se l'oggetto frame da passare al metodo è l'elemento padre dell'oggetto frame in cui è stato chiamato il metodo.</span><span class="sxs-lookup"><span data-stu-id="0bb7d-120">`IsMatchingParentFrame` returns `true` if the frame object you pass to the method is the parent of the frame object on which the method was called.</span></span> <span data-ttu-id="0bb7d-121">Se si chiama il metodo su un frame che non è un figlio del frame specificato, viene restituito un errore.</span><span class="sxs-lookup"><span data-stu-id="0bb7d-121">If you call the method on a frame that is not a child of the specified frame, it returns an error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0bb7d-122">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0bb7d-122">Requirements</span></span>  
 <span data-ttu-id="0bb7d-123">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0bb7d-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0bb7d-124">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="0bb7d-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0bb7d-125">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0bb7d-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0bb7d-126">**Versioni di .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0bb7d-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0bb7d-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0bb7d-127">See Also</span></span>  
 [<span data-ttu-id="0bb7d-128">Interfaccia ICorDebugNativeFrame2</span><span class="sxs-lookup"><span data-stu-id="0bb7d-128">ICorDebugNativeFrame2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-interface.md)  
 [<span data-ttu-id="0bb7d-129">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="0bb7d-129">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="0bb7d-130">Debug</span><span class="sxs-lookup"><span data-stu-id="0bb7d-130">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
