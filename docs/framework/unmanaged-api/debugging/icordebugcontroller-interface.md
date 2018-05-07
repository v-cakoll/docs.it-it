---
title: ICorDebugController Interface1
ms.date: 03/30/2017
api_name:
- ICorDebugController
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController
helpviewer_keywords:
- ICorDebugController interface [.NET Framework debugging]
ms.assetid: dbb1c4dc-269a-459b-ab1d-6c70788782ce
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 230488201b637c5a53f41dd4c3f204b37e8984fd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugcontroller-interface1"></a>ICorDebugController Interface1
Rappresenta un ambito, ossia <xref:System.Diagnostics.Process> o <xref:System.AppDomain>, in cui è possibile controllare il contesto di esecuzione del codice.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|`ICorDebugController::CanCommitChanges`|Questo metodo è obsoleto.|  
|`ICorDebugController::CommitChanges`|Questo metodo è obsoleto.|  
|[Metodo Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md)|Riprende l'esecuzione dei thread gestiti dopo una chiamata a [ICorDebugController:: Stop](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-stop-method.md).|  
|[Metodo Detach](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-detach-method.md)|Disconnette il debugger dal dominio applicazione o processo.|  
|[Metodo EnumerateThreads](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-enumeratethreads-method.md)|Ottiene un enumeratore per i thread gestiti attivi nel processo.|  
|[Metodo HasQueuedCallbacks](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-hasqueuedcallbacks-method.md)|Ottiene un valore che indica se i callback gestiti attualmente in coda per il thread specificato.|  
|[Metodo IsRunning](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-isrunning-method.md)|Ottiene un valore che indica se il thread del processo attualmente in esecuzione liberamente.|  
|[Metodo SetAllThreadsDebugState](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-setallthreadsdebugstate-method.md)|Imposta lo stato di debug di tutti i thread gestiti nel processo.|  
|[Metodo Stop](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-stop-method.md)|Esegue un'interruzione cooperativa su tutti i thread che eseguono codice gestito nel processo.|  
|[Metodo Terminate](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-terminate-method.md)|Termina il processo con il codice di uscita specificato.|  
  
## <a name="remarks"></a>Note  
 Se `ICorDebugController` è un processo di controllo, l'ambito include tutti i thread del processo. Se `ICorDebugController` è controlla un dominio applicazione, l'ambito include solo i thread di quel particolare dominio applicazione.  
  
> [!NOTE]
>  Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cordebug. idl, Cordebug. H  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
