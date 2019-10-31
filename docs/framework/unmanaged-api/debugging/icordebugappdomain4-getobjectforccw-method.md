---
title: Metodo ICorDebugAppDomain4::GetObjectForCCW
ms.date: 03/30/2017
ms.assetid: 2cacdb85-e7b8-42e7-b310-c3e8c22e5d33
ms.openlocfilehash: 8b046eb5926bb9aa4738e8fff8e61b0b7c23a3aa
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73088834"
---
# <a name="icordebugappdomain4getobjectforccw-method"></a>Metodo ICorDebugAppDomain4::GetObjectForCCW
Ottiene un oggetto gestito da un puntatore a COM Callable Wrapper (CCW)  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetObjectForCCW(  
   [in]CORDB_ADDRESS ccwPointer,   
   [out]ICorDebugValue **ppManagedObject  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `ccwPointer`  
 [in] Puntatore a COM Callable Wrapper (CCW)  
  
 `ppManagedObject`  
 out Puntatore all'indirizzo di un oggetto "ICorDebugValue" che rappresenta l'oggetto gestito che corrisponde al puntatore CCW specificato.  
  
## <a name="remarks"></a>Note  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugAppDomain4](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain4-interface.md)
- [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
