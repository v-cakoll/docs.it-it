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
ms.openlocfilehash: c7a95f09d1baebed65bae994550431d88ba0dfc9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugcontrollerterminate-method"></a>Metodo ICorDebugController::Terminate
Termina il processo con il codice di uscita specificato.  
  
> [!NOTE]
>  Questo metodo è un wrapper per Win32 `TerminateProcess` (funzione). Di conseguenza, `Terminate` utilizza il codice di uscita nello stesso modo in cui Win32 `TerminateProcess` funzione.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT Terminate (  
    [in] UINT exitCode  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `exitCode`  
 [in] Un valore numerico che rappresenta il codice di uscita. I valori numerici validi sono definiti in winbase.  
  
## <a name="remarks"></a>Note  
 Se il processo viene arrestato quando `Terminate` viene chiamato, il processo di proseguire con la [ICorDebugController:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) metodo in modo che il debugger riceve una conferma di chiusura tramite il [ ICorDebugManagedCallback::](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md) o [ICorDebugManagedCallback:: ExitAppDomain](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitappdomain-method.md) callback.  
  
> [!NOTE]
>  Questo metodo non è implementato da un dominio applicazione. Ovvero, non è implementato nel <xref:System.AppDomain> livello.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cordebug. idl, Cordebug. H  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 
