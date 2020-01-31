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
ms.openlocfilehash: 25ffbf73fbefbb3c584450283c3080dfc11ee598
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791250"
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
 Se il valore di `ty` è ELEMENT_TYPE_CLASS o ELEMENT_TYPE_VALUETYPE, è possibile chiamare il metodo [ICorDebugType:: GetClass](icordebugtype-getclass-method.md) per ottenere il tipo di cui non è stata creata un'istanza per un tipo generico. in caso contrario, non chiamare `ICorDebugType::GetClass`.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
