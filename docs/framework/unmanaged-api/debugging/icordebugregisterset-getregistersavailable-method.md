---
title: Metodo ICorDebugRegisterSet::GetRegistersAvailable
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
- ICorDebugRegisterSet.GetRegistersAvailable
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet::GetRegistersAvailable
helpviewer_keywords:
- ICorDebugRegisterSet::GetRegistersAvailable method [.NET Framework debugging]
- GetRegistersAvailable method, ICorDebugRegisterSet interface [.NET Framework debugging]
ms.assetid: 4ba08ffa-55a2-4662-9d6d-4738f1db60c9
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: fd7ff2b711d81ba1fe8fda9422587ec265dd88dd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugregistersetgetregistersavailable-method"></a><span data-ttu-id="8256a-102">Metodo ICorDebugRegisterSet::GetRegistersAvailable</span><span class="sxs-lookup"><span data-stu-id="8256a-102">ICorDebugRegisterSet::GetRegistersAvailable Method</span></span>
<span data-ttu-id="8256a-103">Ottiene una maschera di bit che indica quali registri in [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) sono attualmente disponibili.</span><span class="sxs-lookup"><span data-stu-id="8256a-103">Gets a bit mask indicating which registers in this [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) are currently available.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8256a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8256a-104">Syntax</span></span>  
  
```  
HRESULT GetRegistersAvailable (  
    [out] ULONG64   *pAvailable  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8256a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="8256a-105">Parameters</span></span>  
 `pAvailable`  
 <span data-ttu-id="8256a-106">[out] Maschera di bit che indica quali registri sono attualmente disponibili.</span><span class="sxs-lookup"><span data-stu-id="8256a-106">[out] A bit mask that indicates which registers are currently available.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8256a-107">Note</span><span class="sxs-lookup"><span data-stu-id="8256a-107">Remarks</span></span>  
 <span data-ttu-id="8256a-108">Un registro potrebbe non essere disponibile se non è possibile determinare il valore per una determinata situazione.</span><span class="sxs-lookup"><span data-stu-id="8256a-108">A register may be unavailable if its value cannot be determined for the given situation.</span></span>  
  
 <span data-ttu-id="8256a-109">La maschera restituita contiene un bit per ogni registro (1 << il Registro di indice).</span><span class="sxs-lookup"><span data-stu-id="8256a-109">The returned mask contains a bit for each register (1 << the register index).</span></span> <span data-ttu-id="8256a-110">Il valore di bit è 1 se il registro è disponibile, oppure 0 se non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="8256a-110">The bit value is 1 if the register is available, or 0 if it is not available.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8256a-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8256a-111">Requirements</span></span>  
 <span data-ttu-id="8256a-112">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8256a-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8256a-113">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="8256a-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8256a-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8256a-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8256a-115">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8256a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8256a-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8256a-116">See Also</span></span>  
 [<span data-ttu-id="8256a-117">Interfaccia ICorDebugRegisterSet</span><span class="sxs-lookup"><span data-stu-id="8256a-117">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)  
 [<span data-ttu-id="8256a-118">Interfaccia ICorDebugRegisterSet2</span><span class="sxs-lookup"><span data-stu-id="8256a-118">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
