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
ms.openlocfilehash: 76d1071ddde1509f16fd786afa4c05c05224d051
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966216"
---
# <a name="iclrgcmanager-interface"></a>Interfaccia ICLRGCManager
Fornisce metodi che consentono a un host di interagire con il sistema di Garbage Collection del Common Language Runtime.  
  
> [!NOTE]
> A partire da .NET Framework 4,5, è possibile usare il metodo [ICLRGCManager2:: SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md) per impostare le dimensioni di un segmento di Garbage Collection e le dimensioni massime della generazione 0 del sistema di Garbage Collection su valori maggiori di `DWORD`limite imposto dal metodo [SetGCStartupLimits](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-setgcstartuplimits-method.md) .  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo Collect](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-collect-method.md)|Impone un Garbage Collection per la generazione specificata.|  
|[Metodo GetStats](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-getstats-method.md)|Ottiene un set di statistiche correnti sul sistema di Garbage Collection.|  
|[Metodo SetGCStartupLimits](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-setgcstartuplimits-method.md)|Imposta la dimensione di un segmento di Garbage Collection e la dimensione massima della generazione 0 del sistema Garbage Collection.|  
  
## <a name="remarks"></a>Note  
 Il Common Language Runtime (CLR) implementa il meccanismo Garbage Collection con il tipo <xref:System.GC> gestito. Per ulteriori informazioni sul sistema di Garbage Collection, vedere [Garbage Collection](../../../standard/garbage-collection/index.md).  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Gestione automatica della memoria](../../../standard/automatic-memory-management.md)
- [Struttura COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)
- [Interfaccia ICLRControl](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [Interfacce di hosting CLR](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)
- [Interfacce di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [Hosting](../../../../docs/framework/unmanaged-api/hosting/index.md)
