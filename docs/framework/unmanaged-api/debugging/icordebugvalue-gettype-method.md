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
ms.openlocfilehash: a3cd62384ad87d072cd715d23d0e9ee9dac23270
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396734"
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
  
## <a name="remarks"></a>Commenti  
 Se l'oggetto è un tipo di runtime complesso, il tipo può essere esaminato tramite le sottoclassi appropriate dell' `ICorDebugValue` interfaccia. Ad esempio, "ICorDebugObjectValue", che eredita da `ICorDebugValue` , rappresenta un tipo complesso.  
  
 I `GetType` metodi e [ICorDebugObjectValue:: GetClass](icordebugobjectvalue-getclass-method.md) restituiscono tutti informazioni sul tipo di un valore. Entrambi sono sostituiti dal metodo [ICorDebugValue2:: GetExactType](icordebugvalue2-getexacttype-method.md) in grado di riconoscere i generics.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
