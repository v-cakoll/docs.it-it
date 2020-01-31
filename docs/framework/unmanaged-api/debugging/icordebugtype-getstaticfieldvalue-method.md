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
ms.openlocfilehash: 37bf5abf66b613d8432af84c7d73aff60e9127cb
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791265"
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
 Il metodo `GetStaticFieldValue` può essere utilizzato solo se il tipo è ELEMENT_TYPE_CLASS o ELEMENT_TYPE_VALUETYPE, come indicato dal metodo [ICorDebugType:: GetType](icordebugtype-gettype-method.md) .  
  
 Per i tipi non generici, l'operazione eseguita da `GetStaticFieldValue` è identica alla chiamata di [ICorDebugClass:: GetStaticFieldValue](icordebugclass-getstaticfieldvalue-method.md) sull'oggetto ICorDebugClass restituito da [ICorDebugType:: GetClass](icordebugtype-getclass-method.md).  
  
 Per i tipi generici, un valore di campo statico sarà relativo a una particolare creazione di istanza. Se, inoltre, il campo statico potrebbe essere relativo a un thread, a un contesto o a un dominio dell'applicazione, il stack frame consentirà al debugger di determinare il valore appropriato.  
  
## <a name="remarks"></a>Note  
 `GetStaticFieldValue` può essere utilizzato solo quando una chiamata a `ICorDebugType::GetType` restituisce un valore di ELEMENT_TYPE_CLASS o ELEMENT_TYPE_VALUETYPE.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
