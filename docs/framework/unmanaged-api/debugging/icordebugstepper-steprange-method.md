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
ms.openlocfilehash: b040d9454a5a3a0d550bb645953c783357419f73
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379486"
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
 in Impostare su `true` per eseguire un'istruzione in una funzione chiamata all'interno del thread. Impostare su `false` per eseguire l'istruzione/routine della funzione.  
  
 `ranges`  
 in Matrice di strutture di COR_DEBUG_STEP_RANGE, ognuna delle quali specifica un intervallo.  
  
 `cRangeCount`  
 [in] Dimensione della matrice `ranges`.  
  
## <a name="remarks"></a>Osservazioni  
 Il `StepRange` metodo funziona come il metodo [ICorDebugStepper:: Step](icordebugstepper-step-method.md) , ad eccezione del fatto che non viene completato fino a quando non viene raggiunto il codice non compreso nell'intervallo specificato.  
  
 Questa operazione può essere più efficiente rispetto all'esecuzione di un'istruzione alla volta. Gli intervalli vengono specificati come un elenco di coppie di offset dall'inizio del frame del stepper.  
  
 Gli intervalli sono relativi al codice MSIL (Microsoft Intermediate Language) di un metodo. Chiamare [ICorDebugStepper:: SetRangeIL](icordebugstepper-setrangeil-method.md) con `false` per rendere gli intervalli relativi al codice nativo di un metodo.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
