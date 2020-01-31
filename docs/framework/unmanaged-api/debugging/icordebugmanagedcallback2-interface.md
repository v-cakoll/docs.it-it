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
ms.openlocfilehash: 43982ebb634843c0130c3321aa84c90b84e8c786
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793305"
---
# <a name="icordebugmanagedcallback2-interface"></a>Interfaccia ICorDebugManagedCallback2
Fornisce metodi che supportano la gestione delle eccezioni del debugger e assistenti al debug gestito. `ICorDebugManagedCallback2` è un'estensione logica dell'interfaccia [ICorDebugManagedCallback](icordebugmanagedcallback-interface.md) .  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo ChangeConnection](icordebugmanagedcallback2-changeconnection-method.md)|Notifica al debugger che è stato modificato il set di attività associato alla connessione specificata.|  
|[Metodo CreateConnection](icordebugmanagedcallback2-createconnection-method.md)|Notifica al debugger che è stata creata una nuova connessione.|  
|[Metodo DestroyConnection](icordebugmanagedcallback2-destroyconnection-method.md)|Notifica al debugger che la connessione specificata è stata terminata.|  
|[Metodo Exception](icordebugmanagedcallback2-exception-method.md)|Notifica al debugger che è stata avviata una ricerca di un gestore di eccezioni.|  
|[Metodo ExceptionUnwind](icordebugmanagedcallback2-exceptionunwind-method.md)|Fornisce una notifica di stato durante il processo di rimozione dell'eccezione.|  
|[Metodo FunctionRemapComplete](icordebugmanagedcallback2-functionremapcomplete-method.md)|Notifica al debugger che l'esecuzione del codice è cambiata a una nuova versione di una funzione modificata.|  
|[Metodo FunctionRemapOpportunity](icordebugmanagedcallback2-functionremapopportunity-method.md)|Notifica al debugger che l'esecuzione del codice ha raggiunto un punto di sequenza in una versione precedente di una funzione modificata.|  
|[Metodo MDANotification](icordebugmanagedcallback2-mdanotification-method.md)|Fornisce la notifica che l'esecuzione del codice ha rilevato un messaggio assistente al debug gestito (MDA).|  
  
## <a name="remarks"></a>Note  
 L'interfaccia `ICorDebugManagedCallback2` estende l'interfaccia `ICorDebugManagedCallback` per gestire i nuovi eventi di debug introdotti nella versione .NET Framework 2,0.  
  
 Un debugger deve implementare `ICorDebugManagedCallback2` se esegue il debug .NET Framework applicazioni 2,0. Un'istanza di `ICorDebugManagedCallback` o `ICorDebugManagedCallback2` viene passata come oggetto callback a [ICorDebug:: SetManagedHandler](icordebug-setmanagedhandler-method.md).  
  
> [!NOTE]
> Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Diagnostica degli errori tramite gli assistenti al debug gestito](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [Interfacce di debug](debugging-interfaces.md)
- [Interfaccia ICorDebugManagedCallback](icordebugmanagedcallback-interface.md)
