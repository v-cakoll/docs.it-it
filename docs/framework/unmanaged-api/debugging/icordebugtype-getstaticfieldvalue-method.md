---
title: Metodo ICorDebugType::GetStaticFieldValue
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2a6a7305017c83b539a3d5ec11fa61ccd2af90a8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugtypegetstaticfieldvalue-method"></a>Metodo ICorDebugType::GetStaticFieldValue
Ottiene un puntatore a interfaccia a un oggetto ICorDebugValue che contiene il valore del campo statico a cui fa riferimento il campo specificato token stack frame specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetStaticFieldValue (  
    [in]  mdFieldDef        fieldDef,  
    [in]  ICorDebugFrame    *pFrame,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `fieldDef`  
 [in] Un `mdFieldDef` token che specifica il campo statico.  
  
 `pFrame`  
 [in] Puntatore a un'interfaccia ICorDebugFrame che rappresenta lo stack frame.  
  
 `ppValue`  
 [out] Un puntatore all'indirizzo di un `ICorDebugValue` che contiene il valore del campo statico.  
  
## <a name="remarks"></a>Note  
 Il `GetStaticFieldValue` metodo può essere utilizzato solo se il tipo è ELEMENT_TYPE_CLASS o un ELEMENT_TYPE_VALUETYPE, come indicato dal [ICorDebugType:: GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md) metodo.  
  
 Per i tipi non generici, l'operazione eseguita da `GetStaticFieldValue` è identica alla chiamata al metodo [ICorDebugClass:: GetStaticFieldValue](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-getstaticfieldvalue-method.md) sull'oggetto restituito da ICorDebugClass [ICorDebugType::GetClass](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getclass-method.md).  
  
 Per i tipi generici, un valore del campo statico sarà rispetto alla creazione di un'istanza particolare. Inoltre, se il campo statico può essere relativo a un thread, un contesto o dominio applicazione, quindi lo stack frame consentirà il debugger di determinare il valore appropriato.  
  
## <a name="remarks"></a>Note  
 `GetStaticFieldValue`può essere utilizzato solo quando una chiamata a `ICorDebugType::GetType` restituisce un valore ELEMENT_TYPE_CLASS o ELEMENT_TYPE_VALUETYPE.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
