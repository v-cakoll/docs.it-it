---
title: Metodo ICorDebugStepper::SetRangeIL
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.SetRangeIL
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::SetRangeIL
helpviewer_keywords:
- SetRangeIL method [.NET Framework debugging]
- ICorDebugStepper::SetRangeIL method [.NET Framework debugging]
ms.assetid: a20c95f0-6da7-4b41-b27f-584211cebb92
topic_type:
- apiref
ms.openlocfilehash: 88270cb73515cc1a671bfb3fb5c479697ad7b359
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137540"
---
# <a name="icordebugsteppersetrangeil-method"></a>Metodo ICorDebugStepper::SetRangeIL
Imposta un valore che specifica se le chiamate a [ICorDebugStepper:: StepRange](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md) passano valori di argomento relativi al codice nativo o rispetto al codice MSIL (Microsoft Intermediate Language) del metodo di cui è in corso il passaggio.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT SetRangeIL (  
    [in] BOOL    bIL  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `bIL`  
 in Impostare su `true` per specificare che gli intervalli sono relativi al codice MSIL. Impostare su `false` per specificare che gli intervalli sono relativi al codice nativo. Il valore predefinito è `true`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
