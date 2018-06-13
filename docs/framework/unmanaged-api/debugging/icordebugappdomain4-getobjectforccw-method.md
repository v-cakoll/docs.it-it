---
title: Metodo ICorDebugAppDomain4::GetObjectForCCW
ms.date: 03/30/2017
ms.assetid: 2cacdb85-e7b8-42e7-b310-c3e8c22e5d33
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f1089668aa19747f5f694360ebb87098e2df9ad4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33405551"
---
# <a name="icordebugappdomain4getobjectforccw-method"></a>Metodo ICorDebugAppDomain4::GetObjectForCCW
Ottiene un oggetto gestito da un puntatore a COM Callable Wrapper (CCW)  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetObjectForCCW(  
   [in]CORDB_ADDRESS ccwPointer,   
   [out]ICorDebugValue **ppManagedObject  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `ccwPointer`  
 [in] Puntatore a COM Callable Wrapper (CCW)  
  
 `ppManagedObject`  
 [out] Un puntatore all'indirizzo di un oggetto "ICorDebugValue" che rappresenta l'oggetto gestito che corrisponde al puntatore CCW specificato.  
  
## <a name="remarks"></a>Note  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cordebug. idl, Cordebug. H  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorDebugAppDomain4](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain4-interface.md)  
 [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
