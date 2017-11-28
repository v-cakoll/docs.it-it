---
title: Interfaccia ICorDebugMDA
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugMDA
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugMDA
helpviewer_keywords: ICorDebugMDA interface [.NET Framework debugging]
ms.assetid: 8ecbb854-295c-4dd4-b9fc-01ebeac46e06
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 00a003ee060de59fe0eb8ce8f740a620d77a7c85
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugmda-interface"></a>Interfaccia ICorDebugMDA
Rappresenta un messaggio relativo all'assistente al debug gestito (MDA, Managed Debugging Assistant).  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[GetDescription (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-getdescription-method.md)|Ottiene una stringa contenente una descrizione di questo assistente al debug gestito.|  
|[Metodo GetFlags](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-getflags-method.md)|Ottiene i flag associati a questo assistente al debug gestito.|  
|[GetName (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-getname-method.md)|Ottiene una stringa contenente il nome di questo assistente al debug gestito.|  
|[GetOSThreadId (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-getosthreadid-method.md)|Ottiene l'identificatore del thread del sistema operativo in cui è in esecuzione questo assistente al debug gestito.|  
|[GetXML (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-getxml-method.md)|Ottiene il flusso XML completo associato a questo assistente al debug gestito.|  
  
## <a name="remarks"></a>Note  
  
> [!NOTE]
>  Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [Diagnostica degli errori tramite gli assistenti al debug gestito](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
