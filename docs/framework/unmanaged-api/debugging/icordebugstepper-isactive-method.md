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
ms.openlocfilehash: 703f454f7ed1d2a959b761726f433db22cb73b01
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791779"
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
 out Restituisce `true` se il gestore di istruzioni sta attualmente eseguendo un passaggio; in caso contrario, restituisce `false`.  
  
## <a name="remarks"></a>Note  
 Qualsiasi azione Step rimane attiva fino a quando il debugger non riceve una chiamata [ICorDebugManagedCallback:: StepComplete](icordebugmanagedcallback-stepcomplete-method.md) , che disattiva automaticamente il stepper. Un stepper può anche essere disattivato in modo anomalo chiamando [ICorDebugStepper::D ttiva](icordebugstepper-deactivate-method.md) prima che venga raggiunta la condizione di callback.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
