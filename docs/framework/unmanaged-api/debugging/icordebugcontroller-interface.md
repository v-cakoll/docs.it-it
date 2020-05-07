---
title: Interfaccia ICorDebugController
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
ms.openlocfilehash: e494bbb24e8f2245593e7945625e72e70ae1dde5
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2020
ms.locfileid: "82892764"
---
# <a name="icordebugcontroller-interface"></a>Interfaccia ICorDebugController

Rappresenta un ambito, ossia <xref:System.Diagnostics.Process> o <xref:System.AppDomain>, in cui è possibile controllare il contesto di esecuzione del codice.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|`ICorDebugController::CanCommitChanges`|Questo metodo è obsoleto.|  
|`ICorDebugController::CommitChanges`|Questo metodo è obsoleto.|  
|[Metodo Continue](icordebugcontroller-continue-method.md)|Riprende l'esecuzione di thread gestiti dopo una chiamata a [ICorDebugController:: Stop](icordebugcontroller-stop-method.md).|  
|[Metodo Detach](icordebugcontroller-detach-method.md)|Scollega il debugger dal dominio del processo o dell'applicazione.|  
|[Metodo EnumerateThreads](icordebugcontroller-enumeratethreads-method.md)|Ottiene un enumeratore per i thread gestiti attivi nel processo.|  
|[Metodo HasQueuedCallbacks](icordebugcontroller-hasqueuedcallbacks-method.md)|Ottiene un valore che indica se i callback gestiti sono attualmente in coda per il thread specificato.|  
|[Metodo IsRunning](icordebugcontroller-isrunning-method.md)|Ottiene un valore che indica se i thread del processo sono attualmente in esecuzione liberamente.|  
|[Metodo SetAllThreadsDebugState](icordebugcontroller-setallthreadsdebugstate-method.md)|Imposta lo stato di debug di tutti i thread gestiti nel processo.|  
|[Metodo Stop](icordebugcontroller-stop-method.md)|Esegue un arresto cooperativo su tutti i thread che eseguono codice gestito nel processo.|  
|[Metodo Terminate](icordebugcontroller-terminate-method.md)|Termina il processo con il codice di uscita specificato.|  
  
## <a name="remarks"></a>Osservazioni  
 Se `ICorDebugController` controlla un processo, l'ambito include tutti i thread del processo. Se `ICorDebugController` controlla un dominio applicazione, l'ambito include solo i thread di quel particolare dominio applicazione.  
  
> [!NOTE]
> Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di debug](debugging-interfaces.md)
