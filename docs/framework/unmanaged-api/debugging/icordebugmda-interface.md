---
title: Interfaccia ICorDebugMDA
ms.date: 03/30/2017
api_name:
- ICorDebugMDA
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugMDA
helpviewer_keywords:
- ICorDebugMDA interface [.NET Framework debugging]
ms.assetid: 8ecbb854-295c-4dd4-b9fc-01ebeac46e06
topic_type:
- apiref
ms.openlocfilehash: d711f36b4e2071dac9458a023e1d3cf4743e77b3
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212633"
---
# <a name="icordebugmda-interface"></a>Interfaccia ICorDebugMDA
Rappresenta un messaggio relativo all'assistente al debug gestito (MDA, Managed Debugging Assistant).  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo GetDescription](icordebugmda-getdescription-method.md)|Ottiene una stringa contenente una descrizione di questo assistente al debug gestito.|  
|[Metodo GetFlags](icordebugmda-getflags-method.md)|Ottiene i flag associati a questo assistente al debug gestito.|  
|[Metodo GetName](icordebugmda-getname-method.md)|Ottiene una stringa contenente il nome di questo assistente al debug gestito.|  
|[Metodo GetOSThreadId](icordebugmda-getosthreadid-method.md)|Ottiene l'identificatore del thread del sistema operativo su cui è in esecuzione questo assistente al debug gestito.|  
|[Metodo GetXML](icordebugmda-getxml-method.md)|Ottiene il flusso XML completo associato a questo assistente al debug gestito.|  
  
## <a name="remarks"></a>Osservazioni  
  
> [!NOTE]
> Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di debug](debugging-interfaces.md)
- [Diagnostica degli errori tramite gli assistenti al debug gestito](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
