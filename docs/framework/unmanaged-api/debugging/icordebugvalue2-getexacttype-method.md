---
title: Metodo ICorDebugValue2::GetExactType
ms.date: 03/30/2017
api_name:
- ICorDebugValue2.GetExactType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue2::GetExactType
helpviewer_keywords:
- ICorDebugValue2::GetExactType method [.NET Framework debugging]
- GetExactType method [.NET Framework debugging]
ms.assetid: 8e9aae1b-d1b7-4b6e-b577-6faf36dcec85
topic_type:
- apiref
ms.openlocfilehash: 441d225dadbbca09ab27c8ccd70debe32f4c12da
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140262"
---
# <a name="icordebugvalue2getexacttype-method"></a>Metodo ICorDebugValue2::GetExactType
Ottiene un puntatore a interfaccia a un oggetto "ICorDebugType" che rappresenta il <xref:System.Type> di questo valore.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetExactType (  
    [out] ICorDebugType   **ppType  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `ppType`  
 out Puntatore all'indirizzo di un `ICorDebugType` oggetto che rappresenta la <xref:System.Type> del valore rappresentato da questo oggetto "ICorDebugValue2".  
  
## <a name="remarks"></a>Note  
 Il metodo `GetExactType` in grado di riconoscere i generics sostituisce entrambi i metodi [ICorDebugObjectValue:: GetClass](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getclass-method.md) e [ICorDebugValue:: GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-gettype-method.md) , ciascuno dei quali restituisce informazioni sul tipo di un valore.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
