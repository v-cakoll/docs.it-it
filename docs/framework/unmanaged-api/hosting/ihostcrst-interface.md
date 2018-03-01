---
title: Interfaccia IHostCrst
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3a9ed2b390ad741d90f9179ef5101d328d3b639d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ihostcrst-interface"></a>Interfaccia IHostCrst
Serve come rappresentazione dell'host di una sezione critica di threading.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo Enter](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-enter-method.md)|Entra nella sezione critica.|  
|[Metodo Leave](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-leave-method.md)|Esce dalla sezione critica.|  
|[Metodo SetSpinCount](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-setspincount-method.md)|Imposta il conteggio di selezione per la sezione critica.|  
|[Metodo TryEnter](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-tryenter-method.md)|Tenta di accedere immediatamente sezione critica e i report l'esito.|  
  
## <a name="remarks"></a>Note  
 `IHostCrst`consente a common language runtime (CLR) per comunicare direttamente con la rappresentazione dell'host di una sezione critica, anziché utilizzare le funzioni Win32, ad esempio `EnterCriticalSection` o `LeaveCriticalSection`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Mscoree. H  
  
 **Libreria:** inclusa come risorsa in MSCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [Interfaccia IHostSyncManager](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)  
 [Interfacce di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
