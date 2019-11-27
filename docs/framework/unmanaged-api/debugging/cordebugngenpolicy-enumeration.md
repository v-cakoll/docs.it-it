---
title: Enumerazione CorDebugNGenPolicy
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- CorDebugNGenPolicy
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugNGenPolicy
helpviewer_keywords:
- CorDebugNgenPolicy enumeration [.NET Framework debugging]
ms.assetid: edb4e4d2-3166-44d4-8b17-bf302f7ea093
topic_type:
- apiref
ms.openlocfilehash: 2f8337f96239948189ffd58923d87fd05c79b0c3
ms.sourcegitcommit: 81ad1f09b93f3b3e6706a7f2e4ddf50ef229ea3d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/20/2019
ms.locfileid: "74204855"
---
# <a name="cordebugngenpolicy-enumeration"></a>Enumerazione CorDebugNGenPolicy
Fornisce un valore che determina se un debugger carica immagini native (NGen) dalla cache delle immagini native.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp
enum CorDebugNGENPolicy {  
    DISABLE_LOCAL_NIC = 1  
} CorDebugNGENPolicy;  
```  
  
## <a name="members"></a>Membri  
  
|Nome del membro|description|  
|-----------------|-----------------|  
|`DISABLE_LOCAL_NIC`|In un'app di Windows 8. x Store, l'uso delle immagini dalla cache delle immagini native locale è disabilitato. In un'applicazione desktop questa impostazione non ha alcun effetto.|  
  
## <a name="remarks"></a>Osservazioni  
 L'enumerazione `CorDebugNGENPolicy` viene utilizzata dal metodo [ICorDebugProcess5:: EnableNGENPolicy](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enablengenpolicy-method.md) . La disabilitazione dell'utilizzo di immagini dalla cache delle immagini native locale garantisce un'esperienza di debug coerente garantendo che il debugger carichi immagini compilate tramite JIT sottoposte a debug anziché immagini native ottimizzate.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazioni di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
