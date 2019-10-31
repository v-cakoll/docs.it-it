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
ms.openlocfilehash: 3593e4d68058a1820f575c92ff9571d43560316a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133924"
---
# <a name="iclrsyncmanager-interface"></a>Interfaccia ICLRSyncManager
Definisce i metodi che consentono all'host di ottenere informazioni sulle attività richieste e di rilevare i deadlock nell'implementazione della sincronizzazione.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo CreateRWLockOwnerIterator](iclrsyncmanager-createrwlockowneriterator-method.md)|Richiede che il Common Language Runtime (CLR) crei un iteratore per l'host da utilizzare per determinare il set di attività in attesa di un blocco in lettura/scrittura.|  
|[Metodo DeleteRWLockOwnerIterator](iclrsyncmanager-deleterwlockowneriterator-method.md)|Richiede che CLR elimini un iteratore creato da una chiamata a `CreateRWLockOwnerIterator`.|  
|[Metodo GetMonitorOwner](iclrsyncmanager-getmonitorowner-method.md)|Ottiene l'attività che possiede il monitor specificato.|  
|[Metodo GetRWLockOwnerNext](iclrsyncmanager-getrwlockownernext-method.md)|Ottiene l'attività successiva in attesa del blocco di lettura/scrittura corrente.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Threading.Thread>
- [Interfaccia IHostSyncManager](ihostsyncmanager-interface.md)
- [Threading gestito e non gestito](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/5s8ee185(v=vs.100))
- [Interfacce di hosting](hosting-interfaces.md)
