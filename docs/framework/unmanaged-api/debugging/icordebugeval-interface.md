---
title: ICorDebugEval Interface1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugEval
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugEval
helpviewer_keywords: ICorDebugEval interface [.NET Framework debugging]
ms.assetid: 3a5c9815-832d-47e1-b7f7-bbba135d7cf1
topic_type: apiref
caps.latest.revision: "17"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 57b285ef5b2d3f8342b473f09650e6db7ec1693d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugeval-interface1"></a>ICorDebugEval Interface1
Fornisce metodi per consentire al debugger di eseguire codice nel contesto del codice in fase di debug.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Abort (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-abort-method.md)|Interrompe il calcolo `ICorDebugEval` attualmente eseguito dall'oggetto.|  
|[CallFunction (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-callfunction-method.md)|Imposta una chiamata alla funzione specificata. (Obsoleto in .NET Framework versione 2.0 [ICorDebugEval2:: CallParameterizedFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-callparameterizedfunction-method.md) invece.)|  
|[CreateValue (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-createvalue-method.md)|Ottiene un puntatore a interfaccia a un oggetto "ICorDebugValue" del tipo specificato, con un valore iniziale pari a zero o null. (Obsoleto in .NET Framework 2.0 [ICorDebugEval2:: CreateValueForType](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-createvaluefortype-method.md) invece.)|  
|[GetResult (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-getresult-method.md)|Ottiene un puntatore a interfaccia a un `ICorDebugValue` che contiene i risultati della valutazione.|  
|[GetThread (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-getthread-method.md)|Ottiene un puntatore a interfaccia a "ICorDebugThread" in cui questa valutazione è in esecuzione o verrà eseguito.|  
|[IsActive (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-isactive-method.md)|Ottiene un valore che indica se questo `ICorDebugEval` oggetto è attualmente in esecuzione.|  
|[NewArray (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-newarray-method.md)|Alloca una nuova matrice del tipo di elemento specificato e le dimensioni. (Obsoleto in .NET Framework 2.0 [ICorDebugEval2::](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedarray-method.md) invece.)|  
|[NewObject (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-newobject-method.md)|Alloca una nuova istanza dell'oggetto e chiama il metodo costruttore specificato. (Obsoleto in .NET Framework 2.0 [ICorDebugEval2::](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobject-method.md) invece.)|  
|[NewObjectNoConstructor (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-newobjectnoconstructor-method.md)|Alloca una nuova istanza dell'oggetto del tipo specificato, senza tentare di chiamare un metodo del costruttore. (Obsoleto in .NET Framework 2.0 [ICorDebugEval2:: NewParameterizedObjectNoConstructor](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobjectnoconstructor-method.md) invece.)|  
|[NewString (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-newstring-method.md)|Alloca un nuovo oggetto stringa con il contenuto specificato.|  
  
## <a name="remarks"></a>Note  
 Un `ICorDebugEval` oggetto viene creato nel contesto di un thread specifico utilizzato per eseguire le valutazioni. Tutti gli oggetti e i tipi utilizzati in una determinata valutazione devono risiedere all'interno dello stesso dominio applicazione. Dominio dell'applicazione devono essere lo stesso come il dominio applicazione corrente del thread. Valutazioni possono essere nidificate.  
  
 Le operazioni della valutazione non vengono completano fino a quando il debugger chiama [ICorDebugController:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md)e riceve un [ICorDebugManagedCallback:: EvalComplete](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-evalcomplete-method.md) callback. Se è necessario utilizzare la funzionalità di valutazione senza consentire l'esecuzione di altri thread, sospendere i thread tramite [ICorDebugController:: SetAllThreadsDebugState](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-setallthreadsdebugstate-method.md) o [ICorDebugController:: Stop](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-stop-method.md)prima di chiamare [ICorDebugController:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md).  
  
 Poiché il codice utente è in esecuzione quando la valutazione è in corso, possono verificarsi tutti gli eventi di debug, inclusi caricamenti di classi e i punti di interruzione. Il debugger riceverà i callback, come di consueto, per questi eventi. Lo stato della valutazione sarà presenti come parte di un controllo dello stato del programma normale. La catena dello stack sarà un `CHAIN_FUNC_EVAL` catena (vedere l'enumerazione "CorDebugStepReason" e [ICorDebugChain:: GetReason](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getreason-method.md) (metodo)). Il debugger completo API continuerà a funzionare normalmente.  
  
 Se si verifica una situazione di ciclo di deadlock o infinita, il codice utente potrebbe non essere completata. In tal caso, è necessario chiamare [ICorDebugEval:: Abort](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-abort-method.md) prima di riprendere il programma.  
  
> [!NOTE]
>  Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
    
    
    
 [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
