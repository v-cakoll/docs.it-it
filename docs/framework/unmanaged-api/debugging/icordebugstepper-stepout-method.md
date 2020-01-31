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
ms.openlocfilehash: 08cf2d0bb09080296fc1fcc69b5817f4d6118765
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791720"
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
  
 In .NET Framework versione 2,0, non usare `StepOut` con il flag di STOP_UNMANAGED impostato in quanto avrà esito negativo. (Usare [ICorDebugStepper:: SetUnmappedStopMask](icordebugstepper-setunmappedstopmask-method.md) per impostare i flag per l'esecuzione di un'istruzione). I debugger di interoperabilità devono uscire dal codice nativo.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
