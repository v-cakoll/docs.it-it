---
title: Interfaccia ICorDebugEval
ms.date: 03/30/2017
api_name:
- ICorDebugEval
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval
helpviewer_keywords:
- ICorDebugEval interface [.NET Framework debugging]
ms.assetid: 3a5c9815-832d-47e1-b7f7-bbba135d7cf1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cfd29067f819ba69305f7ae8620729cd443915a0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69931941"
---
# <a name="icordebugeval-interface"></a>Interfaccia ICorDebugEval

Fornisce metodi per consentire al debugger di eseguire codice nel contesto del codice in fase di debug.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo Abort](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-abort-method.md)|Interrompe il calcolo attualmente effettuato `ICorDebugEval` da questo oggetto.|  
|[Metodo CallFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-callfunction-method.md)|Imposta una chiamata alla funzione specificata. (Obsoleto nella .NET Framework versione 2,0; utilizzare [ICorDebugEval2:: CallParameterizedFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-callparameterizedfunction-method.md) ).|  
|[Metodo CreateValue](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-createvalue-method.md)|Ottiene un puntatore a interfaccia a un oggetto "ICorDebugValue" del tipo specificato, con un valore iniziale pari a zero o null. (Obsoleto nella .NET Framework 2,0; utilizzare [ICorDebugEval2:: CreateValueForType](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-createvaluefortype-method.md) ).|  
|[Metodo GetResult](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-getresult-method.md)|Ottiene un puntatore a `ICorDebugValue` interfaccia che contiene i risultati della valutazione.|  
|[Metodo GetThread](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-getthread-method.md)|Ottiene un puntatore a interfaccia per il "ICorDebugThread" in cui è in esecuzione la valutazione o verrà eseguito.|  
|[Metodo IsActive](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-isactive-method.md)|Ottiene un valore che indica se l' `ICorDebugEval` oggetto è attualmente in esecuzione.|  
|[Metodo NewArray](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-newarray-method.md)|Alloca una nuova matrice del tipo e delle dimensioni dell'elemento specificato. (Obsoleto nella .NET Framework 2,0; utilizzare [ICorDebugEval2:: NewParameterizedArray](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedarray-method.md) ).|  
|[Metodo NewObject](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-newobject-method.md)|Alloca una nuova istanza dell'oggetto e chiama il metodo del costruttore specificato. (Obsoleto nella .NET Framework 2,0; utilizzare [ICorDebugEval2:: NewParameterizedObject](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobject-method.md) ).|  
|[Metodo NewObjectNoConstructor](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-newobjectnoconstructor-method.md)|Alloca una nuova istanza dell'oggetto del tipo specificato, senza tentare di chiamare un metodo del costruttore. (Obsoleto nella .NET Framework 2,0; utilizzare [ICorDebugEval2:: NewParameterizedObjectNoConstructor](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobjectnoconstructor-method.md) ).|  
|[Metodo NewString](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-newstring-method.md)|Alloca un nuovo oggetto stringa con il contenuto specificato.|  
  
## <a name="remarks"></a>Note  
 Un `ICorDebugEval` oggetto viene creato nel contesto di un thread specifico utilizzato per eseguire le valutazioni. Tutti gli oggetti e i tipi utilizzati in una determinata valutazione devono risiedere nello stesso dominio applicazione. Il dominio applicazione non deve corrispondere al dominio applicazione corrente del thread. Le valutazioni possono essere nidificate.  
  
 Le operazioni della valutazione non vengono completate fino a quando il debugger non chiama [ICorDebugController:: continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md), quindi riceve un callback [ICorDebugManagedCallback:: EvalComplete](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-evalcomplete-method.md) . Se è necessario usare la funzionalità di valutazione senza consentire l'esecuzione di altri thread, sospendere i thread usando [ICorDebugController:: SetAllThreadsDebugState](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-setallthreadsdebugstate-method.md) o [ICorDebugController:: Stop](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-stop-method.md) prima di chiamare [ ICorDebugController:: continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md).  
  
 Poiché il codice utente è in esecuzione quando è in corso la valutazione, è possibile che si verifichino eventi di debug, inclusi i carichi di classe e i punti di interruzione. Il debugger riceverà i callback, come di consueto, per questi eventi. Lo stato della valutazione verrà considerato come parte dell'ispezione del normale stato del programma. La catena di stack sarà una `CHAIN_FUNC_EVAL` catena (vedere l'enumerazione "CorDebugStepReason" e il metodo [ICorDebugChain:: GetReason](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getreason-method.md) ). L'API del debugger completa continuerà a funzionare normalmente.  
  
 Se si verifica una situazione di ciclo deadlock o infinito, il codice utente potrebbe non essere mai completato. In tal caso, è necessario chiamare [ICorDebugEval:: Abort](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-abort-method.md) prima di riprendere il programma.  
  
> [!NOTE]
> Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug. idl, CorDebug. h  
  
 **Libreria** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
