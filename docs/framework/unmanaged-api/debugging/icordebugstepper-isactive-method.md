---
title: Metodo ICorDebugStepper::IsActive
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.IsActive
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::IsActive
helpviewer_keywords:
- IsActive method, ICorDebugStepper interface [.NET Framework debugging]
- ICorDebugStepper::IsActive method [.NET Framework debugging]
ms.assetid: 8b35e7a9-b40e-40a9-8d8e-b82e823fc575
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9dde27f74ac59d033b6e25fba1dbb8e52c4b91af
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67760683"
---
# <a name="icordebugstepperisactive-method"></a>Metodo ICorDebugStepper::IsActive
Ottiene un valore che indica se questo ICorDebugStepper è in esecuzione un passaggio.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT IsActive (  
    [out] BOOL   *pbActive  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pbActive`  
 [out] Restituisce `true` se il gestore di istruzioni sta attualmente eseguendo un'istruzione; in caso contrario, restituisce `false`.  
  
## <a name="remarks"></a>Note  
 Qualsiasi azione passaggio rimane attivo finché il debugger non riceve un [StepComplete](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-stepcomplete-method.md) chiamare, che disattiva automaticamente il gestore di istruzioni. Un gestore di istruzioni può anche essere disattivato in modo anomalo chiamando [ICorDebugStepper](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-deactivate-method.md) prima del callback di condizione viene raggiunto.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
