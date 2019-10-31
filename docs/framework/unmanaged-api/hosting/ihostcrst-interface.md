---
title: Interfaccia IHostCrst
ms.date: 03/30/2017
api_name:
- IHostCrst
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostCrst
helpviewer_keywords:
- IHostCrst interface [.NET Framework hosting]
ms.assetid: ac298ebd-0815-47e4-a823-30b31baab903
topic_type:
- apiref
ms.openlocfilehash: 108492ba298e9f8429b2acd890ab3404365bc602
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130519"
---
# <a name="ihostcrst-interface"></a>Interfaccia IHostCrst
Funge da rappresentazione dell'host di una sezione critica per il Threading.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo Enter](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-enter-method.md)|Immette la sezione critica.|  
|[Metodo Leave](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-leave-method.md)|Lascia la sezione critica.|  
|[Metodo SetSpinCount](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-setspincount-method.md)|Imposta il numero di spin per la sezione critica.|  
|[Metodo TryEnter](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-tryenter-method.md)|Tenta di immettere la sezione critica e segnala immediatamente l'esito positivo o negativo.|  
  
## <a name="remarks"></a>Note  
 `IHostCrst` consente al Common Language Runtime (CLR) di comunicare direttamente con la rappresentazione dell'host di una sezione critica, anziché usare funzioni Win32 come `EnterCriticalSection` o `LeaveCriticalSection`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [Interfaccia IHostSyncManager](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
- [Interfacce di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
