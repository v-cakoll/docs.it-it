---
title: Interfaccia ICorDebugStepper
ms.date: 03/30/2017
api_name:
- ICorDebugStepper
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper
helpviewer_keywords:
- ICorDebugStepper interface [.NET Framework debugging]
ms.assetid: ed8364eb-f01b-46f6-b5e3-5dda9cae2dfe
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1bd650178c787440941b9fd9a84b1e85c55aac61
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56973717"
---
# <a name="icordebugstepper-interface"></a>Interfaccia ICorDebugStepper
Rappresenta un'istruzione nell'esecuzione di codice da parte di un debugger, opera da identificatore tra l'invio e il completamento di un comando e consente di annullare un'istruzione.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo Deactivate](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-deactivate-method.md)|Fa in modo che questo `ICorDebugStepper` per annullare l'ultimo comando passaggio ha ricevuto.|  
|[Metodo IsActive](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-isactive-method.md)|Ottiene un valore che indica se questo `ICorDebugStepper` è in esecuzione un passaggio.|  
|[Metodo SetInterceptMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setinterceptmask-method.md)|Imposta un valore CorDebugIntercept che specifica i tipi di codice che viene eseguita l'istruzione.|  
|[Metodo SetRangeIL](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setrangeil-method.md)|Imposta un valore che indica se le chiamate a [StepRange](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md) passare i valori di argomento rispetto al codice nativo o per il codice Microsoft intermediate language (MSIL) del metodo che è in corso una alla volta.|  
|[Metodo SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md)|Imposta un valore CorDebugUnmappedStop che specifica il tipo di codice non mappato in cui verrà interrotta l'esecuzione.|  
|[Metodo Step](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-step-method.md)|Fa in modo che questo `ICorDebugStepper` passo a passo del thread e, facoltativamente, per continuare il debug passo-passo tramite le funzioni che vengono chiamate all'interno del thread.|  
|[Metodo StepOut](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-stepout-method.md)|Fa in modo che questo `ICorDebugStepper` passo a passo del thread di completata quando il frame corrente restituisce il controllo al chiama frame.|  
|[Metodo StepRange](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md)|Fa in modo che questo `ICorDebugStepper` passo a passo del thread e da restituire quando raggiunge il codice oltre l'ultimo degli intervalli specificati.|  
  
## <a name="remarks"></a>Note  
 Il `ICorDebugStepper` interfaccia ha gli scopi seguenti:  
  
-   Funge da identificatore tra un comando di passaggio che viene generato e il completamento del comando.  
  
-   Fornisce un'interfaccia centrale per incapsulare tutte le istruzioni che può essere eseguita.  
  
-   Fornisce un modo per annullare in modo anomalo un'operazione di debug passo a passo.  
  
 Può essere presente più di un gestore di istruzioni per ogni thread. Ad esempio, può essere raggiunto un punto di interruzione durante l'esecuzione di istruzioni/routine di una funzione e l'utente può essere utile avviare una nuova operazione di debug passo a passo all'interno della funzione. Spetta al debugger di determinare come gestire questa situazione. Il debugger potrebbe voler annullare l'operazione di debug passo a passo originale o annidare le due operazioni. Il `ICorDebugStepper` interfaccia supporta entrambe le opzioni.  
  
 Un gestore di istruzioni possono eseguire la migrazione tra i thread se common language runtime (CLR) effettua una chiamata di cross-thread sottoposta a marshalling.  
  
> [!NOTE]
>  Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
