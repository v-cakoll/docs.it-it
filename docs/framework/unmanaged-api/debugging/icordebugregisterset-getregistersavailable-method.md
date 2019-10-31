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
ms.openlocfilehash: 9d8bd6ab13fa408fd7390aaeb76baee274742f48
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137694"
---
# <a name="icordebugregistersetgetregistersavailable-method"></a><span data-ttu-id="868eb-102">Metodo ICorDebugRegisterSet::GetRegistersAvailable</span><span class="sxs-lookup"><span data-stu-id="868eb-102">ICorDebugRegisterSet::GetRegistersAvailable Method</span></span>
<span data-ttu-id="868eb-103">Ottiene una maschera di bit che indica i registri attualmente disponibili in questo [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="868eb-103">Gets a bit mask indicating which registers in this [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) are currently available.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="868eb-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="868eb-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRegistersAvailable (  
    [out] ULONG64   *pAvailable  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="868eb-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="868eb-105">Parameters</span></span>  
 `pAvailable`  
 <span data-ttu-id="868eb-106">out Maschera di bit che indica i registri attualmente disponibili.</span><span class="sxs-lookup"><span data-stu-id="868eb-106">[out] A bit mask that indicates which registers are currently available.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="868eb-107">Note</span><span class="sxs-lookup"><span data-stu-id="868eb-107">Remarks</span></span>  
 <span data-ttu-id="868eb-108">Un registro potrebbe non essere disponibile se non è possibile determinare il relativo valore per la situazione specificata.</span><span class="sxs-lookup"><span data-stu-id="868eb-108">A register may be unavailable if its value cannot be determined for the given situation.</span></span>  
  
 <span data-ttu-id="868eb-109">La maschera restituita contiene un bit per ogni registro (1 < < l'indice di registro).</span><span class="sxs-lookup"><span data-stu-id="868eb-109">The returned mask contains a bit for each register (1 << the register index).</span></span> <span data-ttu-id="868eb-110">Il valore di bit è 1 se il registro è disponibile oppure 0 se non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="868eb-110">The bit value is 1 if the register is available, or 0 if it is not available.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="868eb-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="868eb-111">Requirements</span></span>  
 <span data-ttu-id="868eb-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="868eb-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="868eb-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="868eb-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="868eb-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="868eb-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="868eb-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="868eb-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="868eb-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="868eb-116">See also</span></span>

- [<span data-ttu-id="868eb-117">Interfaccia ICorDebugRegisterSet</span><span class="sxs-lookup"><span data-stu-id="868eb-117">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)
- [<span data-ttu-id="868eb-118">Interfaccia ICorDebugRegisterSet2</span><span class="sxs-lookup"><span data-stu-id="868eb-118">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
