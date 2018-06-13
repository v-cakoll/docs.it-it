---
title: Metodo ICorDebugStepper::SetUnmappedStopMask
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.SetUnmappedStopMask
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::SetUnmappedStopMask
helpviewer_keywords:
- ICorDebugStepper::SetUnmappedStopMask method [.NET Framework debugging]
- SetUnmappedStopMask method [.NET Framework debugging]
ms.assetid: b1211981-e90c-4e05-8def-fa18d85ad9ab
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dc4e51ec60c7526f36bbe4909bec91a527e0862c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33419910"
---
# <a name="icordebugsteppersetunmappedstopmask-method"></a>Metodo ICorDebugStepper::SetUnmappedStopMask
Imposta un valore che specifica il tipo di codice non mappato in cui verrà interrotta l'esecuzione.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT SetUnmappedStopMask (  
    [in] CorDebugUnmappedStop   mask  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `mask`  
 [in] Valore dell'enumerazione CorDebugUnmappedStop che specifica il tipo di codice non mappato nel quale il debugger verrà interrotta l'esecuzione.  
  
 Il valore predefinito è STOP_OTHER_UNMAPPED. Il valore STOP_UNMANAGED è valido solo con il debug di interoperabilità.  
  
## <a name="remarks"></a>Note  
 Quando il debugger rileva una compilazione just-in-time (JIT) è disponibile alcun mapping corrispondente in Microsoft intermediate language (MSIL), arresterà l'esecuzione se è stato impostato il flag che specifica il tipo di codice non mappato; in caso contrario, l'esecuzione di istruzioni in modo trasparente continua.  
  
 Se il debugger non viene utilizzato un gestore di istruzioni per immettere un metodo, quindi non necessariamente le istruzioni nel codice non mappato.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cordebug. idl, Cordebug. H  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
