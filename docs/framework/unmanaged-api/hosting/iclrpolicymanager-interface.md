---
title: Interfaccia ICLRPolicyManager
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRPolicyManager
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRPolicyManager
helpviewer_keywords: ICLRPolicyManager interface [.NET Framework hosting]
ms.assetid: 5c834aa1-f2db-408a-b230-c7bec093d364
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f3dd904184b730a5b0f5b2dfcac4197e708544d3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="iclrpolicymanager-interface"></a>Interfaccia ICLRPolicyManager
Fornisce metodi che consentono all'host specificare le azioni da intraprendere in caso di errori e i timeout dei criteri.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[SetActionOnFailure (metodo)](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md)|Specifica l'azione di criteri che Common language runtime (CLR) deve intraprendere quando si verifica l'errore specificato.|  
|[SetActionOnTimeout (metodo)](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md)|Specifica l'azione di criteri che CLR deve intraprendere quando timeout dell'operazione specificato.|  
|[SetDefaultAction (metodo)](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setdefaultaction-method.md)|Specifica l'azione di criteri che CLR deve essere eseguita quando si verifica l'operazione specificata.|  
|[SetTimeout (metodo)](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeout-method.md)|Imposta un valore di timeout per l'operazione specificata.|  
|[SetTimeoutAndAction (metodo)](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeoutandaction-method.md)|Imposta un valore di timeout per l'operazione specificata e specifica l'azione di criteri che CLR deve essere eseguita quando l'operazione viene eseguita.|  
|[SetUnhandledExceptionPolicy (metodo)](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setunhandledexceptionpolicy-method.md)|Specifica il comportamento di CLR quando si verifica un'eccezione non gestita.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Mscoree. H  
  
 **Libreria:** inclusa come risorsa in MSCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [EClrFailure (enumerazione)](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)  
 [Enumerazione EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)  
 [EPolicyAction (enumerazione)](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)  
 [ICLRControl (interfaccia)](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
