---
title: Enumerazione ETaskType
ms.date: 03/30/2017
api_name:
- ETaskType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ETaskType
helpviewer_keywords:
- ETaskType enumeration [.NET Framework hosting]
ms.assetid: aa527b31-89d4-41f2-ad6f-63b76950b7df
topic_type:
- apiref
ms.openlocfilehash: 0fa72568df77c4916a3c6676e1dcca7c0c616c4a
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84493318"
---
# <a name="etasktype-enumeration"></a>Enumerazione ETaskType
Contiene valori che indicano il tipo di attività rappresentato da un'interfaccia [ICLRTask](iclrtask-interface.md) o [IHostTask](ihosttask-interface.md) .  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
typedef enum ETaskType {  
    TT_DEBUGGERHELPER           = 0x1,  
    TT_GC                       = 0x2,  
    TT_FINALIZER                = 0x4,  
    TT_THREADPOOL_TIMER         = 0x8,  
    TT_THREADPOOL_GATE          = 0x10,  
    TT_THREADPOOL_WORKER        = 0x20,  
    TT_THREADPOOL_IOCOMPLETION  = 0x40,  
    TT_ADUNLOAD                 = 0x80,  
    TT_USER                     = 0x100,  
    TT_THREADPOOL_WAIT          = 0x200,  
    TT_UNKNOWN                  = 0x80000000  
} ETaskType;  
```  
  
## <a name="members"></a>Membri  
  
|Membro|Descrizione|  
|------------|-----------------|  
|`TT_ADUNLOAD`|L'interfaccia rappresenta un'attività di scaricamento del dominio applicazione.|  
|`TT_DEBUGGERHELPER`|L'interfaccia rappresenta un'attività helper del debugger.|  
|`TT_FINALIZER`|L'interfaccia rappresenta un'attività del finalizzatore.|  
|`TT_GC`|L'interfaccia rappresenta un'attività Garbage Collection.|  
|`TT_THREADPOOL_GATE`|L'interfaccia rappresenta un'attività del thread del controllo.|  
|`TT_THREADPOOL_IOCOMPLETION`|L'interfaccia rappresenta un'attività thread di I/O o un'attività thread della porta di completamento.|  
|`TT_THREADPOOL_TIMER`|L'interfaccia rappresenta un'attività thread del timer.|  
|`TT_THREADPOOL_WAIT`|L'interfaccia rappresenta un'attività thread di attesa.|  
|`TT_THREADPOOL_WORKER`|L'interfaccia rappresenta un'attività thread di lavoro.|  
|`TT_UNKNOWN`|L'attività è sconosciuta.|  
|`TT_USER`|L'interfaccia rappresenta un'attività utente.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazioni di hosting](hosting-enumerations.md)
