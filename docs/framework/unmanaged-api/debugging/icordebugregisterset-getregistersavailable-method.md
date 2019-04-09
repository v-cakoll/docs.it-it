---
title: Metodo ICorDebugRegisterSet::GetRegistersAvailable
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f341098268f735a576bdbc5f0cea52f1a7e14f90
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59156039"
---
# <a name="icordebugregistersetgetregistersavailable-method"></a><span data-ttu-id="0e0a8-102">Metodo ICorDebugRegisterSet::GetRegistersAvailable</span><span class="sxs-lookup"><span data-stu-id="0e0a8-102">ICorDebugRegisterSet::GetRegistersAvailable Method</span></span>
<span data-ttu-id="0e0a8-103">Ottiene una maschera di bit che indica quali registri in questo [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) sono attualmente disponibili.</span><span class="sxs-lookup"><span data-stu-id="0e0a8-103">Gets a bit mask indicating which registers in this [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) are currently available.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e0a8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0e0a8-104">Syntax</span></span>  
  
```  
HRESULT GetRegistersAvailable (  
    [out] ULONG64   *pAvailable  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0e0a8-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="0e0a8-105">Parameters</span></span>  
 `pAvailable`  
 <span data-ttu-id="0e0a8-106">[out] Maschera di bit che indica quali registri sono attualmente disponibili.</span><span class="sxs-lookup"><span data-stu-id="0e0a8-106">[out] A bit mask that indicates which registers are currently available.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0e0a8-107">Note</span><span class="sxs-lookup"><span data-stu-id="0e0a8-107">Remarks</span></span>  
 <span data-ttu-id="0e0a8-108">Un registro potrebbe non essere disponibile se non è possibile determinare il valore per una determinata situazione.</span><span class="sxs-lookup"><span data-stu-id="0e0a8-108">A register may be unavailable if its value cannot be determined for the given situation.</span></span>  
  
 <span data-ttu-id="0e0a8-109">La maschera restituita contiene un bit per ogni registrazione (1 << indice register).</span><span class="sxs-lookup"><span data-stu-id="0e0a8-109">The returned mask contains a bit for each register (1 << the register index).</span></span> <span data-ttu-id="0e0a8-110">Il valore di bit è 1 se la registrazione è disponibile, oppure 0 se non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="0e0a8-110">The bit value is 1 if the register is available, or 0 if it is not available.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0e0a8-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0e0a8-111">Requirements</span></span>  
 <span data-ttu-id="0e0a8-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0e0a8-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0e0a8-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0e0a8-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0e0a8-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0e0a8-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="0e0a8-115">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="0e0a8-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="0e0a8-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0e0a8-116">See also</span></span>

- [<span data-ttu-id="0e0a8-117">Interfaccia ICorDebugRegisterSet</span><span class="sxs-lookup"><span data-stu-id="0e0a8-117">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)
- [<span data-ttu-id="0e0a8-118">Interfaccia ICorDebugRegisterSet2</span><span class="sxs-lookup"><span data-stu-id="0e0a8-118">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
