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
ms.openlocfilehash: b137b956e06a2b2954918e4024860f9b234e7583
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792099"
---
# <a name="icordebugregistersetgetregistersavailable-method"></a><span data-ttu-id="f3d16-102">Metodo ICorDebugRegisterSet::GetRegistersAvailable</span><span class="sxs-lookup"><span data-stu-id="f3d16-102">ICorDebugRegisterSet::GetRegistersAvailable Method</span></span>
<span data-ttu-id="f3d16-103">Ottiene una maschera di bit che indica i registri attualmente disponibili in questo [ICorDebugRegisterSet](icordebugregisterset-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="f3d16-103">Gets a bit mask indicating which registers in this [ICorDebugRegisterSet](icordebugregisterset-interface.md) are currently available.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3d16-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f3d16-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRegistersAvailable (  
    [out] ULONG64   *pAvailable  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f3d16-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f3d16-105">Parameters</span></span>  
 `pAvailable`  
 <span data-ttu-id="f3d16-106">out Maschera di bit che indica i registri attualmente disponibili.</span><span class="sxs-lookup"><span data-stu-id="f3d16-106">[out] A bit mask that indicates which registers are currently available.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f3d16-107">Note</span><span class="sxs-lookup"><span data-stu-id="f3d16-107">Remarks</span></span>  
 <span data-ttu-id="f3d16-108">Un registro potrebbe non essere disponibile se non è possibile determinare il relativo valore per la situazione specificata.</span><span class="sxs-lookup"><span data-stu-id="f3d16-108">A register may be unavailable if its value cannot be determined for the given situation.</span></span>  
  
 <span data-ttu-id="f3d16-109">La maschera restituita contiene un bit per ogni registro (1 < < l'indice di registro).</span><span class="sxs-lookup"><span data-stu-id="f3d16-109">The returned mask contains a bit for each register (1 << the register index).</span></span> <span data-ttu-id="f3d16-110">Il valore di bit è 1 se il registro è disponibile oppure 0 se non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="f3d16-110">The bit value is 1 if the register is available, or 0 if it is not available.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f3d16-111">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="f3d16-111">Requirements</span></span>  
 <span data-ttu-id="f3d16-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f3d16-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f3d16-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f3d16-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f3d16-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f3d16-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f3d16-115">**Versioni .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f3d16-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3d16-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f3d16-116">See also</span></span>

- [<span data-ttu-id="f3d16-117">Interfaccia ICorDebugRegisterSet</span><span class="sxs-lookup"><span data-stu-id="f3d16-117">ICorDebugRegisterSet Interface</span></span>](icordebugregisterset-interface.md)
- [<span data-ttu-id="f3d16-118">Interfaccia ICorDebugRegisterSet2</span><span class="sxs-lookup"><span data-stu-id="f3d16-118">ICorDebugRegisterSet2 Interface</span></span>](icordebugregisterset2-interface.md)
