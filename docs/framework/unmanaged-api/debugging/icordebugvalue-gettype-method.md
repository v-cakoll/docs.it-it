---
title: Metodo ICorDebugValue::GetType
ms.date: 03/30/2017
api_name:
- ICorDebugValue.GetType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue::GetType
helpviewer_keywords:
- ICorDebugValue::GetType method [.NET Framework debugging]
- GetType method, ICorDebugValue interface [.NET Framework debugging]
ms.assetid: 41e2d503-e1f1-407b-abe0-6a29adb3e0d1
topic_type:
- apiref
ms.openlocfilehash: 7def2bd2c0f3ab501fdb918a0e9a7ee154159b78
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791148"
---
# <a name="icordebugvaluegettype-method"></a>Metodo ICorDebugValue::GetType
Ottiene il tipo primitivo di questo oggetto "ICorDebugValue".  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetType (  
    [out] CorElementType   *pType  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pType`  
 out Puntatore a un valore dell'enumerazione "CorElementType" che indica il tipo del valore.  
  
## <a name="remarks"></a>Note  
 Se l'oggetto è un tipo di runtime complesso, il tipo può essere esaminato tramite le sottoclassi appropriate dell'interfaccia `ICorDebugValue`. Ad esempio, "ICorDebugObjectValue", che eredita da `ICorDebugValue`, rappresenta un tipo complesso.  
  
 I metodi `GetType` e [ICorDebugObjectValue:: GetClass](icordebugobjectvalue-getclass-method.md) restituiscono informazioni sul tipo di un valore. Entrambi sono sostituiti dal metodo [ICorDebugValue2:: GetExactType](icordebugvalue2-getexacttype-method.md) in grado di riconoscere i generics.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
