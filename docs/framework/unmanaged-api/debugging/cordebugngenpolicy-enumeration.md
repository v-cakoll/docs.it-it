---
title: Enumerazione CorDebugNGenPolicy
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 89767da7178319ed1add3dda0620062893487bfd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
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
|`DISABLE_LOCAL_NIC`|In un [!INCLUDE[win8_appname_long](../../../../includes/win8-appname-long-md.md)] app, l'utilizzo di immagini dalla cache delle immagini native locali è disabilitato. In un'applicazione desktop, questa impostazione non ha alcun effetto.|  
  
## <a name="remarks"></a>Note  
 Il `CorDebugNGENPolicy` enumerazione viene utilizzata per la [icordebugprocess5:: Enablengenpolicy](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enablengenpolicy-method.md) metodo. Disabilitare l'utilizzo di immagini dalla cache delle immagini native locali garantisce per un'esperienza di debug coerente, assicurando che il debugger carica le immagini con compilazione JIT debuggable anziché le immagini native ottimizzate.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Enumerazioni di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
