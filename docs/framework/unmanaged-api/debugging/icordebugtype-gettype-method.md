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
ms.openlocfilehash: 7f3010cccc584288608b3f6ba95efbeb95f271fb
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132051"
---
# <a name="icordebugtypegettype-method"></a>Metodo ICorDebugType::GetType
Ottiene un valore CorElementType che descrive il tipo nativo del Common Language Runtime (CLR) <xref:System.Type> rappresentato da ICorDebugType.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetType (  
    [out] CorElementType   *ty  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `ty`  
 out Puntatore a un valore dell'enumerazione `CorElementType` che indica la <xref:System.Type> CLR rappresentata da questo `ICorDebugType`.  
  
## <a name="remarks"></a>Note  
 Se il valore di `ty` è ELEMENT_TYPE_CLASS o ELEMENT_TYPE_VALUETYPE, è possibile chiamare il metodo [ICorDebugType:: GetClass](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getclass-method.md) per ottenere il tipo di cui non è stata creata un'istanza per un tipo generico. in caso contrario, non chiamare `ICorDebugType::GetClass`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
