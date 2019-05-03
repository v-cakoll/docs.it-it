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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ca922d8b582c0608073d4fd0ba986167ae470e34
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61599502"
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
  
|Nome del membro|Descrizione|  
|-----------------|-----------------|  
|`DISABLE_LOCAL_NIC`|In un [!INCLUDE[win8_appname_long](../../../../includes/win8-appname-long-md.md)] app, l'uso delle immagini dalla cache delle immagini native locale è disabilitato. In un'app desktop, questa impostazione ha effetto.|  
  
## <a name="remarks"></a>Note  
 Il `CorDebugNGENPolicy` enumerazione viene utilizzata per il [ICorDebugProcess5::EnableNGENPolicy](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enablengenpolicy-method.md) (metodo). Disabilitare l'utilizzo delle immagini dalla cache delle immagini native locali fornisce un'esperienza di debug coerente, garantendo che il debugger carica immagini debuggable compilato tramite JIT anziché le immagini native ottimizzate.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazioni di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
