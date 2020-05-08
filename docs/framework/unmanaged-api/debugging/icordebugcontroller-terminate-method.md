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
ms.openlocfilehash: eade3fd5d946c44ae4a77c571f762709de3cef40
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976564"
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
  
## <a name="remarks"></a>Osservazioni  
 Se il processo viene interrotto quando `Terminate` viene chiamato il metodo, il processo deve essere continuato usando il metodo [ICorDebugController:: continue](icordebugcontroller-continue-method.md) , in modo che il debugger riceva la conferma della terminazione tramite il callback [ICorDebugManagedCallback:: ExitProcess](icordebugmanagedcallback-exitprocess-method.md) o [ICorDebugManagedCallback:: ExitAppDomain](icordebugmanagedcallback-exitappdomain-method.md) .  
  
> [!NOTE]
> Questo metodo non è implementato da un dominio applicazione. Ovvero non viene implementato a <xref:System.AppDomain> livello di.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
