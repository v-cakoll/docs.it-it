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
ms.openlocfilehash: 851a127c117b826c271dd021c41cfdb36045a1ff
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76783750"
---
# <a name="icordebugcontrollerterminate-method"></a>Metodo ICorDebugController::Terminate
Termina il processo con il codice di uscita specificato.  
  
> [!NOTE]
> Questo metodo è un wrapper per la funzione Win32 `TerminateProcess`. Pertanto, `Terminate` utilizza il codice di uscita nello stesso modo in cui la funzione `TerminateProcess` Win32 la utilizza.  
  
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
 Se il processo viene interrotto quando viene chiamato `Terminate`, il processo deve essere continuato usando il metodo [ICorDebugController:: continue](icordebugcontroller-continue-method.md) , in modo che il debugger riceva la conferma della terminazione tramite il callback [ICorDebugManagedCallback:: ExitProcess](icordebugmanagedcallback-exitprocess-method.md) o [ICorDebugManagedCallback:: ExitAppDomain](icordebugmanagedcallback-exitappdomain-method.md) .  
  
> [!NOTE]
> Questo metodo non è implementato da un dominio applicazione. Ovvero non viene implementato a livello di <xref:System.AppDomain>.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
