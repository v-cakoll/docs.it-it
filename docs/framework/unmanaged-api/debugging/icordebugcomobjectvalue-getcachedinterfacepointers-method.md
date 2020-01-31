---
title: Metodo ICorDebugComObjectValue::GetCachedInterfacePointers
ms.date: 03/30/2017
api_name:
- ICorDebugComObjectValue::GetCachedInterfacePointers
api_location:
- mscordbi.dll
f1_keywords:
- ICorDebugComObjectValue::GetCachedInterfacePointers
helpviewer_keywords:
- ICorDebugComObjectValue::GetCachedInterfacePointers method [.NET Framework debugging]
- GetCachedInterfacePointers method, ICorDebugComObjectValue interface [.NET Framework debugging]
ms.assetid: 08dbd558-bd39-4263-94c2-71e70687aaf0
topic_type:
- apiref
ms.openlocfilehash: 9d1d6d2f506086dd3204053b0b635da2e7cdc87e
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76783959"
---
# <a name="icordebugcomobjectvaluegetcachedinterfacepointers-method"></a>Metodo ICorDebugComObjectValue::GetCachedInterfacePointers
Ottiene i puntatori di interfaccia raw memorizzati nella cache nel Runtime Callable Wrapper (RCW) corrente.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetCachedInterfacePointers(  
    [in] BOOL bIInspectableOnly,  
    [in] ULONG32 celt,  
    [out] ULONG32 *pceltFetched,  
    [out, size_is(celt), length_is(*pceltFetched) CORDB_ADDRESS *ptrs);  
```  
  
## <a name="parameters"></a>Parametri  
 `bIInspectableOnly`  
 in Valore che indica se il metodo restituirà solo Windows Runtime interfacce (`IInspectable` interfacce) o tutte le interfacce COM memorizzate nella cache dal Runtime Callable Wrapper (RCW).  
  
 `celt`  
 in Numero di oggetti di cui devono essere recuperati gli indirizzi.  
  
 `pceltFetched`  
 out Puntatore al numero di valori di `CORDB_ADDRESS` effettivamente restituiti in `ptrs`.  
  
 `ptrs`  
 Puntatore all'indirizzo iniziale di una matrice di valori `CORDB_ADDRESS` che contengono gli indirizzi degli oggetti dell'interfaccia memorizzati nella cache.  
  
## <a name="remarks"></a>Note  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugComObjectValue](icordebugcomobjectvalue-interface.md)
- [Interfacce di debug](debugging-interfaces.md)
