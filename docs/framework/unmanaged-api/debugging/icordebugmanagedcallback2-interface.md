---
title: Interfaccia ICorDebugManagedCallback2
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2
helpviewer_keywords:
- ICorDebugManagedCallback2 interface [.NET Framework debugging]
ms.assetid: cf7b7cfa-1c4b-4d8c-be70-4f9ed15a788b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ca33436d98edf5844a5ca27c9ac89648f10ec0c5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69909975"
---
# <a name="icordebugmanagedcallback2-interface"></a>Interfaccia ICorDebugManagedCallback2
Fornisce metodi che supportano la gestione delle eccezioni del debugger e assistenti al debug gestito. `ICorDebugManagedCallback2`è un'estensione logica dell'interfaccia [ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md) .  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo ChangeConnection](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-changeconnection-method.md)|Notifica al debugger che è stato modificato il set di attività associato alla connessione specificata.|  
|[Metodo CreateConnection](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-createconnection-method.md)|Notifica al debugger che è stata creata una nuova connessione.|  
|[Metodo DestroyConnection](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-destroyconnection-method.md)|Notifica al debugger che la connessione specificata è stata terminata.|  
|[Metodo Exception](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-exception-method.md)|Notifica al debugger che è stata avviata una ricerca di un gestore di eccezioni.|  
|[Metodo ExceptionUnwind](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-exceptionunwind-method.md)|Fornisce una notifica di stato durante il processo di rimozione dell'eccezione.|  
|[Metodo FunctionRemapComplete](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-functionremapcomplete-method.md)|Notifica al debugger che l'esecuzione del codice è cambiata a una nuova versione di una funzione modificata.|  
|[Metodo FunctionRemapOpportunity](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-functionremapopportunity-method.md)|Notifica al debugger che l'esecuzione del codice ha raggiunto un punto di sequenza in una versione precedente di una funzione modificata.|  
|[Metodo MDANotification](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-mdanotification-method.md)|Fornisce la notifica che l'esecuzione del codice ha rilevato un messaggio assistente al debug gestito (MDA).|  
  
## <a name="remarks"></a>Note  
 L' `ICorDebugManagedCallback2` interfaccia estende l' `ICorDebugManagedCallback` interfaccia per gestire i nuovi eventi di debug introdotti nella versione .NET Framework 2,0.  
  
 Un debugger deve implementare `ICorDebugManagedCallback2` se esegue il debug di applicazioni .NET Framework 2,0. Un'istanza di `ICorDebugManagedCallback` o `ICorDebugManagedCallback2` viene passata come oggetto callback a [ICorDebug:: SetManagedHandler](../../../../docs/framework/unmanaged-api/debugging/icordebug-setmanagedhandler-method.md).  
  
> [!NOTE]
> Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug. idl, CorDebug. h  
  
 **Libreria** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Diagnostica degli errori tramite gli assistenti al debug gestito](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Interfaccia ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
