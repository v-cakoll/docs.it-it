---
title: Metodo ICorDebugInternalFrame2::IsCloserToLeaf
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 30a9d26283d4f544bdd865e40cfc1c1c625ae462
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59120900"
---
# <a name="icordebuginternalframe2isclosertoleaf-method"></a><span data-ttu-id="e5369-102">Metodo ICorDebugInternalFrame2::IsCloserToLeaf</span><span class="sxs-lookup"><span data-stu-id="e5369-102">ICorDebugInternalFrame2::IsCloserToLeaf Method</span></span>
<span data-ttu-id="e5369-103">Controlla se il `this` frame interno è più simile alla foglia a oggetto ICorDebugFrame specificato.</span><span class="sxs-lookup"><span data-stu-id="e5369-103">Checks whether the `this` internal frame is closer to the leaf than the specified ICorDebugFrame object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5369-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e5369-104">Syntax</span></span>  
  
```  
HRESULT IsCloserToLeaf([in] ICorDebugFrame * pFrameToCompare,  
                       [out] BOOL * pIsCloser);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e5369-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e5369-105">Parameters</span></span>  
 `pFrameToCompare`  
 <span data-ttu-id="e5369-106">[in] Un puntatore al confronto `ICorDebugFrame` oggetto.</span><span class="sxs-lookup"><span data-stu-id="e5369-106">[in] A pointer to the comparison `ICorDebugFrame` object.</span></span>  
  
 `pIsCloser`  
 <span data-ttu-id="e5369-107">[out] `true` se il `this` frame interno è più simile alla foglia a frame specificato da `pFrameToCompare`; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="e5369-107">[out] `true` if the `this` internal frame is closer to the leaf than the frame specified by `pFrameToCompare`; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e5369-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="e5369-108">Return Value</span></span>  
 <span data-ttu-id="e5369-109">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="e5369-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="e5369-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e5369-110">HRESULT</span></span>|<span data-ttu-id="e5369-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e5369-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e5369-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="e5369-112">S_OK</span></span>|<span data-ttu-id="e5369-113">Il confronto è stato eseguito correttamente.</span><span class="sxs-lookup"><span data-stu-id="e5369-113">The comparison was successfully performed.</span></span>|  
|<span data-ttu-id="e5369-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e5369-114">E_FAIL</span></span>|<span data-ttu-id="e5369-115">Non è stato possibile eseguire il confronto.</span><span class="sxs-lookup"><span data-stu-id="e5369-115">The comparison could not be performed.</span></span>|  
|<span data-ttu-id="e5369-116">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="e5369-116">E_INVALIDARG</span></span>|`pFrameToCompare` <span data-ttu-id="e5369-117">o `pIsCloser` è null.</span><span class="sxs-lookup"><span data-stu-id="e5369-117">or `pIsCloser` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e5369-118">Note</span><span class="sxs-lookup"><span data-stu-id="e5369-118">Remarks</span></span>  
 `IsCloserToLeaf` <span data-ttu-id="e5369-119">può essere utilizzato per implementare un criterio per interfoliazione frame interni con altri frame nello stack.</span><span class="sxs-lookup"><span data-stu-id="e5369-119">can be used to implement a policy for interleaving internal frames with other frames on the stack.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5369-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e5369-120">Requirements</span></span>  
 <span data-ttu-id="e5369-121">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e5369-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e5369-122">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e5369-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e5369-123">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e5369-123">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="e5369-124">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="e5369-124">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e5369-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e5369-125">See also</span></span>

- [<span data-ttu-id="e5369-126">Interfaccia ICorDebugInternalFrame2</span><span class="sxs-lookup"><span data-stu-id="e5369-126">ICorDebugInternalFrame2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md)
- [<span data-ttu-id="e5369-127">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="e5369-127">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="e5369-128">Debug</span><span class="sxs-lookup"><span data-stu-id="e5369-128">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
