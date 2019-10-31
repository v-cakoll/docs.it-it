---
title: Metodo ICorDebugValue::GetAddress
ms.date: 03/30/2017
api_name:
- ICorDebugValue.GetAddress
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue::GetAddress
helpviewer_keywords:
- ICorDebugValue::GetAddress method [.NET Framework debugging]
- GetAddress method, ICorDebugValue interface [.NET Framework debugging]
ms.assetid: a247c792-45e1-4538-9e1f-b46acca4a463
topic_type:
- apiref
ms.openlocfilehash: 906ca2540e421953b3ce39300aa7b2376f789929
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137106"
---
# <a name="icordebugvaluegetaddress-method"></a>Metodo ICorDebugValue::GetAddress
Ottiene l'indirizzo di questo oggetto "ICorDebugValue", che è in fase di debug.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetAddress (  
    [out] CORDB_ADDRESS   *pAddress  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pAddress`  
 out Puntatore a un oggetto `CORDB_ADDRESS` che specifica l'indirizzo di questo oggetto valore.  
  
## <a name="remarks"></a>Note  
 Se il valore non è disponibile, viene restituito 0 (zero). Questo problema può verificarsi se il valore è almeno parzialmente in registri o archiviato in un handle di Garbage Collector (`GCHandle`).  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
