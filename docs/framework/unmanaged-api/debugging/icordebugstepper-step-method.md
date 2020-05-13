---
title: Metodo ICorDebugStepper::Step
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.Step
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::Step
helpviewer_keywords:
- Step method, ICorDebugStepper interface [.NET Framework debugging]
- ICorDebugStepper::Step method [.NET Framework debugging]
ms.assetid: 38c1940b-ada1-40ba-8295-4c0833744e1e
topic_type:
- apiref
ms.openlocfilehash: 39d2fd0163b0e61295187461d5dbdf5742450306
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379511"
---
# <a name="icordebugstepperstep-method"></a>Metodo ICorDebugStepper::Step
Fa in modo che questo ICorDebugStepper in un unico passaggio attraverso il thread contenitore e, facoltativamente, per continuare a eseguire l'istruzione singola con le funzioni che vengono chiamate all'interno del thread.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT Step (  
    [in] BOOL   bStepIn  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `bStepIn`  
 in Impostare su `true` per eseguire un'istruzione in una funzione chiamata all'interno del thread. Impostare su `false` per eseguire l'istruzione/routine della funzione.  
  
## <a name="remarks"></a>Osservazioni  
 Il passaggio viene completato quando il Common Language Runtime esegue l'istruzione gestita successiva nel frame di questo stepper. Se `Step` viene chiamato su un stepper, che non si trova nel codice gestito, il passaggio verrà completato quando l'istruzione del codice gestito successiva viene eseguita dal thread.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
