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
ms.openlocfilehash: 1b87ccc3d6c3e957d0384499048032e35247093a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="iclrsyncmanager-interface"></a>Interfaccia ICLRSyncManager
Definisce i metodi che consentono all'host per ottenere informazioni sulle attività richieste e di rilevare deadlock nell'implementazione della sincronizzazione.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo CreateRWLockOwnerIterator](iclrsyncmanager-createrwlockowneriterator-method.md)|Richiede che common language runtime (CLR) crea un iteratore per l'host da usare per determinare il set di attività in attesa di un blocco di lettura / scrittura.|  
|[Metodo DeleteRWLockOwnerIterator](iclrsyncmanager-deleterwlockowneriterator-method.md)|Richiede che Common Language Runtime di eliminare un iteratore che è stato creato da una chiamata a `CreateRWLockOwnerIterator`.|  
|[Metodo GetMonitorOwner](iclrsyncmanager-getmonitorowner-method.md)|Ottiene l'attività proprietaria del monitor specificato.|  
|[Metodo GetRWLockOwnerNext](iclrsyncmanager-getrwlockownernext-method.md)|Ottiene l'attività successiva è in attesa sul blocco di lettura / scrittura corrente.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../get-started/system-requirements.md).  
  
 **Intestazione:** Mscoree. H  
  
 **Libreria:** inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Threading.Thread>  
 [Interfaccia IHostSyncManager](ihostsyncmanager-interface.md)  
 [Threading gestito e non gestito](https://msdn.microsoft.com/library/db425c20-4b2f-4433-bf96-76071c7881e5(v=vs.100))  
 [Interfacce di hosting](hosting-interfaces.md)
