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
ms.openlocfilehash: 5dd93dcc29ace6573e313f732c45af0dfbb900e1
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76782219"
---
# <a name="icordebuginternalframe2isclosertoleaf-method"></a><span data-ttu-id="71f77-102">Metodo ICorDebugInternalFrame2::IsCloserToLeaf</span><span class="sxs-lookup"><span data-stu-id="71f77-102">ICorDebugInternalFrame2::IsCloserToLeaf Method</span></span>
<span data-ttu-id="71f77-103">Controlla se il frame interno `this` è più vicino alla foglia rispetto all'oggetto ICorDebugFrame specificato.</span><span class="sxs-lookup"><span data-stu-id="71f77-103">Checks whether the `this` internal frame is closer to the leaf than the specified ICorDebugFrame object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71f77-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="71f77-104">Syntax</span></span>  
  
```cpp  
HRESULT IsCloserToLeaf([in] ICorDebugFrame * pFrameToCompare,  
                       [out] BOOL * pIsCloser);  
```  
  
## <a name="parameters"></a><span data-ttu-id="71f77-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="71f77-105">Parameters</span></span>  
 `pFrameToCompare`  
 <span data-ttu-id="71f77-106">in Puntatore all'oggetto di confronto `ICorDebugFrame`.</span><span class="sxs-lookup"><span data-stu-id="71f77-106">[in] A pointer to the comparison `ICorDebugFrame` object.</span></span>  
  
 `pIsCloser`  
 <span data-ttu-id="71f77-107">[out] `true` se il `this` frame interno è più vicino alla foglia rispetto al frame specificato da `pFrameToCompare`; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="71f77-107">[out] `true` if the `this` internal frame is closer to the leaf than the frame specified by `pFrameToCompare`; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="71f77-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="71f77-108">Return Value</span></span>  
 <span data-ttu-id="71f77-109">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="71f77-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="71f77-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="71f77-110">HRESULT</span></span>|<span data-ttu-id="71f77-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="71f77-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="71f77-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="71f77-112">S_OK</span></span>|<span data-ttu-id="71f77-113">Il confronto è stato eseguito correttamente.</span><span class="sxs-lookup"><span data-stu-id="71f77-113">The comparison was successfully performed.</span></span>|  
|<span data-ttu-id="71f77-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="71f77-114">E_FAIL</span></span>|<span data-ttu-id="71f77-115">Non è stato possibile eseguire il confronto.</span><span class="sxs-lookup"><span data-stu-id="71f77-115">The comparison could not be performed.</span></span>|  
|<span data-ttu-id="71f77-116">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="71f77-116">E_INVALIDARG</span></span>|<span data-ttu-id="71f77-117">`pFrameToCompare` o `pIsCloser` è null.</span><span class="sxs-lookup"><span data-stu-id="71f77-117">`pFrameToCompare` or `pIsCloser` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="71f77-118">Note</span><span class="sxs-lookup"><span data-stu-id="71f77-118">Remarks</span></span>  
 <span data-ttu-id="71f77-119">`IsCloserToLeaf` può essere usato per implementare un criterio per l'interfoliazione di frame interni con altri frame nello stack.</span><span class="sxs-lookup"><span data-stu-id="71f77-119">`IsCloserToLeaf` can be used to implement a policy for interleaving internal frames with other frames on the stack.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="71f77-120">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="71f77-120">Requirements</span></span>  
 <span data-ttu-id="71f77-121">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="71f77-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="71f77-122">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="71f77-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="71f77-123">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="71f77-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="71f77-124">**Versioni .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="71f77-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71f77-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="71f77-125">See also</span></span>

- [<span data-ttu-id="71f77-126">Interfaccia ICorDebugInternalFrame2</span><span class="sxs-lookup"><span data-stu-id="71f77-126">ICorDebugInternalFrame2 Interface</span></span>](icordebuginternalframe2-interface.md)
- [<span data-ttu-id="71f77-127">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="71f77-127">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="71f77-128">Debug</span><span class="sxs-lookup"><span data-stu-id="71f77-128">Debugging</span></span>](index.md)
