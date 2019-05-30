---
title: Interfaccia ICLRGCManager
ms.date: 03/30/2017
api_name:
- ICLRGCManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRGCManager
helpviewer_keywords:
- ICLRGCManager interface [.NET Framework hosting]
ms.assetid: fb511c9b-3fe4-41b0-822a-6ba4a079d1f5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6e284f94ad0dac9523bd6267e7bc1034a079503d
ms.sourcegitcommit: 4735bb7741555bcb870d7b42964d3774f4897a6e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/30/2019
ms.locfileid: "66380301"
---
# <a name="iclrgcmanager-interface"></a>Interfaccia ICLRGCManager
Fornisce metodi che consentono a un host interagire con il sistema di common language runtime garbage collection.  
  
> [!NOTE]
>  A partire da .NET Framework 4.5, è possibile usare la [ICLRGCManager2::SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md) metodo per impostare le dimensioni di un segmento di garbage collection e le dimensioni massime della generazione del sistema di garbage collection 0 sui valori maggiore il `DWORD` limite imposto per il [SetGCStartupLimits](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-setgcstartuplimits-method.md) (metodo).  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo Collect](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-collect-method.md)|Forza un'operazione di garbage collection per la generazione specificata.|  
|[Metodo GetStats](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-getstats-method.md)|Ottiene un set di statistiche correnti sul sistema di garbage collection.|  
|[Metodo SetGCStartupLimits](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-setgcstartuplimits-method.md)|Imposta le dimensioni di un segmento di garbage collection e le dimensioni massime della generazione del sistema di garbage collection 0.|  
  
## <a name="remarks"></a>Note  
 Common language runtime (CLR) implementa il meccanismo di garbage collection con managed <xref:System.GC> tipo. Per altre informazioni sul sistema di garbage collection, vedere [Garbage Collection](../../../../docs/standard/garbage-collection/index.md).  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE.h  
  
 **Libreria:** Inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Gestione automatica della memoria](../../../../docs/standard/automatic-memory-management.md)
- [Struttura COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)
- [Interfaccia ICLRControl](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [Interfacce di hosting CLR](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)
- [Interfacce di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [Hosting](../../../../docs/framework/unmanaged-api/hosting/index.md)
