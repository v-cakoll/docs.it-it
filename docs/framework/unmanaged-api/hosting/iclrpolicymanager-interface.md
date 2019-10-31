---
title: Interfaccia ICLRPolicyManager
ms.date: 03/30/2017
api_name:
- ICLRPolicyManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRPolicyManager
helpviewer_keywords:
- ICLRPolicyManager interface [.NET Framework hosting]
ms.assetid: 5c834aa1-f2db-408a-b230-c7bec093d364
topic_type:
- apiref
ms.openlocfilehash: 59aa904d4c67326b60381d3476eaab179d7fa42b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140800"
---
# <a name="iclrpolicymanager-interface"></a>Interfaccia ICLRPolicyManager
Fornisce metodi che consentono all'host di specificare le azioni dei criteri da intraprendere in caso di errori e timeout.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo SetActionOnFailure](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md)|Specifica l'azione del criterio che il Common Language Runtime (CLR) deve eseguire quando si verifica l'errore specificato.|  
|[Metodo SetActionOnTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md)|Specifica l'azione del criterio che CLR deve eseguire quando si verifica il timeout dell'operazione specificata.|  
|[Metodo SetDefaultAction](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setdefaultaction-method.md)|Specifica l'azione del criterio che CLR deve eseguire quando si verifica l'operazione specificata.|  
|[Metodo SetTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeout-method.md)|Imposta un valore di timeout per l'operazione specificata.|  
|[Metodo SetTimeoutAndAction](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeoutandaction-method.md)|Imposta un valore di timeout per l'operazione specificata e specifica l'azione del criterio che CLR deve eseguire quando si verifica l'operazione.|  
|[Metodo SetUnhandledExceptionPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setunhandledexceptionpolicy-method.md)|Specifica il comportamento di CLR quando si verifica un'eccezione non gestita.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazione EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)
- [Enumerazione EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [Enumerazione EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [Interfaccia ICLRControl](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
