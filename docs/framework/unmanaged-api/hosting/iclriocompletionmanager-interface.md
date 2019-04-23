---
title: Interfaccia ICLRIoCompletionManager
ms.date: 03/30/2017
api_name:
- ICLRIoCompletionManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRIoCompletionManager
helpviewer_keywords:
- ICLRIoCompletionManager interface [.NET Framework hosting]
ms.assetid: c6c3ace6-e5e7-4450-8cc5-a9a48208c493
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7864bb81c3b457bf8ec07cd194d24b29a42bd441
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59156065"
---
# <a name="iclriocompletionmanager-interface"></a>Interfaccia ICLRIoCompletionManager
Implementa un metodo di callback che consente all'host di common language runtime (CLR) di inviare una notifica dello stato dei / o specifico le richieste.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo OnComplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md)|Invia una notifica dello stato di una richiesta dei / o che è stato effettuato mediante una chiamata a CLR i [IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md) (metodo).|  
  
## <a name="remarks"></a>Note  
 L'host implementa l'astrazione di completamento i/o utilizzando il [IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md) interfaccia. Common Language Runtime effettua le richieste dei / o tramite questa interfaccia e l'host di notifica il runtime il risultato di tali richieste usando il `ICLRIoCompletionManager` interfaccia.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE.h  
  
 **Libreria:** Inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
- [Interfaccia IHostThreadPoolManager](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
- [Interfacce di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
