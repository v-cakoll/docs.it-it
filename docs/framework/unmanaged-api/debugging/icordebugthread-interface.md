---
title: ICorDebugThread Interface1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugThread
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugThread
helpviewer_keywords: ICorDebugThread interface [.NET Framework debugging]
ms.assetid: 3930fd9b-2bc3-4b72-80a0-b6eeb94d60c6
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 25b5c8f0720402cce56c69394c6fbe2fb70a6177
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugthread-interface1"></a>ICorDebugThread Interface1
Rappresenta un thread in un processo. Il ciclo di vita di un'istanza di `ICorDebugThread` equivale a quello del thread che rappresenta.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[ClearCurrentException (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-clearcurrentexception-method.md)|Questo metodo non è implementato. Non usarlo.|  
|[CreateEval (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-createeval-method.md)|Crea un oggetto ICorDebugEval che agisce su questo `ICorDebugThread`.|  
|[CreateStepper (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-createstepper-method.md)|Crea un oggetto ICorDebugStepper che consente l'esecuzione passo passo del frame attivo in questo `ICorDebugThread`.|  
|[EnumerateChains (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-enumeratechains-method.md)|Ottiene un puntatore a interfaccia a un enumeratore ICorDebugChainEnum contenente tutte le catene dello stack in `ICorDebugThread`.|  
|[GetActiveChain (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getactivechain-method.md)|Ottiene un puntatore a interfaccia ICorDebugChain attiva su questo `ICorDebugThread`.|  
|[GetActiveFrame (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getactiveframe-method.md)|Ottiene un puntatore a interfaccia ICorDebugFrame attiva su questo `ICorDebugThread`.|  
|[GetAppDomain (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getappdomain-method.md)|Ottiene un puntatore a interfaccia per il dominio dell'applicazione in cui `ICorDebugThread` è attualmente in esecuzione.|  
|[GetCurrentException (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getcurrentexception-method.md)|Ottiene un puntatore a interfaccia a un oggetto ICorDebugValue che rappresenta un'eccezione generata dal codice gestito.|  
|[GetDebugState (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getdebugstate-method.md)|Ottiene un valore CorDebugThreadState che descrive lo stato di debug corrente di questo `ICorDebugThread`.|  
|[GetHandle (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-gethandle-method.md)|Ottiene l'handle corrente per la parte attiva di `ICorDebugThread`.|  
|[GetID (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getid-method.md)|Ottiene l'identificatore del sistema operativo corrente della parte attiva di `ICorDebugThread`.|  
|[GetObject (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getobject-method.md)|Ottiene un puntatore a interfaccia per il thread di common language runtime (CLR).|  
|[GetProcess (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getprocess-method.md)|Ottiene un puntatore a interfaccia per il processo di cui `ICorDebugThread` costituisce una parte.|  
|[GetRegisterSet (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getregisterset-method.md)|Ottiene un puntatore a interfaccia al set di registri associato a questo `ICorDebugThread`.|  
|[GetUserState (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getuserstate-method.md)|Ottiene una combinazione bit per bit di valori CorDebugUserState che descrivono lo stato corrente di questo `ICorDebugThread`.|  
|[SetDebugState (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-setdebugstate-method.md)|Ottiene una combinazione bit per bit di `CorDebugThreadState` valori che descrivono lo stato di debug di questo `ICorDebugThread`.|  
  
## <a name="remarks"></a>Note  
  
> [!NOTE]
>  Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
