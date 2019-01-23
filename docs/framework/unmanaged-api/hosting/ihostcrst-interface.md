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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 34a911668db09b255282833cec3e6272b315373b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54618659"
---
# <a name="ihostcrst-interface"></a>Interfaccia IHostCrst
Serve come rappresentazione di una sezione critica per il threading dall'host.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo Enter](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-enter-method.md)|Entra nella sezione critica.|  
|[Metodo Leave](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-leave-method.md)|Esce dalla sezione critica.|  
|[Metodo SetSpinCount](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-setspincount-method.md)|Imposta il conteggio della rotazione della sezione critica.|  
|[Metodo TryEnter](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-tryenter-method.md)|Tenta di accedere immediatamente la sezione critica e report esito positivo o negativo.|  
  
## <a name="remarks"></a>Note  
 `IHostCrst` consente a common language runtime (CLR) per comunicare direttamente con rappresentazione dell'host di una sezione critica, invece di usare le funzioni Win32, ad esempio `EnterCriticalSection` o `LeaveCriticalSection`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE.h  
  
 **Libreria:** Inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Interfaccia ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [Interfaccia IHostSyncManager](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
- [Interfacce di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
