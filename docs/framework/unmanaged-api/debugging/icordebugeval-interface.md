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
ms.openlocfilehash: c9e2dc95bf78d95e5d608a8ce6e9462345c20a07
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788738"
---
# <a name="icordebugeval-interface"></a>Interfaccia ICorDebugEval

Fornisce metodi per consentire al debugger di eseguire codice nel contesto del codice in fase di debug.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo Abort](icordebugeval-abort-method.md)|Interrompe il calcolo che questo `ICorDebugEval` oggetto sta attualmente eseguendo.|  
|[Metodo CallFunction](icordebugeval-callfunction-method.md)|Imposta una chiamata alla funzione specificata. (Obsoleto nella .NET Framework versione 2,0; utilizzare [ICorDebugEval2:: CallParameterizedFunction](icordebugeval2-callparameterizedfunction-method.md) ).|  
|[Metodo CreateValue](icordebugeval-createvalue-method.md)|Ottiene un puntatore a interfaccia a un oggetto "ICorDebugValue" del tipo specificato, con un valore iniziale pari a zero o null. (Obsoleto nella .NET Framework 2,0; utilizzare [ICorDebugEval2:: CreateValueForType](icordebugeval2-createvaluefortype-method.md) ).|  
|[Metodo GetResult](icordebugeval-getresult-method.md)|Ottiene un puntatore a interfaccia a un `ICorDebugValue` contenente i risultati della valutazione.|  
|[Metodo GetThread](icordebugeval-getthread-method.md)|Ottiene un puntatore a interfaccia per il "ICorDebugThread" in cui è in esecuzione la valutazione o verrà eseguito.|  
|[Metodo IsActive](icordebugeval-isactive-method.md)|Ottiene un valore che indica se l'oggetto `ICorDebugEval` è attualmente in esecuzione.|  
|[Metodo NewArray](icordebugeval-newarray-method.md)|Alloca una nuova matrice del tipo e delle dimensioni dell'elemento specificato. (Obsoleto nella .NET Framework 2,0; utilizzare [ICorDebugEval2:: NewParameterizedArray](icordebugeval2-newparameterizedarray-method.md) ).|  
|[Metodo NewObject](icordebugeval-newobject-method.md)|Alloca una nuova istanza dell'oggetto e chiama il metodo del costruttore specificato. (Obsoleto nella .NET Framework 2,0; utilizzare [ICorDebugEval2:: NewParameterizedObject](icordebugeval2-newparameterizedobject-method.md) ).|  
|[Metodo NewObjectNoConstructor](icordebugeval-newobjectnoconstructor-method.md)|Alloca una nuova istanza dell'oggetto del tipo specificato, senza tentare di chiamare un metodo del costruttore. (Obsoleto nella .NET Framework 2,0; utilizzare [ICorDebugEval2:: NewParameterizedObjectNoConstructor](icordebugeval2-newparameterizedobjectnoconstructor-method.md) ).|  
|[Metodo NewString](icordebugeval-newstring-method.md)|Alloca un nuovo oggetto stringa con il contenuto specificato.|  
  
## <a name="remarks"></a>Note  
 Un oggetto `ICorDebugEval` viene creato nel contesto di un thread specifico utilizzato per eseguire le valutazioni. Tutti gli oggetti e i tipi utilizzati in una determinata valutazione devono risiedere nello stesso dominio applicazione. Il dominio applicazione non deve corrispondere al dominio applicazione corrente del thread. Le valutazioni possono essere nidificate.  
  
 Le operazioni della valutazione non vengono completate fino a quando il debugger non chiama [ICorDebugController:: continue](icordebugcontroller-continue-method.md), quindi riceve un callback [ICorDebugManagedCallback:: EvalComplete](icordebugmanagedcallback-evalcomplete-method.md) . Se è necessario usare la funzionalità di valutazione senza consentire l'esecuzione di altri thread, sospendere i thread usando [ICorDebugController:: SetAllThreadsDebugState](icordebugcontroller-setallthreadsdebugstate-method.md) o [ICorDebugController:: Stop](icordebugcontroller-stop-method.md) prima di chiamare [ICorDebugController:: continue](icordebugcontroller-continue-method.md).  
  
 Poiché il codice utente è in esecuzione quando è in corso la valutazione, è possibile che si verifichino eventi di debug, inclusi i carichi di classe e i punti di interruzione. Il debugger riceverà i callback, come di consueto, per questi eventi. Lo stato della valutazione verrà considerato come parte dell'ispezione del normale stato del programma. La catena di stack sarà una catena di `CHAIN_FUNC_EVAL` (vedere l'enumerazione "CorDebugStepReason" e il metodo [ICorDebugChain:: GetReason](icordebugchain-getreason-method.md) ). L'API del debugger completa continuerà a funzionare normalmente.  
  
 Se si verifica una situazione di ciclo deadlock o infinito, il codice utente potrebbe non essere mai completato. In tal caso, è necessario chiamare [ICorDebugEval:: Abort](icordebugeval-abort-method.md) prima di riprendere il programma.  
  
> [!NOTE]
> Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di debug](debugging-interfaces.md)
