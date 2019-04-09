---
title: Interfaccia ICLRSyncManager
ms.date: 03/30/2017
api_name:
- ICLRSyncManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRSyncManager
helpviewer_keywords:
- ICLRSyncManager interface [.NET Framework hosting]
ms.assetid: a49f9d80-1c76-4ddd-8c49-34f913a5c596
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d3e4affa363083ce55ac3764c26412a0d60ba3f6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59203093"
---
# <a name="iclrsyncmanager-interface"></a>Interfaccia ICLRSyncManager
Definisce i metodi che consentono all'host per ottenere informazioni sulle attività di richiesta e per rilevare i deadlock nell'implementazione della sincronizzazione.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo CreateRWLockOwnerIterator](iclrsyncmanager-createrwlockowneriterator-method.md)|Richieste che common language runtime (CLR) crea un iteratore per l'host da usare per determinare il set di attività in attesa di un blocco di lettura / scrittura.|  
|[Metodo DeleteRWLockOwnerIterator](iclrsyncmanager-deleterwlockowneriterator-method.md)|Richiede a CLR di eliminare un iteratore che è stato creato da una chiamata a `CreateRWLockOwnerIterator`.|  
|[Metodo GetMonitorOwner](iclrsyncmanager-getmonitorowner-method.md)|Ottiene l'attività che possiede il monitoraggio specificato.|  
|[Metodo GetRWLockOwnerNext](iclrsyncmanager-getrwlockownernext-method.md)|Ottiene l'attività successiva in attesa di blocco in lettura-scrittura corrente.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE.h  
  
 **Libreria:** Inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Threading.Thread>
- [Interfaccia IHostSyncManager](ihostsyncmanager-interface.md)
- [Threading gestito e non gestito](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/5s8ee185(v=vs.100))
- [Interfacce di hosting](hosting-interfaces.md)
