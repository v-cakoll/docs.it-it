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
ms.openlocfilehash: 95183701987d3ddec3835a17c5d256c25c2c4c64
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132072"
---
# <a name="icordebugtypegetstaticfieldvalue-method"></a>Metodo ICorDebugType::GetStaticFieldValue
Ottiene un puntatore a interfaccia a un oggetto ICorDebugValue che contiene il valore del campo statico a cui fa riferimento il token di campo specificato nel stack frame specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetStaticFieldValue (  
    [in]  mdFieldDef        fieldDef,  
    [in]  ICorDebugFrame    *pFrame,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `fieldDef`  
 in Token `mdFieldDef` che specifica il campo statico.  
  
 `pFrame`  
 in Puntatore a un ICorDebugFrame che rappresenta l'stack frame.  
  
 `ppValue`  
 out Puntatore all'indirizzo di un `ICorDebugValue` che contiene il valore del campo statico.  
  
## <a name="remarks"></a>Note  
 Il metodo `GetStaticFieldValue` può essere utilizzato solo se il tipo è ELEMENT_TYPE_CLASS o ELEMENT_TYPE_VALUETYPE, come indicato dal metodo [ICorDebugType:: GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md) .  
  
 Per i tipi non generici, l'operazione eseguita da `GetStaticFieldValue` è identica alla chiamata di [ICorDebugClass:: GetStaticFieldValue](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-getstaticfieldvalue-method.md) sull'oggetto ICorDebugClass restituito da [ICorDebugType:: GetClass](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getclass-method.md).  
  
 Per i tipi generici, un valore di campo statico sarà relativo a una particolare creazione di istanza. Se, inoltre, il campo statico potrebbe essere relativo a un thread, a un contesto o a un dominio dell'applicazione, il stack frame consentirà al debugger di determinare il valore appropriato.  
  
## <a name="remarks"></a>Note  
 `GetStaticFieldValue` può essere utilizzato solo quando una chiamata a `ICorDebugType::GetType` restituisce un valore di ELEMENT_TYPE_CLASS o ELEMENT_TYPE_VALUETYPE.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
