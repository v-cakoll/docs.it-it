---
title: Metodo ICorDebugType::GetType
ms.date: 03/30/2017
api_name:
- ICorDebugType.GetType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::GetType
helpviewer_keywords:
- ICorDebugType::GetType method [.NET Framework debugging]
- GetType method, ICorDebugType interface [.NET Framework debugging]
ms.assetid: d6e64534-4d47-4ad0-a340-7590e07e2b4a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 78f2733584e07433171c91d6a2674d3a67c8e283
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67772512"
---
# <a name="icordebugtypegettype-method"></a>Metodo ICorDebugType::GetType
Ottiene un valore CorElementType che descrive il tipo nativo del common language runtime (CLR) <xref:System.Type> rappresentato da questo ICorDebugType.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetType (  
    [out] CorElementType   *ty  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `ty`  
 [out] Un puntatore a un valore di `CorElementType` enumerazione che indica il CLR <xref:System.Type> da questo `ICorDebugType` rappresenta.  
  
## <a name="remarks"></a>Note  
 Se il valore di `ty` è ELEMENT_TYPE_CLASS o ELEMENT_TYPE_VALUETYPE, il [ICorDebugType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getclass-method.md) metodo può essere chiamato per ottenere il tipo privo di istanze per un tipo generico; in caso contrario, non chiamare `ICorDebugType::GetClass`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
