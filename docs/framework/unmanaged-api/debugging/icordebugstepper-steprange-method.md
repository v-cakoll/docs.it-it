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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 838f2df06f8875037edbe39d2db0411f31abe01f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugsteppersteprange-method"></a>Metodo ICorDebugStepper::StepRange
Fa sì che ICorDebugStepper passo a passo del thread e da restituire quando raggiunge il codice oltre l'ultimo degli intervalli specificati.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT StepRange (  
    [in] BOOL     bStepIn,  
    [in, size_is(cRangeCount)] COR_DEBUG_STEP_RANGE ranges[],  
    [in] ULONG32  cRangeCount  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `bStepIn`  
 [in] Impostare su `true` al passaggio a una funzione che viene chiamata all'interno del thread. Impostare su `false` per Esegui istruzione/routine di funzione.  
  
 `ranges`  
 [in] Matrice di strutture COR_DEBUG_STEP_RANGE, ognuno dei quali specifica un intervallo.  
  
 `cRangeCount`  
 [in] Dimensione della matrice `ranges`.  
  
## <a name="remarks"></a>Note  
 Il `StepRange` metodo opera come il [ICorDebugStepper:: Step](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-step-method.md) metodo, ad eccezione del fatto che non viene completata fino al codice di fuori dell'intervallo specificato viene raggiunto.  
  
 Può essere più efficiente rispetto al debug di un'istruzione alla volta. Gli intervalli vengono specificati come elenco di coppie di offset dall'inizio del frame del gestore di istruzioni.  
  
 Gli intervalli sono relativi al codice Microsoft intermediate language (MSIL) di un metodo. Chiamare [ICorDebugStepper:: SetRangeIL](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setrangeil-method.md) con `false` per rendere gli intervalli relativi al codice nativo di un metodo.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cordebug. idl, Cordebug. H  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
