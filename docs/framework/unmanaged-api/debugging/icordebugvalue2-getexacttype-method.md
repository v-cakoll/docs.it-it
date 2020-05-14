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
ms.openlocfilehash: dcec97bac2aefc8db1f9351f1dacb0f36fc0d2a0
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396803"
---
# <a name="icordebugvalue2getexacttype-method"></a>Metodo ICorDebugValue2::GetExactType
Ottiene un puntatore a interfaccia a un oggetto "ICorDebugType" che rappresenta l'oggetto <xref:System.Type> di questo valore.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetExactType (  
    [out] ICorDebugType   **ppType  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `ppType`  
 out Puntatore all'indirizzo di un `ICorDebugType` oggetto che rappresenta l' <xref:System.Type> oggetto del valore rappresentato da questo oggetto "ICorDebugValue2".  
  
## <a name="remarks"></a>Commenti  
 Il metodo in grado di riconoscere i generics `GetExactType` sostituisce entrambi i metodi [ICorDebugObjectValue:: GetClass](icordebugobjectvalue-getclass-method.md) e [ICorDebugValue:: GetType](icordebugvalue-gettype-method.md) , ciascuno dei quali restituisce informazioni sul tipo di un valore.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
