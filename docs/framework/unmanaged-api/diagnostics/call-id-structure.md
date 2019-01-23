---
title: Struttura CALL_ID
ms.date: 03/30/2017
api_name:
- CALL_ID
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- CALL_ID
helpviewer_keywords:
- CALL_ID structure [.NET Framework debugging]
ms.assetid: bfd46324-afec-4782-9c18-586d81fb4740
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 204c2dfbf28f95c1b8c2d2c1b757730e64a8e91d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54503703"
---
# <a name="callid-structure"></a>Struttura CALL_ID
Fornisce informazioni relative a una funzione che viene chiamata un debugger. Vedere le [INotifySink2](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md) interfaccia per altre informazioni.  
  
## <a name="syntax"></a>Sintassi  
  
```  
typedef struct tagCALL_ID  
{  
    LPCOLESTR       szMachine;  
    DWORD           dwPid;  
    USER_THREAD     *pUserThread;  
    STACK_ADDRESS   addrStackPointer;  
    LPCOLESTR       szEntryPoint;  
    LPCOLESTR       szDestinationMachine;  
} CALL_ID;  
```  
  
## <a name="members"></a>Membri  
  
|Membro|Descrizione|  
|------------|-----------------|  
|`szMachine`|Identifica il computer che esegue la chiamata.|  
|`dwPid`|Identifica il processore della macchina.|  
|`pUserThread`|Identifica il thread che sta eseguendo la chiamata.|  
|`addrStackPointer`|Specifica l'indirizzo dello stack di chiamate.|  
|`szEntryPoint`|Specifica l'indirizzo della chiamata.|  
|`szDestinationMachine`|Identifica il computer che eseguirà la chiamata.|  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** ProtocolNotify2.idl  
  
## <a name="see-also"></a>Vedere anche
- [Interfaccia INotifySink2](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)
- [Strutture dell'archivio simboli di diagnostica](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-structures.md)
