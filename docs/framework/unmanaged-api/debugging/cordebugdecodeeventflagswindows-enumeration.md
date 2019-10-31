---
title: Enumerazione CorDebugDecodeEventFlagsWindows
ms.date: 03/30/2017
api_name:
- CorDebugDecodeEventFlagsWindows
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: aa6cf962-30ae-4cfd-8895-826deeb46a54
topic_type:
- apiref
ms.openlocfilehash: da3a100bd552eaa3233642b006e0265adbcac1ca
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132207"
---
# <a name="cordebugdecodeeventflagswindows-enumeration"></a>Enumerazione CorDebugDecodeEventFlagsWindows
Fornisce altre informazioni sugli eventi di debug nella piattaforma Windows.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
typedef enum CorDebugDecodeEventFlagsWindows {  
    IS_FIRST_CHANCE = 1,  
} CorDebugDecodeEventFlagsWindows;  
```  
  
## <a name="members"></a>Members  
  
|Member|Descrizione|  
|------------|-----------------|  
|`IS_FIRST_CHANCE`|Indica che l'evento di debug è un'eccezione first-chance.|  
  
## <a name="remarks"></a>Note  
 Il metodo [Metodo icordebugprocess6::D ecodeevent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md) include un parametro `dwFlags` che fornisce informazioni aggiuntive su un evento di debug e il cui valore dipende dall'architettura di destinazione. L'enumerazione `CorDebugDecodeEventFlagsWindows` può essere usata con gli eventi di debug nella piattaforma Windows.  
  
> [!NOTE]
> Questa enumerazione è progettata per l'uso solo in scenari di debug di .NET Native.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazioni di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
