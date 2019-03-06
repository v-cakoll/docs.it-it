---
title: Metodo ICorDebugType::GetStaticFieldValue
ms.date: 03/30/2017
api_name:
- ICorDebugType.GetStaticFieldValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::GetStaticFieldValue
helpviewer_keywords:
- GetStaticFieldValue method, ICorDebugType interface [.NET Framework debugging]
- ICorDebugType::GetStaticFieldValue method [.NET Framework debugging]
ms.assetid: 62eb5d55-53ee-4fb3-8d47-7b6c96808f9e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2c6b86c5ce3cc246af600d9b65d2fe12a0427f9f
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57485395"
---
# <a name="icordebugtypegetstaticfieldvalue-method"></a>Metodo ICorDebugType::GetStaticFieldValue
Ottiene un puntatore a interfaccia a un oggetto ICorDebugValue che contiene il valore del campo statico a cui fa riferimento il campo specificato token lo stack frame specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetStaticFieldValue (  
    [in]  mdFieldDef        fieldDef,  
    [in]  ICorDebugFrame    *pFrame,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `fieldDef`  
 [in] Un `mdFieldDef` token che specifica il campo statico.  
  
 `pFrame`  
 [in] Un puntatore a un'interfaccia ICorDebugFrame che rappresenta il frame dello stack.  
  
 `ppValue`  
 [out] Un puntatore all'indirizzo di un `ICorDebugValue` che contiene il valore del campo statico.  
  
## <a name="remarks"></a>Note  
 Il `GetStaticFieldValue` metodo può essere usato solo se il tipo è ELEMENT_TYPE_CLASS o ELEMENT_TYPE_VALUETYPE, come indicato dal [ICorDebugType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md) (metodo).  
  
 Per i tipi non generici, l'operazione eseguita da `GetStaticFieldValue` è identica alla chiamata [ICorDebugClass](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-getstaticfieldvalue-method.md) sull'oggetto restituito da ICorDebugClass [ICorDebugType::GetClass](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getclass-method.md).  
  
 Per i tipi generici, un valore del campo statico è relativo alla creazione di un'istanza particolare. Inoltre, se il campo statico può essere relativo a un thread, un contesto o un dominio dell'applicazione, quindi lo stack frame per il debugger di determinare il valore appropriato.  
  
## <a name="remarks"></a>Note  
 `GetStaticFieldValue` può essere utilizzato solo quando una chiamata a `ICorDebugType::GetType` restituisce un valore di ELEMENT_TYPE_CLASS o ELEMENT_TYPE_VALUETYPE.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
