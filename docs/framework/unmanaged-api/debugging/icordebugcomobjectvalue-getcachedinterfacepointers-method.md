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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: da0e62250dbef9be93ccee7020e23c3f83e85592
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61749904"
---
# <a name="icordebugcomobjectvaluegetcachedinterfacepointers-method"></a>Metodo ICorDebugComObjectValue::GetCachedInterfacePointers
Ottiene i puntatori a interfaccia raw memorizzato nella cache su corrente runtime callable wrapper (RCW).  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetCachedInterfacePointers(  
    [in] BOOL bIInspectableOnly,  
    [in] ULONG32 celt,  
    [out] ULONG32 *pceltFetched,  
    [out, size_is(celt), length_is(*pceltFetched) CORDB_ADDRESS *ptrs);  
```  
  
## <a name="parameters"></a>Parametri  
 `bIInspectableOnly`  
 [in] Un valore che indica se il metodo restituirà solo [!INCLUDE[wrt](../../../../includes/wrt-md.md)] interfacce (`IInspectable` interfacce) o tutte le interfacce COM presenti nella cache il runtime callable wrapper (RCW).  
  
 `celt`  
 [in] Il numero di oggetti cui indirizzi devono essere recuperate.  
  
 `pceltFetched`  
 [out] Un puntatore al numero di `CORDB_ADDRESS` valori effettivamente restituiti nella `ptrs`.  
  
 `ptrs`  
 Un puntatore all'indirizzo iniziale di una matrice di `CORDB_ADDRESS` valori che contengono gli indirizzi di memorizzati nella cache gli oggetti dell'interfaccia.  
  
## <a name="remarks"></a>Note  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugComObjectValue](../../../../docs/framework/unmanaged-api/debugging/icordebugcomobjectvalue-interface.md)
- [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
