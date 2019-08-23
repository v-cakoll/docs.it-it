---
title: Metodo ICorDebugController::Terminate
ms.date: 03/30/2017
api_name:
- ICorDebugController.Terminate
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::Terminate
helpviewer_keywords:
- Terminate method, ICorDebugController interface [.NET Framework debugging]
- ICorDebugController::Terminate method [.NET Framework debugging]
ms.assetid: 4275af0c-b5a7-4e4c-97c9-7e41f36b2dd8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ee1c30809567097e67b6b1e40f5534429d748abd
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964362"
---
# <a name="icordebugcontrollerterminate-method"></a>Metodo ICorDebugController::Terminate
Termina il processo con il codice di uscita specificato.  
  
> [!NOTE]
> Questo metodo è un wrapper per la funzione `TerminateProcess` Win32. Quindi, `Terminate` usa il codice di uscita nello stesso modo in cui la `TerminateProcess` funzione Win32 la USA.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT Terminate (  
    [in] UINT exitCode  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `exitCode`  
 in Valore numerico che rappresenta il codice di uscita. I valori numerici validi sono definiti in winbase. h.  
  
## <a name="remarks"></a>Note  
 Se il processo viene interrotto quando `Terminate` viene chiamato il metodo, il processo deve essere continuato usando il metodo [ICorDebugController:: continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) , in modo che il debugger riceva la conferma della terminazione tramite [ICorDebugManagedCallback:: ](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md)Callback di ExitProcess o [ICorDebugManagedCallback:: ExitAppDomain](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitappdomain-method.md) .  
  
> [!NOTE]
> Questo metodo non è implementato da un dominio applicazione. Ovvero non viene implementato a <xref:System.AppDomain> livello di.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug. idl, CorDebug. h  
  
 **Libreria** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
