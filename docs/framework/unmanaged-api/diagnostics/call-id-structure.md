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
ms.openlocfilehash: 1c795ee536483a7def9c0339efae66a013898a77
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420630"
---
# <a name="call_id-structure"></a>Struttura CALL_ID
Fornisce informazioni a un debugger relativo a una funzione chiamata. Per ulteriori informazioni, vedere l'interfaccia [INotifySink2](inotifysink2-interface.md) .  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
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
  
|Membro|Description|  
|------------|-----------------|  
|`szMachine`|Identifica il computer che effettua la chiamata.|  
|`dwPid`|Identifica il processore del computer.|  
|`pUserThread`|Identifica il thread che esegue la chiamata.|  
|`addrStackPointer`|Specifica l'indirizzo dello stack di chiamate.|  
|`szEntryPoint`|Specifica l'indirizzo della chiamata.|  
|`szDestinationMachine`|Identifica il computer che eseguirà la chiamata.|  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** ProtocolNotify2. idl  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia INotifySink2](inotifysink2-interface.md)
- [Strutture dell'archivio simboli di diagnostica](diagnostics-symbol-store-structures.md)
