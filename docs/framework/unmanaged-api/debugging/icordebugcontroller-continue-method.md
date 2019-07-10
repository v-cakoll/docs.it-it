---
title: Metodo ICorDebugController::Continue
ms.date: 03/30/2017
api_name:
- ICorDebugController.Continue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::Continue
helpviewer_keywords:
- Continue method [.NET Framework debugging]
- ICorDebugController::Continue method [.NET Framework debugging]
ms.assetid: 8684cd06-ad3e-48ef-832e-15320e1f43a2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c3a4e98a7265bda288b20b1cee1a10ab11990e8e
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67748879"
---
# <a name="icordebugcontrollercontinue-method"></a>Metodo ICorDebugController::Continue
Riprende l'esecuzione dei thread gestiti dopo una chiamata a [metodo Stop](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-stop-method.md).  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT Continue (  
    [in] BOOL fIsOutOfBand  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `fIsOutOfBand`  
 [in] Impostare su `true` andare a un evento di out-of-band; in caso contrario, impostato su `false`.  
  
## <a name="remarks"></a>Note  
 `Continue` continua il processo dopo una chiamata al `ICorDebugController::Stop` (metodo).  
  
 Quando si esegue il debug in modalità mista, non chiamare `Continue` in Win32 evento thread a meno che non si continui da un evento di out-of-band.  
  
 Un' *eventi in banda* è un evento gestito o un normale evento non gestito durante il quale il debugger supporta l'interazione con la gestione degli Stati del processo. In questo caso, il debugger riceve la [ICorDebugUnmanagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-debugevent-method.md) callback con relativo `fOutOfBand` parametro impostato su `false`.  
  
 Un' *evento out-of-band* è un evento non gestito durante il quale è possibile l'interazione con la gestione degli Stati del processo durante il processo viene arrestato a causa di un evento. In questo caso, il debugger riceve la `ICorDebugUnmanagedCallback::DebugEvent` callback con relativo `fOutOfBand` parametro impostato su `true`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
