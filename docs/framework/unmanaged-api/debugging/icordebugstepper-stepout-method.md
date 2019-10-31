---
title: Metodo ICorDebugStepper::StepOut
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.StepOut
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::StepOut
helpviewer_keywords:
- ICorDebugStepper::StepOut method [.NET Framework debugging]
- StepOut method [.NET Framework debugging]
ms.assetid: aae0f48c-4ede-4256-9251-a7fc85a229dc
topic_type:
- apiref
ms.openlocfilehash: 6c1d7db8aacaf81d47abd4a9cd972b44f56a3bb1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137516"
---
# <a name="icordebugstepperstepout-method"></a>Metodo ICorDebugStepper::StepOut
Fa in modo che questo ICorDebugStepper a un singolo passaggio tramite il thread contenitore e venga completato quando il frame corrente restituisce il controllo al frame chiamante.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT StepOut ();  
```  
  
## <a name="remarks"></a>Note  
 Un'operazione di `StepOut` verrà completata dopo la restituzione normale dal frame corrente al frame chiamante.  
  
 Se `StepOut` viene chiamato quando si trova nel codice non gestito, il passaggio viene completato quando il frame corrente torna al codice gestito che lo ha chiamato.  
  
 In .NET Framework versione 2,0, non usare `StepOut` con il flag STOP_UNMANAGED impostato in quanto avrà esito negativo. (Usare [ICorDebugStepper:: SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) per impostare i flag per l'esecuzione di un'istruzione). I debugger di interoperabilità devono uscire dal codice nativo.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
