---
title: Enumerazione NOTIFY_FILTER
ms.date: 03/30/2017
api_name:
- NOTIFY_FILTER
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- NOTIFY_FILTER
helpviewer_keywords:
- NOTIFY_FILTER enumeration [.NET Framework debugging]
ms.assetid: 4789d08f-8683-45d3-ac30-73d48c61e470
topic_type:
- apiref
ms.openlocfilehash: b20e18d5f4314a0ab1442ac7bd5c6514e4db85d5
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83609482"
---
# <a name="notify_filter-enumeration"></a>Enumerazione NOTIFY_FILTER
Identifica i callback per le funzioni del debugger. Per ulteriori informazioni, vedere il metodo [INotifySource2:: SetNotifyFilter](inotifysource2-setnotifyfilter-method.md) .  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
enum tagNOTIFY_FILTER  
{  
    NOTIFY_FILTER_ONSYNCCALLOUT    = 0x1,  
    NOTIFY_FILTER_ONSYNCCALLENTER  = 0x2,  
    NOTIFY_FILTER_ONSYNCCALLEXIT   = 0x4,  
    NOTIFY_FILTER_ONSYNCCALLRETURN = 0x8,  
    NOTIFY_FILTER_ALLSYNC = NOTIFY_FILTER_ONSYNCCALLOUT | NOTIFY_FILTER_ONSYNCCALLENTER | NOTIFY_FILTER_ONSYNCCALLEXIT | NOTIFY_FILTER_ONSYNCCALLRETURN,  
    NOTIFY_FILTER_ALL              = 0xffffffff,  
    NOTIFY_FILTER_NONE             = 0  
};  
```  
  
## <a name="members"></a>Membri  
  
|Membro|Description|  
|------------|-----------------|  
|`NOTIFY_FILTER_ONSYNCCALLOUT`|Indica che il metodo [INotifySink2:: OnSyncCallOut](inotifysink2-onsynccallout-method.md) deve essere richiamato.|  
|`NOTIFY_FILTER_ONSYNCCALLENTER`|Indica che il metodo [INotifySink2:: OnSyncCallEnter](inotifysink2-onsynccallenter-method.md) deve essere richiamato.|  
|`NOTIFY_FILTER_ONSYNCCALLEXIT`|Indica che il metodo [INotifySink2:: OnSyncCallExit](inotifysink2-onsynccallexit-method.md) deve essere richiamato.|  
|`NOTIFY_FILTER_ONSYNCCALLRETURN`|Indica che il metodo [INotifySink2:: OnSyncCallReturn](inotifysink2-onsynccallreturn-method.md) deve essere richiamato.|  
|`NOTIFY_FILTER_ALLSYNC`|Indica che devono essere richiamati tutti i metodi [INotifySink2](inotifysink2-interface.md) .|  
|`NOTIFY_FILTER_ALL`|Attiva tutte le notifiche esistenti e future.|  
|`NOTIFY_FILTER_NONE`|Indica che non deve essere richiamato alcun metodo di notifica.|  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** ProtocolNotify2. idl  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazioni dell'archivio dei simboli di diagnostica](diagnostics-symbol-store-enumerations.md)
