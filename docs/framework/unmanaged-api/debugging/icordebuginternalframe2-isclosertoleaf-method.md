---
title: Metodo ICorDebugInternalFrame2::IsCloserToLeaf
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugInternalFrame2.IsCloserToLeaf Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugInternalFrame2::IsCloserToLeaf
helpviewer_keywords:
- ICorDebugInternalFrame2::IsCloserToLeaf method [.NET Framework debugging]
- IsCloserToLeaf method [.NET Framework debugging]
ms.assetid: c1d3d1eb-8370-4f25-8297-3bd262b4740a
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 7b6b769c25e0cd706eb57965b73d0fcfdcf9b9ea
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebuginternalframe2isclosertoleaf-method"></a><span data-ttu-id="1036a-102">Metodo ICorDebugInternalFrame2::IsCloserToLeaf</span><span class="sxs-lookup"><span data-stu-id="1036a-102">ICorDebugInternalFrame2::IsCloserToLeaf Method</span></span>
<span data-ttu-id="1036a-103">Controlla se il `this` frame interno è più vicino alla foglia rispetto all'oggetto ICorDebugFrame specificato.</span><span class="sxs-lookup"><span data-stu-id="1036a-103">Checks whether the `this` internal frame is closer to the leaf than the specified ICorDebugFrame object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1036a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1036a-104">Syntax</span></span>  
  
```  
HRESULT IsCloserToLeaf([in] ICorDebugFrame * pFrameToCompare,  
                       [out] BOOL * pIsCloser);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1036a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="1036a-105">Parameters</span></span>  
 `pFrameToCompare`  
 <span data-ttu-id="1036a-106">[in] Un puntatore al confronto `ICorDebugFrame` oggetto.</span><span class="sxs-lookup"><span data-stu-id="1036a-106">[in] A pointer to the comparison `ICorDebugFrame` object.</span></span>  
  
 `pIsCloser`  
 <span data-ttu-id="1036a-107">[out] `true` se il `this` frame interno è più vicino alla foglia rispetto al frame specificato da `pFrameToCompare`; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="1036a-107">[out] `true` if the `this` internal frame is closer to the leaf than the frame specified by `pFrameToCompare`; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1036a-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="1036a-108">Return Value</span></span>  
 <span data-ttu-id="1036a-109">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="1036a-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="1036a-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1036a-110">HRESULT</span></span>|<span data-ttu-id="1036a-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1036a-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1036a-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="1036a-112">S_OK</span></span>|<span data-ttu-id="1036a-113">Il confronto è stato eseguito correttamente.</span><span class="sxs-lookup"><span data-stu-id="1036a-113">The comparison was successfully performed.</span></span>|  
|<span data-ttu-id="1036a-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="1036a-114">E_FAIL</span></span>|<span data-ttu-id="1036a-115">Non è stato possibile eseguire il confronto.</span><span class="sxs-lookup"><span data-stu-id="1036a-115">The comparison could not be performed.</span></span>|  
|<span data-ttu-id="1036a-116">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="1036a-116">E_INVALIDARG</span></span>|<span data-ttu-id="1036a-117">`pFrameToCompare` o `pIsCloser` è null.</span><span class="sxs-lookup"><span data-stu-id="1036a-117">`pFrameToCompare` or `pIsCloser` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1036a-118">Note</span><span class="sxs-lookup"><span data-stu-id="1036a-118">Remarks</span></span>  
 <span data-ttu-id="1036a-119">`IsCloserToLeaf`può essere utilizzato per implementare un criterio per interfoliazione frame interni con altri frame nello stack.</span><span class="sxs-lookup"><span data-stu-id="1036a-119">`IsCloserToLeaf` can be used to implement a policy for interleaving internal frames with other frames on the stack.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1036a-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1036a-120">Requirements</span></span>  
 <span data-ttu-id="1036a-121">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1036a-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1036a-122">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="1036a-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1036a-123">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1036a-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1036a-124">**Versioni di .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1036a-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1036a-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1036a-125">See Also</span></span>  
 [<span data-ttu-id="1036a-126">Interfaccia ICorDebugInternalFrame2</span><span class="sxs-lookup"><span data-stu-id="1036a-126">ICorDebugInternalFrame2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md)  
 [<span data-ttu-id="1036a-127">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="1036a-127">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="1036a-128">Debug</span><span class="sxs-lookup"><span data-stu-id="1036a-128">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
