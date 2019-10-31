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
ms.openlocfilehash: 199f58456e64ccf7ef771d42d5c7d64b189cb670
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125503"
---
# <a name="icordebugcomobjectvaluegetcachedinterfacetypes-method"></a>Metodo ICorDebugComObjectValue::GetCachedInterfaceTypes
Fornisce un enumeratore per i tipi di interfaccia a cui è stato eseguito il cast o l'utilizzo dell'oggetto corrente.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetCachedInterfaceTypes(  
    [in] BOOL bIInspectableOnly,  
    [out] ICorDebugTypeEnum **ppInterfacesEnum);  
```  
  
## <a name="parameters"></a>Parametri  
 `bIInspectableOnly`  
 in Valore che indica se il metodo restituisce solo Windows Runtime interfacce (`IInspectable` interfacce) o tutte le interfacce COM memorizzate nella cache dal Runtime Callable Wrapper (RCW).  
  
 `ppInterfacesEnum`  
 out Puntatore all'indirizzo di un enumeratore ICorDebugTypeEnum che fornisce l'accesso agli oggetti ICorDebugType che rappresentano i tipi di interfaccia memorizzati nella cache filtrati in base al `bIInspectableOnly`.  
  
## <a name="remarks"></a>Note  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugComObjectValue](../../../../docs/framework/unmanaged-api/debugging/icordebugcomobjectvalue-interface.md)
- [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
