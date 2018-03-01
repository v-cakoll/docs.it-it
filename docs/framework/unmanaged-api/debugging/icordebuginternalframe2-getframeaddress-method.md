---
title: Metodo ICorDebugInternalFrame2::GetFrameAddress
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
- ICorDebugInternalFrame2.GetFrameAddress Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugInternalFrame2::GetFrameAddress
helpviewer_keywords:
- GetFrameAddress method [.NET Framework debugging]
- ICorDebugInternalFrame2::GetFrameAddress method [.NET Framework debugging]
ms.assetid: 4ee8d058-ffc8-4967-9133-a5adfef4e518
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: f44f0707892197398e4638a5e6d037fba7c8fc71
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebuginternalframe2getframeaddress-method"></a><span data-ttu-id="219b0-102">Metodo ICorDebugInternalFrame2::GetFrameAddress</span><span class="sxs-lookup"><span data-stu-id="219b0-102">ICorDebugInternalFrame2::GetFrameAddress Method</span></span>
<span data-ttu-id="219b0-103">Restituisce l'indirizzo dello stack del frame interno.</span><span class="sxs-lookup"><span data-stu-id="219b0-103">Returns the stack address of the internal frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="219b0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="219b0-104">Syntax</span></span>  
  
```  
HRESULT GetFrameAddress([out] CORDB_ADDRESS *pAddress);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="219b0-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="219b0-105">Parameters</span></span>  
 `pAddress`  
 <span data-ttu-id="219b0-106">[out] Puntatore al `CORDB_ADDRESS` del frame interno.</span><span class="sxs-lookup"><span data-stu-id="219b0-106">[out] Pointer to the `CORDB_ADDRESS` for the internal frame.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="219b0-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="219b0-107">Return Value</span></span>  
 <span data-ttu-id="219b0-108">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="219b0-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="219b0-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="219b0-109">HRESULT</span></span>|<span data-ttu-id="219b0-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="219b0-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="219b0-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="219b0-111">S_OK</span></span>|<span data-ttu-id="219b0-112">L'indirizzo del frame interno è stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="219b0-112">The address of the internal frame was successfully returned.</span></span>|  
|<span data-ttu-id="219b0-113">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="219b0-113">E_FAIL</span></span>|<span data-ttu-id="219b0-114">Non è stato possibile restituire l'indirizzo del frame interno.</span><span class="sxs-lookup"><span data-stu-id="219b0-114">The address of the internal frame could not be returned.</span></span>|  
|<span data-ttu-id="219b0-115">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="219b0-115">E_INVALIDARG</span></span>|<span data-ttu-id="219b0-116">`pAddress` è `null`.</span><span class="sxs-lookup"><span data-stu-id="219b0-116">`pAddress` is `null`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="219b0-117">Note</span><span class="sxs-lookup"><span data-stu-id="219b0-117">Remarks</span></span>  
 <span data-ttu-id="219b0-118">Il valore restituito in `pAddress` può essere utilizzato per determinare la posizione del frame interno relativa ad altri frame nello stack.</span><span class="sxs-lookup"><span data-stu-id="219b0-118">The value returned in `pAddress` can be used to determine the location of the internal frame relative to other frames on the stack.</span></span> <span data-ttu-id="219b0-119">Anche nei computer basati su IA-64, frame interni risiede solo lo stack e nessun puntatore a un archivio di backup corrispondente.</span><span class="sxs-lookup"><span data-stu-id="219b0-119">Even on IA-64-based computers, the internal frame lives on the stack only, and there is no corresponding pointer to a backing store.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="219b0-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="219b0-120">Requirements</span></span>  
 <span data-ttu-id="219b0-121">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="219b0-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="219b0-122">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="219b0-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="219b0-123">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="219b0-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="219b0-124">**Versioni di .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="219b0-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="219b0-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="219b0-125">See Also</span></span>  
 [<span data-ttu-id="219b0-126">Interfaccia ICorDebugInternalFrame2</span><span class="sxs-lookup"><span data-stu-id="219b0-126">ICorDebugInternalFrame2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md)  
 [<span data-ttu-id="219b0-127">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="219b0-127">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="219b0-128">Debug</span><span class="sxs-lookup"><span data-stu-id="219b0-128">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
