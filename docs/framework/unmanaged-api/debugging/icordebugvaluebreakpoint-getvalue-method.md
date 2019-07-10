---
title: Metodo ICorDebugValueBreakpoint::GetValue
ms.date: 03/30/2017
api_name:
- ICorDebugValueBreakpoint.GetValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValueBreakpoint::GetValue
helpviewer_keywords:
- GetValue method, ICorDebugValueBreakpoint interface [.NET Framework debugging]
- ICorDebugValueBreakpoint::GetValue method [.NET Framework debugging]
ms.assetid: 52a73654-bc47-48b6-b2b1-a4456b10140c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 639b34093e79933b4daaa0e3ae5223f1a1a51bf6
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67773773"
---
# <a name="icordebugvaluebreakpointgetvalue-method"></a><span data-ttu-id="095df-102">Metodo ICorDebugValueBreakpoint::GetValue</span><span class="sxs-lookup"><span data-stu-id="095df-102">ICorDebugValueBreakpoint::GetValue Method</span></span>
<span data-ttu-id="095df-103">Ottiene un puntatore a interfaccia a un oggetto "ICorDebugValue" che rappresenta il valore dell'oggetto in cui è impostato il punto di interruzione.</span><span class="sxs-lookup"><span data-stu-id="095df-103">Gets an interface pointer to an "ICorDebugValue" object that represents the value of the object on which the breakpoint is set.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="095df-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="095df-104">Syntax</span></span>  
  
```cpp  
HRESULT GetValue (  
    [out] ICorDebugValue   **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="095df-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="095df-105">Parameters</span></span>  
 `ppValue`  
 <span data-ttu-id="095df-106">[out] Un puntatore all'indirizzo di un `ICorDebugValue` oggetto.</span><span class="sxs-lookup"><span data-stu-id="095df-106">[out] A pointer to the address of an `ICorDebugValue` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="095df-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="095df-107">Requirements</span></span>  
 <span data-ttu-id="095df-108">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="095df-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="095df-109">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="095df-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="095df-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="095df-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="095df-111">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="095df-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="095df-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="095df-112">See also</span></span>
