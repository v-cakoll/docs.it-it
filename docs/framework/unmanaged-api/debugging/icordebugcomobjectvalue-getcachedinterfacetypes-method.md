---
title: Metodo ICorDebugComObjectValue::GetCachedInterfaceTypes
ms.date: 03/30/2017
api_name:
- ICorDebugComObjectValue::GetCachedInterfaceTypes
api_location:
- mscordbi.dll
f1_keywords:
- ICorDebugComObjectValue::GetCachedInterfaceTypes
helpviewer_keywords:
- GetCachedInterface method, ICorDebugComObjectValue interface [.NET Framework debugging]
- ICorDebugComObjectValue::GetCachedInterface method [.NET Framework debugging]
ms.assetid: d492284f-d3c5-4614-adb8-d718d5042500
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 60a74b3c90c11f799f5b9738e84d33b603f0ef04
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57485473"
---
# <a name="icordebugcomobjectvaluegetcachedinterfacetypes-method"></a>Metodo ICorDebugComObjectValue::GetCachedInterfaceTypes
Fornisce un enumeratore per i tipi di interfaccia che l'oggetto corrente è stato eseguito il cast a o utilizzato come.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetCachedInterfaceTypes(  
    [in] BOOL bIInspectableOnly,  
    [out] ICorDebugTypeEnum **ppInterfacesEnum);  
```  
  
## <a name="parameters"></a>Parametri  
 `bIInspectableOnly`  
 [in] Un valore che indica se il metodo restituisce solo [!INCLUDE[wrt](../../../../includes/wrt-md.md)] interfacce (`IInspectable` interfacce) o tutte le interfacce COM memorizzati nella cache dal runtime callable wrapper (RCW).  
  
 `ppInterfacesEnum`  
 [out] Un puntatore all'indirizzo di un enumeratore ICorDebugTypeEnum che fornisce accesso agli oggetti ICorDebugType che rappresentano i tipi di interfaccia memorizzati nella cache filtrata in base alla `bIInspectableOnly`.  
  
## <a name="remarks"></a>Note  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Interfaccia ICorDebugComObjectValue](../../../../docs/framework/unmanaged-api/debugging/icordebugcomobjectvalue-interface.md)
- [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
