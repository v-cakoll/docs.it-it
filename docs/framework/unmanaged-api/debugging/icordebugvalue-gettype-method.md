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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 83265c4f6dffed76f1710378cf5293aac7020ef2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59119353"
---
# <a name="icordebugvaluegettype-method"></a>Metodo ICorDebugValue::GetType
Ottiene il tipo primitivo di questo oggetto "ICorDebugValue".  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetType (  
    [out] CorElementType   *pType  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pType`  
 [out] Puntatore a un valore di enumerazione che indica il tipo del valore "CorElementType".  
  
## <a name="remarks"></a>Note  
 Se l'oggetto è un tipo complesso in fase di esecuzione, tale tipo può essere esaminato mediante le sottoclassi appropriate del `ICorDebugValue` interfaccia. Ad esempio, "ICorDebugObjectValue," che eredita da `ICorDebugValue`, rappresenta un tipo complesso.  
  
 Il `GetType` e [ICorDebugObjectValue](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getclass-method.md) ogni i metodi restituiscono le informazioni sul tipo di valore. Entrambi sono sostituiti da GetExactType [ICorDebugValue2::GetExactType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue2-getexacttype-method.md) (metodo).  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
