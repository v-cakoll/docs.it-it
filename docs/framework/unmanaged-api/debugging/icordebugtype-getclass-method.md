---
title: Metodo ICorDebugType::GetClass
ms.date: 03/30/2017
api_name:
- ICorDebugType.GetClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::GetClass
helpviewer_keywords:
- ICorDebugType::GetClass method [.NET Framework debugging]
- GetClass method, ICorDebugType interface [.NET Framework debugging]
ms.assetid: 2644f48b-db3c-429f-ae62-76f1c98a1af5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bd68df77adafb8b21e7684b28fe978722ca37e16
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67736799"
---
# <a name="icordebugtypegetclass-method"></a>Metodo ICorDebugType::GetClass
Ottiene un puntatore a interfaccia ICorDebugClass che rappresenta il tipo generico privo di istanze.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetClass (  
    [out] ICorDebugClass   **ppClass  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `ppClass`  
 [out] Un puntatore all'indirizzo di un `ICorDebugClass` interfaccia che rappresenta il tipo generico privo di istanze.  
  
## <a name="remarks"></a>Note  
 `GetClass` può essere chiamato solo in determinate condizioni. Chiamare [ICorDebugType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md) prima di chiamare `GetClass`. Se `ICorDebugType::GetType` restituisce un valore di ELEMENT_TYPE_CLASS o ELEMENT_TYPE_VALUETYPE, CorElementType `GetClass` può essere chiamato per ottenere il tipo privo di istanze per un tipo generico.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
