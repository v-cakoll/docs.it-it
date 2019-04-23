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
ms.openlocfilehash: acdfddd015013215bba9039d871837a60ead1405
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59175091"
---
# <a name="icordebugvaluebreakpointgetvalue-method"></a><span data-ttu-id="2ebaf-102">Metodo ICorDebugValueBreakpoint::GetValue</span><span class="sxs-lookup"><span data-stu-id="2ebaf-102">ICorDebugValueBreakpoint::GetValue Method</span></span>
<span data-ttu-id="2ebaf-103">Ottiene un puntatore a interfaccia a un oggetto "ICorDebugValue" che rappresenta il valore dell'oggetto in cui è impostato il punto di interruzione.</span><span class="sxs-lookup"><span data-stu-id="2ebaf-103">Gets an interface pointer to an "ICorDebugValue" object that represents the value of the object on which the breakpoint is set.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ebaf-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2ebaf-104">Syntax</span></span>  
  
```  
HRESULT GetValue (  
    [out] ICorDebugValue   **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2ebaf-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="2ebaf-105">Parameters</span></span>  
 `ppValue`  
 <span data-ttu-id="2ebaf-106">[out] Un puntatore all'indirizzo di un `ICorDebugValue` oggetto.</span><span class="sxs-lookup"><span data-stu-id="2ebaf-106">[out] A pointer to the address of an `ICorDebugValue` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2ebaf-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2ebaf-107">Requirements</span></span>  
 <span data-ttu-id="2ebaf-108">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2ebaf-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2ebaf-109">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2ebaf-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2ebaf-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2ebaf-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2ebaf-111">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2ebaf-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ebaf-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2ebaf-112">See also</span></span>
