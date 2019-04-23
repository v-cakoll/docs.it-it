---
title: Interfaccia ICorDebugThread
ms.date: 03/30/2017
api_name:
- ICorDebugThread
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread
helpviewer_keywords:
- ICorDebugThread interface [.NET Framework debugging]
ms.assetid: 3930fd9b-2bc3-4b72-80a0-b6eeb94d60c6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: db322bbdc7293410968542d0d22c572edb87795a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59184704"
---
# <a name="icordebugthread-interface"></a>Interfaccia ICorDebugThread
Rappresenta un thread in un processo. Il ciclo di vita di un'istanza di `ICorDebugThread` equivale a quello del thread che rappresenta.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo ClearCurrentException](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-clearcurrentexception-method.md)|Questo metodo non è implementato. Non usarlo.|  
|[Metodo CreateEval](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-createeval-method.md)|Crea un oggetto ICorDebugEval che opera su questo `ICorDebugThread`.|  
|[Metodo CreateStepper](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-createstepper-method.md)|Crea un oggetto ICorDebugStepper che consente di scorrere il frame attivo in questo `ICorDebugThread`.|  
|[Metodo EnumerateChains](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-enumeratechains-method.md)|Ottiene un puntatore a interfaccia per un enumeratore ICorDebugChainEnum che contiene tutte le catene dello stack in `ICorDebugThread`.|  
|[Metodo GetActiveChain](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getactivechain-method.md)|Ottiene un puntatore a interfaccia ICorDebugChain attiva su questo `ICorDebugThread`.|  
|[Metodo GetActiveFrame](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getactiveframe-method.md)|Ottiene un puntatore a interfaccia ICorDebugFrame attiva su questo `ICorDebugThread`.|  
|[Metodo GetAppDomain](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getappdomain-method.md)|Ottiene un puntatore a interfaccia per il dominio dell'applicazione in cui questo `ICorDebugThread` è attualmente in esecuzione.|  
|[Metodo GetCurrentException](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getcurrentexception-method.md)|Ottiene un puntatore a interfaccia a un oggetto ICorDebugValue che rappresenta un'eccezione generata dal codice gestito.|  
|[Metodo GetDebugState](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getdebugstate-method.md)|Ottiene un valore CorDebugThreadState che descrive lo stato di debug corrente di questo `ICorDebugThread`.|  
|[Metodo GetHandle](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-gethandle-method.md)|Ottiene l'handle corrente per la parte attiva di `ICorDebugThread`.|  
|[Metodo GetID](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getid-method.md)|Ottiene l'identificatore del sistema operativo corrente della parte attiva di questo `ICorDebugThread`.|  
|[Metodo GetObject](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getobject-method.md)|Ottiene un puntatore a interfaccia per il thread di common language runtime (CLR).|  
|[Metodo GetProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getprocess-method.md)|Ottiene un puntatore a interfaccia per il processo di cui questo `ICorDebugThread` costituisce una parte.|  
|[Metodo GetRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getregisterset-method.md)|Ottiene un puntatore di interfaccia al set di registri associato a questo `ICorDebugThread`.|  
|[Metodo GetUserState](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getuserstate-method.md)|Ottiene una combinazione bit per bit dei valori CorDebugUserState che descrivono lo stato corrente di questo `ICorDebugThread`.|  
|[Metodo SetDebugState](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-setdebugstate-method.md)|Imposta una combinazione bit per bit di `CorDebugThreadState` i valori che descrivono lo stato di debug di questo `ICorDebugThread`.|  
  
## <a name="remarks"></a>Note  
  
> [!NOTE]
>  Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
