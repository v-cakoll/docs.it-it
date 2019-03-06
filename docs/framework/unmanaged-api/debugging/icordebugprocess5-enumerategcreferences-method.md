---
title: Metodo ICorDebugProcess5::EnumerateGCReferences
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.EnumerateGCReferences
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::EnumerateGCReferences
helpviewer_keywords:
- EnumerateGCReferences method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::EnumerateGCReferences method [.NET Framework debugging]
ms.assetid: 86c397c3-81d8-463e-a248-3cbe06c44d9d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 54e2648765d896c189cc2deb5590a0a2a9b3f410
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57476484"
---
# <a name="icordebugprocess5enumerategcreferences-method"></a>Metodo ICorDebugProcess5::EnumerateGCReferences
Ottiene un enumeratore per tutti gli oggetti che devono essere sottoposto a garbage collection in un processo.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT EnumerateGCReferences(  
    [in] Bool enumerateWeakReferences,   
    [out] ICorDebugGCReferenceEnum **ppEnum  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `enumerateWeakReferences`  
 [in] Valore booleano che indica se i riferimenti deboli sono anche da enumerare. Se `enumerateWeakReferences` viene `true`, il `ppEnum` enumeratore include riferimenti forti e i riferimenti deboli. Se `enumerateWeakReferences` è `false`, l'enumeratore include solo i riferimenti sicuri.  
  
 `ppEnum`  
 [out] Un puntatore all'indirizzo di un [ICorDebugGCReferenceEnum](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md) vale a dire un enumeratore per gli oggetti per essere sottoposto a garbage collection.  
  
## <a name="remarks"></a>Note  
 Questo metodo fornisce un modo per determinare la catena di definizione radice completa per qualsiasi oggetto gestito in un processo e può essere utilizzato per determinare il motivo per cui un oggetto è ancora attivo.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Interfaccia ICorDebugProcess5](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
