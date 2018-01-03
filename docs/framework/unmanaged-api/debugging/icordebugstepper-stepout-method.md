---
title: Metodo ICorDebugStepper::StepOut
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugStepper.StepOut
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugStepper::StepOut
helpviewer_keywords:
- ICorDebugStepper::StepOut method [.NET Framework debugging]
- StepOut method [.NET Framework debugging]
ms.assetid: aae0f48c-4ede-4256-9251-a7fc85a229dc
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1d6462f166e9c734dacc7ebee13cb82e3b12158b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugstepperstepout-method"></a>Metodo ICorDebugStepper::StepOut
Fa sì che ICorDebugStepper passo a passo del thread e che venga completato quando il frame corrente restituisce il controllo al frame chiamante.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT StepOut ();  
```  
  
## <a name="remarks"></a>Note  
 Oggetto `StepOut` operazione verrà completata dopo la restituzione in genere dal frame corrente per il frame del chiamante.  
  
 Se `StepOut` viene chiamato quando nel codice non gestito, il passaggio verrà completato quando il frame corrente viene restituito al codice gestito che lo hanno chiamato.  
  
 In .NET Framework versione 2.0, non usare `StepOut` con il flag STOP_UNMANAGED set perché avrà esito negativo. (Utilizzare [ICorDebugStepper:: SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) per impostare i flag per l'esecuzione di istruzioni.) Debugger di interoperabilità devono Esci da istruzione al codice nativo se stessi.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
