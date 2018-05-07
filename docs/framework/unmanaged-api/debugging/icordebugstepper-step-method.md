---
title: Metodo ICorDebugStepper::Step
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.Step
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::Step
helpviewer_keywords:
- Step method, ICorDebugStepper interface [.NET Framework debugging]
- ICorDebugStepper::Step method [.NET Framework debugging]
ms.assetid: 38c1940b-ada1-40ba-8295-4c0833744e1e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c2d282e27ec5068fa6fe7f58ba95458fdc219972
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugstepperstep-method"></a>Metodo ICorDebugStepper::Step
Fa sì che ICorDebugStepper passo a passo del thread e, facoltativamente, per continuare l'esecuzione passo passo tramite le funzioni che vengono chiamate all'interno del thread.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT Step (  
    [in] BOOL   bStepIn  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `bStepIn`  
 [in] Impostare su `true` al passaggio a una funzione che viene chiamata all'interno del thread. Impostare su `false` per Esegui istruzione/routine di funzione.  
  
## <a name="remarks"></a>Note  
 Il passaggio viene completato quando common language runtime esegue la successiva istruzione gestita nel frame del gestore di istruzioni. Se `Step` viene chiamato su un gestore, che non è in codice gestito, il passaggio verrà completata quando la successiva istruzione di codice gestito viene eseguita dal thread.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cordebug. idl, Cordebug. H  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
