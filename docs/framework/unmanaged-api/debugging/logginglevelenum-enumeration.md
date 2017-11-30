---
title: Enumerazione LoggingLevelEnum
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: LoggingLevelEnum
api_location: mscordbi.dll
api_type: COM
f1_keywords: LoggingLevelEnum
helpviewer_keywords: LoggingLevelEnum enumeration [.NET Framework debugging]
ms.assetid: 09daac08-005a-46b2-beab-408d0820c5e5
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1f6041f429c057cea9607df34ec5691be84e2d3c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="logginglevelenum-enumeration"></a>Enumerazione LoggingLevelEnum
Indica il livello di gravità di un messaggio descrittivo scritto nel registro eventi quando un thread gestito registra un evento.  
  
## <a name="syntax"></a>Sintassi  
  
```  
typedef enum LoggingLevelEnum {  
    LTraceLevel0 = 0,  
    LTraceLevel1,  
    LTraceLevel2,  
    LTraceLevel3,  
    LTraceLevel4,  
    LStatusLevel0 = 20,  
    LStatusLevel1,  
    LStatusLevel2,  
    LStatusLevel3,  
    LStatusLevel4,  
    LWarningLevel = 40,  
    LErrorLevel = 50,  
    LPanicLevel = 100  
} LoggingLevelEnum;  
```  
  
## <a name="members"></a>Membri  
  
|Membro|Descrizione|  
|------------|-----------------|  
|`LTraceLevel0`|Il messaggio è un livello di traccia, 0.|  
|`LTraceLevel1`|Il messaggio è un livello di traccia 1.|  
|`LTraceLevel2`|Il messaggio è un livello di traccia 2.|  
|`LTraceLevel3`|Il messaggio è un livello di traccia 3.|  
|`LTraceLevel4`|Il messaggio è un livello di traccia 4.|  
|`LStatusLevel0`|Il messaggio è un livello di stato 0.|  
|`LStatusLevel1`|Il messaggio è un livello di stato 1.|  
|`LStatusLevel2`|Il messaggio è un livello di stato 2.|  
|`LStatusLevel3`|Il messaggio è un livello di stato 3.|  
|`LStatusLevel4`|Il messaggio è un livello di stato 4.|  
|`LWarningLevel`|Il messaggio è un livello di avviso.|  
|`LErrorLevel`|Il messaggio è un livello di errore.|  
|`LPanicLevel`|Il messaggio è un livello di panico.|  
  
## <a name="remarks"></a>Note  
 Common language runtime (CLR) chiama il [ICorDebugManagedCallback:: LogMessage](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-logmessage-method.md) metodo per notificare al debugger che un thread gestito ha registrato un evento. CLR passa il valore di `LoggingLevelEnum` enumerazione per indicare il livello di gravità del messaggio che il thread gestito ha scritto nel registro eventi.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Diagnostics.EventLog>  
 [Enumerazioni di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
