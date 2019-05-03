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
ms.openlocfilehash: 444390622ca68244661b91dc85814b05556b12a2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61994318"
---
# <a name="icordebugstepperstep-method"></a>Metodo ICorDebugStepper::Step
Fa sì che questo ICorDebugStepper passo a passo del thread e, facoltativamente, per continuare il debug passo-passo tramite le funzioni che vengono chiamate all'interno del thread.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT Step (  
    [in] BOOL   bStepIn  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `bStepIn`  
 [in] Impostare su `true` al passaggio in una funzione che viene chiamata all'interno del thread. Impostare su `false` per Esegui istruzione/routine di funzione.  
  
## <a name="remarks"></a>Note  
 Il passaggio viene completato quando common language runtime esegue la successiva istruzione gestita nel frame del gestore di istruzioni. Se `Step` viene chiamato su un gestore, che non si trova in codice gestito, il passaggio verrà completata quando la successiva istruzione di codice gestito viene eseguita dal thread.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
