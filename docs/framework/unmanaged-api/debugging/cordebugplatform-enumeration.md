---
title: Enumerazione CorDebugPlatform
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- CorDebugPlatformEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugPlatformEnum
helpviewer_keywords:
- CorDebugPlatformEnum enumeration [.NET Framework debugging]
ms.assetid: c5444816-7378-4521-afd3-bf5e4b5303d5
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1f67ed6ad886c137eddaa42840f3f0edda88bd4a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="cordebugplatform-enumeration"></a>Enumerazione CorDebugPlatform
Fornisce i valori di piattaforma di destinazione vengono utilizzati dal [ICorDebugDataTarget:: GetPlatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md) metodo.  
  
## <a name="syntax"></a>Sintassi  
  
```  
typedef enum CorDebugPlatform  
{  
    CORDB_PLATFORM_WINDOWS_X86,    // Windows on Intel x86  
    CORDB_PLATFORM_WINDOWS_AMD64,  // Windows x64 (AMD64, Intel EM64T)  
    CORDB_PLATFORM_WINDOWS_IA64,   // Windows on Intel IA-64  
    CORDB_PLATFORM_MAC_PPC,        // Macintosh OS on PowerPC  
    CORDB_PLATFORM_MAC_X86,        // Macintosh OS on Intel x86  
    CORDB_PLATFORM_WINDOWS_ARM,    // Windows on ARM  
    CORDB_PLATFORM_MAC_AMD64       // MacOS on Intel x64  
} CorDebugPlatform;  
```  
  
## <a name="members"></a>Membri  
  
|Membro|Descrizione|  
|------------|-----------------|  
|CORDB_PLATFORM_WINDOWS_X86|La piattaforma di destinazione è Windows in esecuzione su hardware Intel x86.|  
|CORDB_PLATFORM_WINDOWS_AMD64|La piattaforma di destinazione è Windows a 64 bit in esecuzione su hardware AMD64 o Intel EM64T.|  
|CORDB_PLATFORM_WINDOWS_IA64|La piattaforma di destinazione è Windows a 32 bit in esecuzione su hardware Intel IA64.|  
|CORDB_PLATFORM_MAC_PPC|La piattaforma di destinazione è il sistema operativo Macintosh in esecuzione su hardware PowerPC.|  
|CORDB_PLATFORM_MAC_X86|La piattaforma di destinazione è il sistema operativo Macintosh in esecuzione su hardware Intel x86.|  
|CORDB_PLATFORM_WINDOWS_ARM|La piattaforma di destinazione è il sistema operativo Macintosh in esecuzione su hardware Windows ARM.|  
|CORDB_PLATFORM_MAC_AMD64|La piattaforma di destinazione è il sistema operativo Macintosh in esecuzione su hardware AMD64.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
 I membri `CORDB_PLATFORM_WINDOWS_ARM` e `CORDB_PLATFORM_MAC_AMD64` sono disponibili in .NET Framework 4.5.2 e versioni successive.  
  
## <a name="see-also"></a>Vedere anche  
 [Enumerazioni di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
