---
title: Interfaccia1 ICorDebugEval
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
ms.openlocfilehash: 6da68bc4218d59320997a341f8c4a860201ba643
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54620331"
---
# <a name="icordebugeval-interface1"></a>Interfaccia1 ICorDebugEval
Fornisce metodi per consentire al debugger di eseguire codice nel contesto del codice in fase di debug.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo Abort](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-abort-method.md)|Interrompe il calcolo `ICorDebugEval` oggetto è attualmente in corso.|  
|[Metodo CallFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-callfunction-method.md)|Imposta una chiamata alla funzione specificata. (Obsoleto in .NET Framework versione 2.0 [ICorDebugEval2::CallParameterizedFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-callparameterizedfunction-method.md) invece.)|  
|[Metodo CreateValue](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-createvalue-method.md)|Ottiene un puntatore a interfaccia a un oggetto "ICorDebugValue" del tipo specificato, con un valore iniziale pari a zero o null. (Obsoleto in .NET Framework 2.0 [ICorDebugEval2::CreateValueForType](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-createvaluefortype-method.md) invece.)|  
|[Metodo GetResult](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-getresult-method.md)|Ottiene un puntatore a interfaccia per un `ICorDebugValue` che contiene i risultati della valutazione.|  
|[Metodo GetThread](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-getthread-method.md)|Ottiene un puntatore a interfaccia a "ICorDebugThread" in questa versione di valutazione è in esecuzione o verrà eseguita.|  
|[Metodo IsActive](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-isactive-method.md)|Ottiene un valore che indica se questo `ICorDebugEval` oggetto è attualmente in esecuzione.|  
|[Metodo NewArray](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-newarray-method.md)|Consente di allocare una nuova matrice del tipo di elemento specificato e le dimensioni. (Obsoleto in .NET Framework 2.0 [ICorDebugEval2::NewParameterizedArray](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedarray-method.md) invece.)|  
|[Metodo NewObject](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-newobject-method.md)|Consente di allocare una nuova istanza dell'oggetto e chiama il metodo costruttore specificato. (Obsoleto in .NET Framework 2.0 [ICorDebugEval2::NewParameterizedObject](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobject-method.md) invece.)|  
|[Metodo NewObjectNoConstructor](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-newobjectnoconstructor-method.md)|Consente di allocare una nuova istanza dell'oggetto del tipo specificato, senza effettuare alcun tentativo di chiamare un metodo del costruttore. (Obsoleto in .NET Framework 2.0 [ICorDebugEval2::NewParameterizedObjectNoConstructor](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobjectnoconstructor-method.md) invece.)|  
|[Metodo NewString](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-newstring-method.md)|Alloca un nuovo oggetto stringa con il contenuto specificato.|  
  
## <a name="remarks"></a>Note  
 Un `ICorDebugEval` oggetto viene creato nel contesto di un thread specifico utilizzato per eseguire le valutazioni. Tutti gli oggetti e i tipi usati in una determinata valutazione devono risiedere nello stesso dominio applicazione. Dominio dell'applicazione non è necessario lo stesso come il dominio applicazione corrente del thread. Le versioni di valutazione possono essere annidate.  
  
 Le operazioni della valutazione non vengono completate fino a quando il debugger chiama [ICorDebugController](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md)e quindi riceve un [EvalComplete](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-evalcomplete-method.md) callback. Se è necessario usare la funzionalità di valutazione senza consentire l'esecuzione di altri thread, sospendere i thread utilizzando [SetAllThreadsDebugState](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-setallthreadsdebugstate-method.md) o [ICorDebugController](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-stop-method.md)prima di chiamare [ICorDebugController](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md).  
  
 Poiché il codice utente è in esecuzione quando la versione di valutazione è in corso, possono verificarsi tutti gli eventi di debug, inclusi carichi di classe e i punti di interruzione. Il debugger riceveranno i callback, come di consueto, per questi eventi. Lo stato della valutazione sarà visibile come parte di un controllo dello stato del programma normale. La catena dello stack sarà un `CHAIN_FUNC_EVAL` catena (vedere l'enumerazione "CorDebugStepReason" e il [ICorDebugChain:: GetReason](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getreason-method.md) (metodo)). Il debugger completo API continuerà a funzionare come di consueto.  
  
 Se si verifica una situazione di ciclo in deadlock o infinita, il codice utente non venga mai completata. In tal caso, è necessario chiamare [ICorDebugEval](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-abort-method.md) prima di riprendere il programma.  
  
> [!NOTE]
>  Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche



- [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
