---
title: Interfaccia ICLRGCManager
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRGCManager
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRGCManager
helpviewer_keywords: ICLRGCManager interface [.NET Framework hosting]
ms.assetid: fb511c9b-3fe4-41b0-822a-6ba4a079d1f5
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7215ce1423e8541b23daae7b9e051ade6e25f1b7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="iclrgcmanager-interface"></a>Interfaccia ICLRGCManager
Fornisce metodi che consentono a un host di interagire con sistema di garbage collection di common language runtime.  
  
> [!NOTE]
>  A partire dal [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], è possibile utilizzare il [iclrgcmanager2:: Setgcstartuplimitsex](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md) per impostare le dimensioni di un segmento di garbage collection e la dimensione massima della generazione del sistema di garbage collection 0 su valori di maggiore (metodo) più il `DWORD` limite imposto dal [SetGCStartupLimits](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-setgcstartuplimits-method.md) metodo.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Collect (metodo)](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-collect-method.md)|Forza un'operazione di garbage collection per la generazione specificata.|  
|[GetStats (metodo)](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-getstats-method.md)|Ottiene un set di statistiche sul sistema di garbage collection.|  
|[SetGCStartupLimits (metodo)](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-setgcstartuplimits-method.md)|Imposta le dimensioni di un segmento di garbage collection e la dimensione massima della generazione del sistema di garbage collection 0.|  
  
## <a name="remarks"></a>Note  
 Common language runtime (CLR) implementa il meccanismo di garbage collection con gestito <xref:System.GC> tipo. Per ulteriori informazioni sul sistema di garbage collection, vedere [Garbage Collection](../../../../docs/standard/garbage-collection/index.md).  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Mscoree. H  
  
 **Libreria:** inclusa come risorsa in MSCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Gestione automatica della memoria](../../../../docs/standard/automatic-memory-management.md)  
 [COR_GC_STATS (struttura)](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)  
 [ICLRControl (interfaccia)](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [Interfacce di Hosting CLR](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)  
 [Interfacce di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [Hosting](../../../../docs/framework/unmanaged-api/hosting/index.md)
