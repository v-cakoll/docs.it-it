---
title: Metodo ICorDebugExceptionObjectValue::EnumerateExceptionCallStack
ms.date: 03/30/2017
api_name:
- ICorDebugExceptionObjectValue.EnumerateExceptionCallStack
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugExceptionObjectValue::EnumerateExceptionCallStack
helpviewer_keywords:
- EnumerateExceptionCallStack method, ICorDebugExceptionObjectValue interface [.NET Framework debugging]
- ICorDebugExceptionObjectValue::EnumerateExceptionCallStack method [.NET Framework debugging]
ms.assetid: 00c64533-15dd-47f4-bb97-fe80a1ebadef
topic_type:
- apiref
ms.openlocfilehash: e45b180ac6d943d89740ad7ae10500ea4ad1aa9c
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/08/2020
ms.locfileid: "82975966"
---
# <a name="icordebugexceptionobjectvalueenumerateexceptioncallstack-method"></a>Metodo ICorDebugExceptionObjectValue::EnumerateExceptionCallStack
Ottiene un enumeratore per lo stack di chiamate incorporato in un oggetto eccezione.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT EnumerateExceptionCallStack(  
    [out] ICorDebugExceptionObjectCallStackEnum **ppCallStackEnum  
);  
```  
  
## <a name="parameters"></a>Parametri  
 ppCallStackEnum  
 out Puntatore all'indirizzo di un oggetto interfaccia [ICorDebugExceptionObjectCallStackEnum](icordebugexceptionobjectcallstackenum-interface.md) che è un enumeratore di analisi dello stack per un oggetto eccezione gestita.  
  
## <a name="remarks"></a>Osservazioni  
 Se non sono disponibili informazioni sullo stack di chiamate, il `S_OK`metodo restituisce e [ICorDebugExceptionObjectCallStackEnum](icordebugexceptionobjectcallstackenum-interface.md) è un enumeratore valido con lunghezza pari a 0. Se il metodo non è in grado di recuperare informazioni sulla traccia dello stack, `E_FAIL` il valore restituito è e non viene restituito alcun enumeratore.  
  
 L'oggetto [ICorDebugExceptionObjectCallStackEnum](icordebugexceptionobjectcallstackenum-interface.md) è responsabile della decodifica dei dati di traccia dello stack dal `_stackTrace` campo dell'oggetto eccezione.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugExceptionObjectValue](icordebugexceptionobjectvalue-interface.md)
- [Interfacce di debug](debugging-interfaces.md)
