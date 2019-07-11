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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 36a33b74a692761d772a888ce918aa28a2d92678
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67760563"
---
# <a name="icordebugstepperstepout-method"></a>Metodo ICorDebugStepper::StepOut
Fa sì che questo ICorDebugStepper passo a passo del thread e che venga completato quando il frame corrente restituisce il controllo al chiama frame.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT StepOut ();  
```  
  
## <a name="remarks"></a>Note  
 Oggetto `StepOut` operazione verrà completata dopo essere tornati in genere dal frame corrente per il frame di chiamata.  
  
 Se `StepOut` viene chiamato quando nel codice non gestito, il passaggio verrà completata quando il frame corrente viene restituito al codice gestito che lo ha chiamato.  
  
 In .NET Framework versione 2.0, non usare `StepOut` con il flag STOP_UNMANAGED set poiché avrà esito negativo. (Usare [SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) impostare i flag per l'esecuzione di istruzioni.) Debugger di interoperabilità devono Esci da istruzione al codice nativo se stessi.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
