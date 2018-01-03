---
title: ICorDebugStepper Interface1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugStepper
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugStepper
helpviewer_keywords: ICorDebugStepper interface [.NET Framework debugging]
ms.assetid: ed8364eb-f01b-46f6-b5e3-5dda9cae2dfe
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 266e8c664ac7c5efa1b199efc522f0b890e38e3a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugstepper-interface1"></a>ICorDebugStepper Interface1
Rappresenta un'istruzione nell'esecuzione di codice da parte di un debugger, opera da identificatore tra l'invio e il completamento di un comando e consente di annullare un'istruzione.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo Deactivate](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-deactivate-method.md)|Fa sì che `ICorDebugStepper` per annullare l'ultimo comando passaggio ricevuto.|  
|[Metodo IsActive](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-isactive-method.md)|Ottiene un valore che indica se questo `ICorDebugStepper` è in esecuzione un passaggio.|  
|[Metodo SetInterceptMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setinterceptmask-method.md)|Imposta un valore CorDebugIntercept che specifica i tipi di codice che viene eseguito l'accesso.|  
|[Metodo SetRangeIL](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setrangeil-method.md)|Imposta un valore che indica se le chiamate a [ICorDebugStepper:: StepRange](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md) passare i valori di argomento rispetto al codice nativo o codice di Microsoft intermediate language (MSIL) del metodo che viene eseguito il debug passo a tramite.|  
|[Metodo SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md)|Imposta un valore CorDebugUnmappedStop che specifica il tipo di codice non mappato in cui verrà interrotta l'esecuzione.|  
|[Metodo Step](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-step-method.md)|Fa sì che `ICorDebugStepper` passo a passo del thread e, facoltativamente, per continuare l'esecuzione passo passo tramite le funzioni che vengono chiamate all'interno del thread.|  
|[Metodo StepOut](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-stepout-method.md)|Fa sì che `ICorDebugStepper` passo a passo del thread e venga completato quando il frame corrente restituisce il controllo al frame chiamante.|  
|[Metodo StepRange](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md)|Fa sì che `ICorDebugStepper` passo a passo del thread e da restituire quando raggiunge il codice oltre l'ultimo degli intervalli specificati.|  
  
## <a name="remarks"></a>Note  
 Il `ICorDebugStepper` interfaccia utilizza per gli scopi seguenti:  
  
-   Funge da identificatore tra un comando del passaggio che viene eseguito e il completamento del comando.  
  
-   Fornisce un'interfaccia centrale per incapsulare tutti l'esecuzione di istruzioni che può essere eseguita.  
  
-   Fornisce un modo per annullare in modo anomalo di un'operazione passo a passo.  
  
 Può essere presente più di un gestore di istruzioni per ogni thread. Ad esempio, può essere raggiunto un punto di interruzione durante l'esecuzione su una funzione e l'utente potrebbe desiderare di avviare una nuova operazione passo a passo all'interno di tale funzione. In questo caso, il debugger per determinare come gestire questa situazione. Il debugger possibile annullare l'operazione passo a passo originale o annidare entrambe le operazioni. Il `ICorDebugStepper` interfaccia supporta entrambe le opzioni.  
  
 Un gestore di istruzioni possono essere migrate tra thread se common language runtime (CLR) effettua una chiamata cross-thread sottoposta a marshalling.  
  
> [!NOTE]
>  Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
