---
title: Interfaccia ICLRMemoryNotificationCallback
ms.date: 03/30/2017
api_name:
- ICLRMemoryNotificationCallback
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMemoryNotificationCallback
helpviewer_keywords:
- ICLRMemoryNotificationCallback interface [.NET Framework hosting]
ms.assetid: 873639e2-4837-4568-83b3-4493e67e4174
topic_type:
- apiref
ms.openlocfilehash: 52fc21044d345998ad72c045cdf5e80a8a03a38e
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703809"
---
# <a name="iclrmemorynotificationcallback-interface"></a>Interfaccia ICLRMemoryNotificationCallback
Consente all'host di segnalare le condizioni di utilizzo della memoria utilizzando un approccio simile a quello della `CreateMemoryResourceNotification` funzione Win32.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo OnMemoryNotification](iclrmemorynotificationcallback-onmemorynotification-method.md)|Notifica al Common Language Runtime (CLR) il carico di memoria nel computer.|  
  
## <a name="remarks"></a>Osservazioni  
 L'host utilizza l' `ICLRMemoryNotificationCallback` interfaccia per richiedere che le risorse di memoria di CLR siano disponibili.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IHostMemoryManager](ihostmemorymanager-interface.md)
- [Interfacce di hosting](hosting-interfaces.md)
