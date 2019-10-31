---
title: Metodo ICorDebugStepper::StepRange
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.StepRange
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::StepRange
helpviewer_keywords:
- StepRange method [.NET Framework debugging]
- ICorDebugStepper::StepRange method [.NET Framework debugging]
ms.assetid: b9776112-6e6d-4708-892a-8873db02e16f
topic_type:
- apiref
ms.openlocfilehash: 2ca4542fe42fab0b5ff54b23b9492d3906698c10
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120627"
---
# <a name="icordebugsteppersteprange-method"></a>Metodo ICorDebugStepper::StepRange
Fa in modo che questo ICorDebugStepper a un singolo passaggio tramite il thread contenitore e restituisca quando raggiunge il codice oltre l'ultimo intervallo specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT StepRange (  
    [in] BOOL     bStepIn,  
    [in, size_is(cRangeCount)] COR_DEBUG_STEP_RANGE ranges[],  
    [in] ULONG32  cRangeCount  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `bStepIn`  
 in Impostare su `true` per eseguire un'istruzione in una funzione chiamata all'interno del thread. Impostare su `false` per eseguire un'istruzione/routine della funzione.  
  
 `ranges`  
 in Matrice di strutture COR_DEBUG_STEP_RANGE, ognuna delle quali specifica un intervallo.  
  
 `cRangeCount`  
 [in] Dimensione della matrice `ranges`.  
  
## <a name="remarks"></a>Note  
 Il metodo `StepRange` funziona come il metodo [ICorDebugStepper:: Step](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-step-method.md) , ad eccezione del fatto che non viene completato finché non viene raggiunto il codice non compreso nell'intervallo specificato.  
  
 Questa operazione può essere più efficiente rispetto all'esecuzione di un'istruzione alla volta. Gli intervalli vengono specificati come un elenco di coppie di offset dall'inizio del frame del stepper.  
  
 Gli intervalli sono relativi al codice MSIL (Microsoft Intermediate Language) di un metodo. Chiamare [ICorDebugStepper:: SetRangeIL](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setrangeil-method.md) con `false` per rendere gli intervalli relativi al codice nativo di un metodo.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
