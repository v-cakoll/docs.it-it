---
title: Struttura CALL_ID
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CALL_ID
api_location: diasymreader.dll
api_type: COM
f1_keywords: CALL_ID
helpviewer_keywords: CALL_ID structure [.NET Framework debugging]
ms.assetid: bfd46324-afec-4782-9c18-586d81fb4740
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c44db9021a7dbf5b497db3536eddcea020e71bf7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="callid-structure"></a>Struttura CALL_ID
Vengono fornite informazioni a un debugger su una funzione chiamata. Vedere il [INotifySink2](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md) interfaccia per altre informazioni.  
  
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
|`szDestinationMachine`|Identifica il computer che esegue la chiamata.|  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** ProtocolNotify2. idl  
  
## <a name="see-also"></a>Vedere anche  
 [INotifySink2 (interfaccia)](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)  
 [Strutture di archivio dei simboli di diagnostica](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-structures.md)
