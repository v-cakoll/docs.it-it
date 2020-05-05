---
title: Enumerazione CorDebugPlatform
ms.date: 03/30/2017
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
ms.openlocfilehash: fdb03b9244d3cb351735f5f2214248a08a399188
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2020
ms.locfileid: "82795742"
---
# <a name="cordebugplatform-enumeration"></a>Enumerazione CorDebugPlatform
Fornisce i valori della piattaforma di destinazione usati dal metodo [ICorDebugDataTarget:: GetPlatform](icordebugdatatarget-getplatform-method.md) .  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
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
  
## <a name="members"></a>Members  
  
|Membro|Description|  
|------------|-----------------|  
|CORDB_PLATFORM_WINDOWS_X86|La piattaforma di destinazione è Windows in esecuzione su hardware Intel x86.|  
|CORDB_PLATFORM_WINDOWS_AMD64|La piattaforma di destinazione è Windows a 64 bit in esecuzione su hardware AMD64 o Intel EM64T.|  
|CORDB_PLATFORM_WINDOWS_IA64|La piattaforma di destinazione è Windows a 32 bit in esecuzione su hardware Intel IA64.|  
|CORDB_PLATFORM_MAC_PPC|La piattaforma di destinazione è il sistema operativo Macintosh in esecuzione su hardware PowerPC.|  
|CORDB_PLATFORM_MAC_X86|La piattaforma di destinazione è il sistema operativo Macintosh in esecuzione su hardware Intel x86.|  
|CORDB_PLATFORM_WINDOWS_ARM|La piattaforma di destinazione è il sistema operativo Macintosh in esecuzione su hardware ARM di Windows.|  
|CORDB_PLATFORM_MAC_AMD64|La piattaforma di destinazione è il sistema operativo Macintosh in esecuzione su hardware AMD64.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
 I membri `CORDB_PLATFORM_WINDOWS_ARM` e `CORDB_PLATFORM_MAC_AMD64` sono disponibili in .NET Framework 4.5.2 e versioni successive.  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazioni di debug](debugging-enumerations.md)
