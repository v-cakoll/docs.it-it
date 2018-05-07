---
title: Metodo ICorDebugILFrame::SetIP
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame.SetIP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::SetIP
helpviewer_keywords:
- SetIP method, ICorDebugILFrame interface [.NET Framework debugging]
- ICorDebugILFrame::SetIP method [.NET Framework debugging]
ms.assetid: 23f38dc1-85e4-4263-9235-2d05bbb6a833
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ed7de70c8ea26f46f44abb3e063c6e4c4b115666
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugilframesetip-method"></a>Metodo ICorDebugILFrame::SetIP
Imposta il puntatore all'istruzione alla posizione di offset specificata nel codice Microsoft intermediate language (MSIL).  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT SetIP (  
    [in] ULONG32 nOffset  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `nOffset`  
 Posizione di offset nel codice MSIL.  
  
## <a name="remarks"></a>Note  
 Le chiamate a `SetIP` invalidano immediatamente tutti i frame e sulle sequenze per il thread corrente. Se il debugger deve ottenere informazioni sui frame dopo una chiamata a `SetIP`, è necessario eseguire una nuova traccia dello stack.  
  
 [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) proverà a mantenere lo stack frame in uno stato valido. Tuttavia, anche se il frame è in uno stato valido, è comunque possibile problemi come variabili locali non inizializzate. Il chiamante è responsabile di garantire la coerenza del programma in esecuzione.  
  
 Su piattaforme a 64 bit, il puntatore all'istruzione non può essere spostato fuori da un `catch` o `finally` blocco. Se `SetIP` viene chiamato per rendere un tale spostamento su una piattaforma a 64 bit, verrà restituito un HRESULT che indica un errore.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cordebug. idl, Cordebug. H  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
