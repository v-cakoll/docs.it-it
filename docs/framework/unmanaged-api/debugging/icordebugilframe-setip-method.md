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
ms.openlocfilehash: 60273d7cf91be04c5fc3041260e4bb146ce9a45e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73095423"
---
# <a name="icordebugilframesetip-method"></a>Metodo ICorDebugILFrame::SetIP
Imposta il puntatore all'istruzione nella posizione di offset specificata nel codice MSIL (Microsoft Intermediate Language).  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT SetIP (  
    [in] ULONG32 nOffset  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `nOffset`  
 Posizione dell'offset nel codice MSIL.  
  
## <a name="remarks"></a>Note  
 Le chiamate a `SetIP` invalidano immediatamente tutti i frame e le catene per il thread corrente. Se il debugger necessita di informazioni sul frame dopo una chiamata a `SetIP`, deve eseguire una nuova analisi dello stack.  
  
 [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) tenterà di impedire la stack frame in uno stato valido. Tuttavia, anche se il frame è in uno stato valido, potrebbero essere presenti problemi come le variabili locali non inizializzate. Il chiamante è responsabile di garantire l'coerenza del programma in esecuzione.  
  
 Nelle piattaforme a 64 bit il puntatore all'istruzione non può essere spostato all'esterno di un blocco `catch` o `finally`. Se `SetIP` viene chiamato per eseguire tale spostamento su una piattaforma a 64 bit, viene restituito un valore HRESULT che indica un errore.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
