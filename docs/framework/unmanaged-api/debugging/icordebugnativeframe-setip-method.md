---
title: Metodo ICorDebugNativeFrame::SetIP
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.SetIP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::SetIP
helpviewer_keywords:
- ICorDebugNativeFrame::SetIP method [.NET Framework debugging]
- SetIP method, ICorDebugNativeFrame interface [.NET Framework debugging]
ms.assetid: 57784a51-c76d-48f8-9392-584d0e1946d9
topic_type:
- apiref
ms.openlocfilehash: bc33768e4155a0e272d3374d4c586c79ef2ff3fb
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792776"
---
# <a name="icordebugnativeframesetip-method"></a>Metodo ICorDebugNativeFrame::SetIP
Imposta il puntatore all'istruzione per la posizione di offset specificata nel codice nativo.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT SetIP (  
    [in] ULONG32 nOffset  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `nOffset`  
 in Posizione dell'offset nel codice nativo.  
  
## <a name="remarks"></a>Note  
 Le chiamate a `SetIP` invalidano immediatamente tutti i frame e le catene per il thread corrente. Se il debugger necessita di informazioni sul frame dopo una chiamata a `SetIP`, deve eseguire una nuova analisi dello stack.  
  
 [ICorDebug](icordebug-interface.md) tenterà di impedire la stack frame in uno stato valido. Tuttavia, anche se il frame è in uno stato valido, per quanto riguarda il runtime, è possibile che si verifichino problemi, ad esempio le variabili locali non inizializzate e così via. Il chiamante è responsabile dell'assicurazione del coerenza del programma in esecuzione.  
  
 Nelle piattaforme a 64 bit il puntatore all'istruzione non può essere spostato all'esterno di un blocco `catch` o `finally`. Se `SetIP` viene chiamato per eseguire tale spostamento su una piattaforma a 64 bit, viene restituito un valore HRESULT che indica un errore.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
