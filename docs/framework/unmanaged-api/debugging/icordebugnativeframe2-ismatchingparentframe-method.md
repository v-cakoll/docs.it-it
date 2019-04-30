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
ms.openlocfilehash: 0a553f2cbac6110e82803e6d0dd872cfaa15d773
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61987831"
---
# <a name="icordebugnativeframe2ismatchingparentframe-method"></a><span data-ttu-id="9e57a-102">Metodo ICorDebugNativeFrame2::IsMatchingParentFrame</span><span class="sxs-lookup"><span data-stu-id="9e57a-102">ICorDebugNativeFrame2::IsMatchingParentFrame Method</span></span>
<span data-ttu-id="9e57a-103">Determina se l'intervallo specificato è l'elemento padre del frame corrente.</span><span class="sxs-lookup"><span data-stu-id="9e57a-103">Determines whether the specified frame is the parent of the current frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e57a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9e57a-104">Syntax</span></span>  
  
```  
HRESULT IsMatchingParentFrame([in] ICorDebugNativeFrame2  
                                      *pPotentialParentFrame,  
                              [out] BOOL *pIsParent);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9e57a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="9e57a-105">Parameters</span></span>  
 `pPotentialParentFrame`  
 <span data-ttu-id="9e57a-106">[in] Un puntatore all'oggetto frame che si vuole valutare lo stato di padre.</span><span class="sxs-lookup"><span data-stu-id="9e57a-106">[in] A pointer to the frame object that you want to evaluate for parent status.</span></span>  
  
 `pIsParent`  
 <span data-ttu-id="9e57a-107">[out] `true` se `pPotentialParentFrame` è padre del frame corrente; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="9e57a-107">[out] `true` if `pPotentialParentFrame` is the current frame’s parent; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9e57a-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="9e57a-108">Return Value</span></span>  
 <span data-ttu-id="9e57a-109">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="9e57a-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="9e57a-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9e57a-110">HRESULT</span></span>|<span data-ttu-id="9e57a-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9e57a-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9e57a-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="9e57a-112">S_OK</span></span>|<span data-ttu-id="9e57a-113">Lo stato dell'elemento padre è stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="9e57a-113">The parent status was successfully returned.</span></span>|  
|<span data-ttu-id="9e57a-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9e57a-114">E_FAIL</span></span>|<span data-ttu-id="9e57a-115">Lo stato dell'elemento padre non può essere restituito.</span><span class="sxs-lookup"><span data-stu-id="9e57a-115">The parent status could not be returned.</span></span>|  
|<span data-ttu-id="9e57a-116">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="9e57a-116">E_INVALIDARG</span></span>|<span data-ttu-id="9e57a-117">`pPotentialParentFrame` o `pIsParent` è null.</span><span class="sxs-lookup"><span data-stu-id="9e57a-117">`pPotentialParentFrame` or `pIsParent` is null.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="9e57a-118">Eccezioni</span><span class="sxs-lookup"><span data-stu-id="9e57a-118">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9e57a-119">Note</span><span class="sxs-lookup"><span data-stu-id="9e57a-119">Remarks</span></span>  
 <span data-ttu-id="9e57a-120">`IsMatchingParentFrame` Restituisce `true` se l'oggetto cornice passa al metodo è l'elemento padre dell'oggetto frame sul quale è stato chiamato il metodo.</span><span class="sxs-lookup"><span data-stu-id="9e57a-120">`IsMatchingParentFrame` returns `true` if the frame object you pass to the method is the parent of the frame object on which the method was called.</span></span> <span data-ttu-id="9e57a-121">Se si chiama il metodo su un frame che non è un figlio del frame specificato, viene restituito un errore.</span><span class="sxs-lookup"><span data-stu-id="9e57a-121">If you call the method on a frame that is not a child of the specified frame, it returns an error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9e57a-122">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9e57a-122">Requirements</span></span>  
 <span data-ttu-id="9e57a-123">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9e57a-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9e57a-124">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9e57a-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9e57a-125">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9e57a-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9e57a-126">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9e57a-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e57a-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9e57a-127">See also</span></span>

- [<span data-ttu-id="9e57a-128">Interfaccia ICorDebugNativeFrame2</span><span class="sxs-lookup"><span data-stu-id="9e57a-128">ICorDebugNativeFrame2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-interface.md)
- [<span data-ttu-id="9e57a-129">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="9e57a-129">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="9e57a-130">Debug</span><span class="sxs-lookup"><span data-stu-id="9e57a-130">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
