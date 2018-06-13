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
ms.openlocfilehash: b8ff07c483ef1bcbf9d5141b7180cea08454ebef
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33417099"
---
# <a name="icordebugvaluebreakpointgetvalue-method"></a><span data-ttu-id="447e2-102">Metodo ICorDebugValueBreakpoint::GetValue</span><span class="sxs-lookup"><span data-stu-id="447e2-102">ICorDebugValueBreakpoint::GetValue Method</span></span>
<span data-ttu-id="447e2-103">Ottiene un puntatore a interfaccia a un oggetto "ICorDebugValue" che rappresenta il valore dell'oggetto su cui è impostato il punto di interruzione.</span><span class="sxs-lookup"><span data-stu-id="447e2-103">Gets an interface pointer to an "ICorDebugValue" object that represents the value of the object on which the breakpoint is set.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="447e2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="447e2-104">Syntax</span></span>  
  
```  
HRESULT GetValue (  
    [out] ICorDebugValue   **ppValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="447e2-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="447e2-105">Parameters</span></span>  
 `ppValue`  
 <span data-ttu-id="447e2-106">[out] Un puntatore all'indirizzo di un `ICorDebugValue` oggetto.</span><span class="sxs-lookup"><span data-stu-id="447e2-106">[out] A pointer to the address of an `ICorDebugValue` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="447e2-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="447e2-107">Requirements</span></span>  
 <span data-ttu-id="447e2-108">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="447e2-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="447e2-109">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="447e2-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="447e2-110">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="447e2-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="447e2-111">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="447e2-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="447e2-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="447e2-112">See Also</span></span>  
 
