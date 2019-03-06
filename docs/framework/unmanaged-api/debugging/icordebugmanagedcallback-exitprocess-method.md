---
title: Metodo ICorDebugManagedCallback::ExitProcess
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.ExitProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::ExitProcess
helpviewer_keywords:
- ExitProcess method, ICorDebugManagedCallback interface [.NET Framework debugging]
- ICorDebugManagedCallback::ExitProcess method [.NET Framework debugging]
ms.assetid: 63a7d47a-0d54-4e29-9767-9f09feaa38b7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b33b38b85bd5b8cfb3502e3fadcd739aac37b2dc
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57476373"
---
# <a name="icordebugmanagedcallbackexitprocess-method"></a>Metodo ICorDebugManagedCallback::ExitProcess
Notifica al debugger che un processo è stato terminato.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT ExitProcess (  
    [in] ICorDebugProcess *pProcess  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pProcess`  
 [in] Un puntatore a un oggetto ICorDebugProcess che rappresenta il processo.  
  
## <a name="remarks"></a>Note  
 Non è possibile continuare da un `ExitProcess` evento. Questo evento possono essere attivati in modo asincrono e gli altri eventi mentre il processo sembra essere stato arrestato. Ciò può verificarsi se il processo viene terminato mentre arrestato, in genere a causa di circostanza esterna.  
  
 Se common language runtime (CLR) sta già inviando un callback gestito, questo evento verrà posticipato fino al dopo tale callback ha restituito.  
  
 Il `ExitProcess` eventi sono l'unico evento/Scaricamento di uscita che viene chiamato in fase di arresto.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Interfaccia ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
