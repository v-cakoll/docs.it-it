---
title: Enumerazione NOTIFY_FILTER
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: NOTIFY_FILTER
api_location: diasymreader.dll
api_type: COM
f1_keywords: NOTIFY_FILTER
helpviewer_keywords: NOTIFY_FILTER enumeration [.NET Framework debugging]
ms.assetid: 4789d08f-8683-45d3-ac30-73d48c61e470
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 9db03458aab60d28efe52edfd9830da7862fcb8c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="notifyfilter-enumeration"></a>Enumerazione NOTIFY_FILTER
Identifica i callback per funzioni del debugger. Per ulteriori informazioni, vedere il [INotifySource2:: SetNotifyFilter](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-setnotifyfilter-method.md) metodo.  
  
## <a name="syntax"></a>Sintassi  
  
```  
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
  
|Membro|Descrizione|  
|------------|-----------------|  
|`NOTIFY_FILTER_ONSYNCCALLOUT`|Indica che il [INotifySink2:: OnSyncCallOut](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallout-method.md) metodo deve essere richiamato.|  
|`NOTIFY_FILTER_ONSYNCCALLENTER`|Indica che il [INotifySink2:: OnSyncCallEnter](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallenter-method.md) metodo deve essere richiamato.|  
|`NOTIFY_FILTER_ONSYNCCALLEXIT`|Indica che il [INotifySink2:: OnSyncCallExit](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallexit-method.md) metodo deve essere richiamato.|  
|`NOTIFY_FILTER_ONSYNCCALLRETURN`|Indica che il [INotifySink2:: OnSyncCallReturn](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallreturn-method.md) metodo deve essere richiamato.|  
|`NOTIFY_FILTER_ALLSYNC`|Indica che tutti i [INotifySink2](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md) metodi devono essere richiamati.|  
|`NOTIFY_FILTER_ALL`|Attiva tutte le notifiche esistenti e future.|  
|`NOTIFY_FILTER_NONE`|Indica che nessun metodo di notifica deve essere richiamato.|  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** ProtocolNotify2. idl  
  
## <a name="see-also"></a>Vedere anche  
 [Enumerazioni dell'archivio di simboli di diagnostica](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)
