---
title: Metodo ICorDebugInternalFrame2::GetFrameAddress
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3062e636921ea959716a500dae689fbe07915006
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67759993"
---
# <a name="icordebuginternalframe2getframeaddress-method"></a><span data-ttu-id="ecad5-102">Metodo ICorDebugInternalFrame2::GetFrameAddress</span><span class="sxs-lookup"><span data-stu-id="ecad5-102">ICorDebugInternalFrame2::GetFrameAddress Method</span></span>
<span data-ttu-id="ecad5-103">Restituisce l'indirizzo dello stack del frame interno.</span><span class="sxs-lookup"><span data-stu-id="ecad5-103">Returns the stack address of the internal frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ecad5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ecad5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFrameAddress([out] CORDB_ADDRESS *pAddress);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ecad5-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ecad5-105">Parameters</span></span>  
 `pAddress`  
 <span data-ttu-id="ecad5-106">[out] Puntatore al `CORDB_ADDRESS` per il frame interno.</span><span class="sxs-lookup"><span data-stu-id="ecad5-106">[out] Pointer to the `CORDB_ADDRESS` for the internal frame.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ecad5-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="ecad5-107">Return Value</span></span>  
 <span data-ttu-id="ecad5-108">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="ecad5-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="ecad5-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ecad5-109">HRESULT</span></span>|<span data-ttu-id="ecad5-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ecad5-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ecad5-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="ecad5-111">S_OK</span></span>|<span data-ttu-id="ecad5-112">L'indirizzo del frame interno è stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="ecad5-112">The address of the internal frame was successfully returned.</span></span>|  
|<span data-ttu-id="ecad5-113">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ecad5-113">E_FAIL</span></span>|<span data-ttu-id="ecad5-114">L'indirizzo del frame interno non può essere restituito.</span><span class="sxs-lookup"><span data-stu-id="ecad5-114">The address of the internal frame could not be returned.</span></span>|  
|<span data-ttu-id="ecad5-115">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="ecad5-115">E_INVALIDARG</span></span>|<span data-ttu-id="ecad5-116">`pAddress` è `null`.</span><span class="sxs-lookup"><span data-stu-id="ecad5-116">`pAddress` is `null`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ecad5-117">Note</span><span class="sxs-lookup"><span data-stu-id="ecad5-117">Remarks</span></span>  
 <span data-ttu-id="ecad5-118">Il valore restituito in `pAddress` può essere utilizzato per determinare la posizione del frame interno rispetto a altro frame nello stack.</span><span class="sxs-lookup"><span data-stu-id="ecad5-118">The value returned in `pAddress` can be used to determine the location of the internal frame relative to other frames on the stack.</span></span> <span data-ttu-id="ecad5-119">Anche nei computer basati su IA-64, il frame interno si trova solo dello stack e nessun puntatore corrispondente a un archivio di backup.</span><span class="sxs-lookup"><span data-stu-id="ecad5-119">Even on IA-64-based computers, the internal frame lives on the stack only, and there is no corresponding pointer to a backing store.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ecad5-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ecad5-120">Requirements</span></span>  
 <span data-ttu-id="ecad5-121">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ecad5-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ecad5-122">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ecad5-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ecad5-123">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ecad5-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ecad5-124">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ecad5-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ecad5-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ecad5-125">See also</span></span>

- [<span data-ttu-id="ecad5-126">Interfaccia ICorDebugInternalFrame2</span><span class="sxs-lookup"><span data-stu-id="ecad5-126">ICorDebugInternalFrame2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md)
- [<span data-ttu-id="ecad5-127">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="ecad5-127">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="ecad5-128">Debug</span><span class="sxs-lookup"><span data-stu-id="ecad5-128">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
