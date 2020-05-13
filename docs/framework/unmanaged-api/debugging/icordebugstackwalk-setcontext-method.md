---
title: Metodo ICorDebugStackWalk::SetContext
ms.date: 03/30/2017
api_name:
- ICorDebugStackWalk.SetContext Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStackWalk::SetContext
helpviewer_keywords:
- SetContext method [.NET Framework debugging]
- ICorDebugStackWalk::SetContext method [.NET Framework debugging]
ms.assetid: bac0b156-31a3-4e7f-be4d-ab21789c81f1
topic_type:
- apiref
ms.openlocfilehash: 896e797acc76e8d8034bd964e488317a62eed97b
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378770"
---
# <a name="icordebugstackwalksetcontext-method"></a>Metodo ICorDebugStackWalk::SetContext
Imposta il contesto corrente dell'oggetto [ICorDebugStackWalk](icordebugstackwalk-interface.md) su un contesto valido per il thread.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT SetContext([in] CorDebugSetContextFlag flag,  
                   [in] ULONG32 contextSize,  
                   [in, size_is(contextSize)] BYTE context[]);  
```  
  
## <a name="parameters"></a>Parametri  
 `flag`  
 in Flag [CorDebugSetContextFlag](cordebugsetcontextflag-enumeration.md) che indica se il contesto è del frame attivo nello stack o un contesto ottenuto tramite la rimozione dello stack.  
  
 `contextSize`  
 in Dimensione allocata del `CONTEXT` buffer.  
  
 `context`  
 in `CONTEXT`Buffer.  
  
## <a name="return-value"></a>Valore restituito  
 Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.  
  
|HRESULT|Description|  
|-------------|-----------------|  
|S_OK|Il `ICorDebugStackWalk` contesto dell'oggetto è stato impostato correttamente.|  
|E_FAIL|Il `ICorDebugStackWalk` contesto dell'oggetto non è stato impostato.|  
|E_INVALIDARG|Il contesto è null.|  
|HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)|Il buffer del contesto è troppo piccolo.|  
  
## <a name="exceptions"></a>Eccezioni  
  
## <a name="remarks"></a>Osservazioni  
 Questo metodo non modifica il contesto corrente del thread.  
  
 L'impostazione del contesto corrente su un contesto non valido può causare risultati imprevedibili dal camminatore dello stack.  
  
 È possibile recuperare un'esatta copia bit per bit di questo contesto chiamando immediatamente il metodo [ICorDebugStackWalk:: GetContext](icordebugstackwalk-getcontext-method.md) .  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di debug](debugging-interfaces.md)
- [Debug](index.md)
