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
ms.openlocfilehash: faddf30248b58c68037635480d8977f22ad077d0
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379027"
---
# <a name="icordebugstepperisactive-method"></a>Metodo ICorDebugStepper::IsActive
Ottiene un valore che indica se questo ICorDebugStepper sta attualmente eseguendo un passaggio.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT IsActive (  
    [out] BOOL   *pbActive  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pbActive`  
 out Restituisce `true` se il gestore di istruzioni sta attualmente eseguendo un passaggio; in caso contrario, restituisce `false` .  
  
## <a name="remarks"></a>Osservazioni  
 Qualsiasi azione Step rimane attiva fino a quando il debugger non riceve una chiamata [ICorDebugManagedCallback:: StepComplete](icordebugmanagedcallback-stepcomplete-method.md) , che disattiva automaticamente il stepper. Un stepper può anche essere disattivato in modo anomalo chiamando [ICorDebugStepper::D ttiva](icordebugstepper-deactivate-method.md) prima che venga raggiunta la condizione di callback.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
