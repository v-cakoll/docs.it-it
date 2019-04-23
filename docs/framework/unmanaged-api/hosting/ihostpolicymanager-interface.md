---
title: Interfaccia IHostPolicyManager
ms.date: 03/30/2017
api_name:
- IHostPolicyManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostPolicyManager
helpviewer_keywords:
- IHostPolicyManager interface [.NET Framework hosting]
ms.assetid: 8c4aa124-5e00-46d9-b1e8-57ba6574bb0d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cf9d903b4e44ea7a185ad8b3b71b7a5da2f2bda3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59126347"
---
# <a name="ihostpolicymanager-interface"></a>Interfaccia IHostPolicyManager
Fornisce metodi per notificare all'host le azioni eseguite da common language runtime (CLR) in caso di interruzioni, timeout o errori.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo OnDefaultAction](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-ondefaultaction-method.md)|Notifica all'host che sta CLR per eseguire l'azione predefinita specificata da una chiamata a [SetDefaultAction](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setdefaultaction-method.md) in risposta a un thread di interruzione o <xref:System.AppDomain> unload.|  
|[Metodo OnFailure](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-onfailure-method.md)|Notifica all'host che sta CLR per eseguire l'azione specificata da una chiamata a [SetActionOnFailure](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md) in risposta a un errore di allocazione o recupero di risorse.|  
|[Metodo OnTimeout](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-ontimeout-method.md)|Notifica all'host che sta CLR per eseguire l'azione specificata da una chiamata a [SetActionOnTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md) in risposta a un timeout.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE.h  
  
 **Libreria:** Inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazione EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)
- [Enumerazione EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [Enumerazione EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [Interfaccia ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [Interfacce di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
