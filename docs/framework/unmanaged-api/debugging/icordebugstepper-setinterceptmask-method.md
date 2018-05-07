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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7654a91180dd0b4148cfb85b35bf1ce730764f28
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugsteppersetinterceptmask-method"></a>Metodo ICorDebugStepper::SetInterceptMask
Imposta un valore che specifica i tipi di codice che viene eseguito l'accesso.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT SetInterceptMask (  
    [in] CorDebugIntercept    mask  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `mask`  
 [in] Una combinazione dei valori dell'enumerazione CorDebugIntercept che specifica i tipi di codice.  
  
## <a name="remarks"></a>Note  
 Se il bit di un intercettore è impostato, il gestore di istruzioni verrà completata quando viene rilevato il tipo specificato di intercettazione di codice. Se il bit è deselezionato, il codice di intercettazione verrà ignorato.  
  
 Il `SetInterceptMask` metodo potrebbe avere con [ICorDebugStepper:: SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) (dal punto di vista dell'utente). Ad esempio, se visibile solo (vale a dire non interna) parte del codice di inizializzazione classe manca le informazioni di mapping e STOP_NO_MAPPING_INFO non è impostato (vedere il [ICorDebugStepper:: SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) (metodo) e Enumerazione CorDebugUnmappedStop), il salterà l'inizializzazione della classe. Per impostazione predefinita, solo il valore INTERCEPT_NONE il `CorDebugIntercept` verrà utilizzata l'enumerazione.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cordebug. idl, Cordebug. H  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
