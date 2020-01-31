---
title: Metodo ICorDebugObjectValue::GetClass
ms.date: 03/30/2017
api_name:
- ICorDebugObjectValue.GetClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugObjectValue::GetClass
helpviewer_keywords:
- ICorDebugObjectValue::GetClass method [.NET Framework debugging]
- GetClass method, ICorDebugObjectValue interface [.NET Framework debugging]
ms.assetid: 5be25292-8357-445f-a09b-f997c0de761c
topic_type:
- apiref
ms.openlocfilehash: d15938e94d647fd5fded23c72bdc200d198d21a7
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792696"
---
# <a name="icordebugobjectvaluegetclass-method"></a>Metodo ICorDebugObjectValue::GetClass
Ottiene la classe del valore di questo oggetto.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetClass (  
    [out] ICorDebugClass     **ppClass  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `ppClass`  
 out Puntatore all'indirizzo di un oggetto "ICorDebugClass" che rappresenta la classe del valore dell'oggetto rappresentato da questo oggetto "ICorDebugObjectValue".  
  
## <a name="remarks"></a>Note  
 I metodi `GetClass` e [ICorDebugValue:: GetType](icordebugvalue-gettype-method.md) restituiscono informazioni sul tipo di un valore. entrambi sono sostituiti dai generics-Aware [ICorDebugValue2:: GetExactType](icordebugvalue2-getexacttype-method.md).  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
