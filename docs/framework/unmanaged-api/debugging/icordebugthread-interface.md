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
ms.openlocfilehash: b227b374021136e78f7f061d235eb18eca5b9515
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791481"
---
# <a name="icordebugthread-interface"></a>Interfaccia ICorDebugThread
Rappresenta un thread in un processo. Il ciclo di vita di un'istanza di `ICorDebugThread` equivale a quello del thread che rappresenta.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo ClearCurrentException](icordebugthread-clearcurrentexception-method.md)|Questo metodo non è implementato. Non usarlo.|  
|[Metodo CreateEval](icordebugthread-createeval-method.md)|Crea un oggetto ICorDebugEval che opera su questo `ICorDebugThread`.|  
|[Metodo CreateStepper](icordebugthread-createstepper-method.md)|Crea un oggetto ICorDebugStepper che consente l'esecuzione del frame attivo in questo `ICorDebugThread`.|  
|[Metodo EnumerateChains](icordebugthread-enumeratechains-method.md)|Ottiene un puntatore a interfaccia a un enumeratore ICorDebugChainEnum che contiene tutte le catene dello stack in questo `ICorDebugThread`.|  
|[Metodo GetActiveChain](icordebugthread-getactivechain-method.md)|Ottiene un puntatore a interfaccia per il ICorDebugChain attivo nel `ICorDebugThread`.|  
|[Metodo GetActiveFrame](icordebugthread-getactiveframe-method.md)|Ottiene un puntatore a interfaccia per il ICorDebugFrame attivo nel `ICorDebugThread`.|  
|[Metodo GetAppDomain](icordebugthread-getappdomain-method.md)|Ottiene un puntatore a interfaccia per il dominio dell'applicazione in cui è attualmente in esecuzione il `ICorDebugThread`.|  
|[Metodo GetCurrentException](icordebugthread-getcurrentexception-method.md)|Ottiene un puntatore a interfaccia a un oggetto ICorDebugValue che rappresenta un'eccezione attualmente generata dal codice gestito.|  
|[Metodo GetDebugState](icordebugthread-getdebugstate-method.md)|Ottiene un valore CorDebugThreadState che descrive lo stato di debug corrente di questo `ICorDebugThread`.|  
|[Metodo GetHandle](icordebugthread-gethandle-method.md)|Ottiene l'handle corrente per la parte attiva di questo `ICorDebugThread`.|  
|[Metodo GetID](icordebugthread-getid-method.md)|Ottiene l'identificatore del sistema operativo corrente della parte attiva di questo `ICorDebugThread`.|  
|[Metodo GetObject](icordebugthread-getobject-method.md)|Ottiene un puntatore a interfaccia al thread di Common Language Runtime (CLR).|  
|[Metodo GetProcess](icordebugthread-getprocess-method.md)|Ottiene un puntatore a interfaccia al processo di cui questo `ICorDebugThread` costituisce una parte.|  
|[Metodo GetRegisterSet](icordebugthread-getregisterset-method.md)|Ottiene un puntatore a interfaccia per il set di registri associato a questo `ICorDebugThread`.|  
|[Metodo GetUserState](icordebugthread-getuserstate-method.md)|Ottiene una combinazione bit per bit di valori CorDebugUserState che descrivono lo stato corrente di questo `ICorDebugThread`.|  
|[Metodo SetDebugState](icordebugthread-setdebugstate-method.md)|Imposta una combinazione bit per bit di valori `CorDebugThreadState` che descrivono lo stato di debug di questo `ICorDebugThread`.|  
  
## <a name="remarks"></a>Note  
  
> [!NOTE]
> Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di debug](debugging-interfaces.md)
