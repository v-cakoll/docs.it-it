---
title: Metodo ICorDebugStepper::SetInterceptMask
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.SetInterceptMask
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::SetInterceptMask
helpviewer_keywords:
- SetInterceptMask method [.NET Framework debugging]
- ICorDebugStepper::SetInterceptMask method [.NET Framework debugging]
ms.assetid: 6245e2ae-5cc2-43ff-8cc1-71953d12113a
topic_type:
- apiref
ms.openlocfilehash: e88fa543eca39c14962f0dbbe8053829713401c8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137586"
---
# <a name="icordebugsteppersetinterceptmask-method"></a>Metodo ICorDebugStepper::SetInterceptMask
Imposta un valore che specifica i tipi di codice sottoposti a istruzione.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT SetInterceptMask (  
    [in] CorDebugIntercept    mask  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `mask`  
 in Combinazione di valori dell'enumerazione CorDebugIntercept che specifica i tipi di codice.  
  
## <a name="remarks"></a>Note  
 Se viene impostato il bit per un intercettore, il stepper verrà completato quando viene rilevato il tipo di codice di intercettazione specificato. Se il bit è deselezionato, il codice di intercettazione verrà ignorato.  
  
 Il metodo `SetInterceptMask` può avere interazioni impreviste con [ICorDebugStepper:: SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) (dal punto di vista dell'utente). Se, ad esempio, l'unica parte visibile (ovvero non interna) del codice di inizializzazione della classe non dispone di informazioni di mapping e STOP_NO_MAPPING_INFO non è impostato (vedere il metodo [ICorDebugStepper:: SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) e CorDebugUnmappedStop Enumeration), il stepper eseguirà un'istruzione/routine dell'inizializzazione della classe. Per impostazione predefinita, verrà utilizzato solo il valore INTERCEPT_NONE dell'enumerazione `CorDebugIntercept`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
