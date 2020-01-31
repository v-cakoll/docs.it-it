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
ms.openlocfilehash: e9bb69567a247472af42efb08b609d3474c87ed2
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791788"
---
# <a name="icordebugstepper-interface"></a>Interfaccia ICorDebugStepper
Rappresenta un'istruzione nell'esecuzione di codice da parte di un debugger, opera da identificatore tra l'invio e il completamento di un comando e consente di annullare un'istruzione.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo Deactivate](icordebugstepper-deactivate-method.md)|Fa in modo che questo `ICorDebugStepper` cancelli il comando dell'ultimo passaggio ricevuto.|  
|[Metodo IsActive](icordebugstepper-isactive-method.md)|Ottiene un valore che indica se questo `ICorDebugStepper` sta attualmente eseguendo un passaggio.|  
|[Metodo SetInterceptMask](icordebugstepper-setinterceptmask-method.md)|Imposta un valore CorDebugIntercept che specifica i tipi di codice sottoposti a rientri.|  
|[Metodo SetRangeIL](icordebugstepper-setrangeil-method.md)|Imposta un valore che indica se le chiamate a [ICorDebugStepper:: StepRange](icordebugstepper-steprange-method.md) passano valori di argomento relativi al codice nativo o al codice MSIL (Microsoft Intermediate Language) del metodo di cui è in corso il passaggio.|  
|[Metodo SetUnmappedStopMask](icordebugstepper-setunmappedstopmask-method.md)|Imposta un valore CorDebugUnmappedStop che specifica il tipo di codice non mappato in cui l'esecuzione si arresterà.|  
|[Metodo Step](icordebugstepper-step-method.md)|Fa in modo che questo `ICorDebugStepper` in un unico passaggio attraverso il thread contenitore e, facoltativamente, per continuare a eseguire l'istruzione singola con le funzioni che vengono chiamate all'interno del thread.|  
|[Metodo StepOut](icordebugstepper-stepout-method.md)|Fa in modo che questo `ICorDebugStepper` a un singolo passaggio attraverso il thread che lo contiene e venga completato quando il frame corrente restituisce il controllo al frame chiamante.|  
|[Metodo StepRange](icordebugstepper-steprange-method.md)|Fa in modo che questo `ICorDebugStepper` a un singolo passaggio tramite il thread contenitore e restituisca quando raggiunge il codice oltre l'ultimo intervallo specificato.|  
  
## <a name="remarks"></a>Note  
 L'interfaccia `ICorDebugStepper` offre gli scopi seguenti:  
  
- Funge da identificatore tra un comando Step emesso e il completamento del comando.  
  
- Fornisce un'interfaccia centrale per incapsulare tutti gli avanzamenti che possono essere eseguiti.  
  
- Consente di annullare in modo anomalo un'operazione di esecuzione.  
  
 Possono essere presenti più stepper per thread. Ad esempio, un punto di interruzione può essere raggiunto durante l'esecuzione di un'istruzione/routine di una funzione e l'utente può voler avviare una nuova operazione di esecuzione all'interno di tale funzione. Spetta al debugger determinare come gestire questa situazione. È possibile che il debugger desideri annullare l'operazione di avanzamento originale o annidare le due operazioni. L'interfaccia `ICorDebugStepper` supporta entrambe le opzioni.  
  
 Uno stepper può eseguire la migrazione tra thread se il Common Language Runtime (CLR) esegue una chiamata con marshalling cross-threading.  
  
> [!NOTE]
> Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di debug](debugging-interfaces.md)
