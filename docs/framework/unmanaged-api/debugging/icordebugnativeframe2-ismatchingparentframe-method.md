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
ms.openlocfilehash: e261f4cb43843ec61ec6cbd1609e6967a4a38a82
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugnativeframe2ismatchingparentframe-method"></a><span data-ttu-id="640b9-102">Metodo ICorDebugNativeFrame2::IsMatchingParentFrame</span><span class="sxs-lookup"><span data-stu-id="640b9-102">ICorDebugNativeFrame2::IsMatchingParentFrame Method</span></span>
<span data-ttu-id="640b9-103">Determina se l'intervallo specificato è l'elemento padre del frame corrente.</span><span class="sxs-lookup"><span data-stu-id="640b9-103">Determines whether the specified frame is the parent of the current frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="640b9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="640b9-104">Syntax</span></span>  
  
```  
HRESULT IsMatchingParentFrame([in] ICorDebugNativeFrame2  
                                      *pPotentialParentFrame,  
                              [out] BOOL *pIsParent);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="640b9-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="640b9-105">Parameters</span></span>  
 `pPotentialParentFrame`  
 <span data-ttu-id="640b9-106">[in] Un puntatore all'oggetto frame che si desidera valutare lo stato di padre.</span><span class="sxs-lookup"><span data-stu-id="640b9-106">[in] A pointer to the frame object that you want to evaluate for parent status.</span></span>  
  
 `pIsParent`  
 <span data-ttu-id="640b9-107">[out] `true` se `pPotentialParentFrame` padre del frame corrente; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="640b9-107">[out] `true` if `pPotentialParentFrame` is the current frame’s parent; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="640b9-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="640b9-108">Return Value</span></span>  
 <span data-ttu-id="640b9-109">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="640b9-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="640b9-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="640b9-110">HRESULT</span></span>|<span data-ttu-id="640b9-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="640b9-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="640b9-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="640b9-112">S_OK</span></span>|<span data-ttu-id="640b9-113">Lo stato dell'elemento padre è stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="640b9-113">The parent status was successfully returned.</span></span>|  
|<span data-ttu-id="640b9-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="640b9-114">E_FAIL</span></span>|<span data-ttu-id="640b9-115">Non è stato possibile restituire lo stato dell'elemento padre.</span><span class="sxs-lookup"><span data-stu-id="640b9-115">The parent status could not be returned.</span></span>|  
|<span data-ttu-id="640b9-116">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="640b9-116">E_INVALIDARG</span></span>|<span data-ttu-id="640b9-117">`pPotentialParentFrame` o `pIsParent` è null.</span><span class="sxs-lookup"><span data-stu-id="640b9-117">`pPotentialParentFrame` or `pIsParent` is null.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="640b9-118">Eccezioni</span><span class="sxs-lookup"><span data-stu-id="640b9-118">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="640b9-119">Note</span><span class="sxs-lookup"><span data-stu-id="640b9-119">Remarks</span></span>  
 <span data-ttu-id="640b9-120">`IsMatchingParentFrame`Restituisce `true` se l'oggetto frame da passare al metodo è l'elemento padre dell'oggetto frame in cui è stato chiamato il metodo.</span><span class="sxs-lookup"><span data-stu-id="640b9-120">`IsMatchingParentFrame` returns `true` if the frame object you pass to the method is the parent of the frame object on which the method was called.</span></span> <span data-ttu-id="640b9-121">Se si chiama il metodo su un frame che non è un figlio del frame specificato, viene restituito un errore.</span><span class="sxs-lookup"><span data-stu-id="640b9-121">If you call the method on a frame that is not a child of the specified frame, it returns an error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="640b9-122">Requisiti</span><span class="sxs-lookup"><span data-stu-id="640b9-122">Requirements</span></span>  
 <span data-ttu-id="640b9-123">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="640b9-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="640b9-124">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="640b9-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="640b9-125">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="640b9-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="640b9-126">**Versioni di .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="640b9-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="640b9-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="640b9-127">See Also</span></span>  
 [<span data-ttu-id="640b9-128">ICorDebugNativeFrame2 (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="640b9-128">ICorDebugNativeFrame2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-interface.md)  
 [<span data-ttu-id="640b9-129">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="640b9-129">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="640b9-130">Debug</span><span class="sxs-lookup"><span data-stu-id="640b9-130">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
