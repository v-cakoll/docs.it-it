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
ms.openlocfilehash: da799b0d4f4e5e4b281445baa35d95f992ba0b63
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61987454"
---
# <a name="icordebugsteppersetunmappedstopmask-method"></a>Metodo ICorDebugStepper::SetUnmappedStopMask
Imposta un valore che specifica il tipo di codice non mappato in cui verrà interrotta l'esecuzione.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT SetUnmappedStopMask (  
    [in] CorDebugUnmappedStop   mask  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `mask`  
 [in] Valore dell'enumerazione CorDebugUnmappedStop che specifica il tipo di codice non mappato in cui il debugger si arresta l'esecuzione.  
  
 Il valore predefinito è STOP_OTHER_UNMAPPED. Il valore STOP_UNMANAGED è valido solo con il debug di interoperabilità.  
  
## <a name="remarks"></a>Note  
 Quando il debugger rileva una compilazione just-in-time (JIT) non ha alcun mapping corrispondente in Microsoft intermediate language (MSIL), arresterà l'esecuzione se è stato impostato il flag che specifica tale tipo di codice non mappato; in caso contrario, l'esecuzione di istruzioni in modo trasparente continua.  
  
 Se il debugger non usa un gestore di istruzioni per immettere un metodo, quindi non sarà necessariamente Esegui istruzione/routine codice non mappato.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
