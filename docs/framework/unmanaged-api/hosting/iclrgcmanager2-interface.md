---
title: Interfaccia ICLRGCManager2
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRGCManager2
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRGCManager2
helpviewer_keywords: ICLRGCManager2 interface [.NET Framework hosting]
ms.assetid: 4b5ffd7b-9ad7-41cd-9bba-34030ae3da7e
topic_type: apiref
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b025ec31e3797fec3ac184929f1274cb5f68501b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="iclrgcmanager2-interface"></a>Interfaccia ICLRGCManager2
Fornisce metodi che consentono a un host di interagire con sistema di garbage collection di common language runtime.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[SetGCStartupLimitsEx (metodo)](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md)|Imposta le dimensioni di un segmento di garbage collection e la dimensione massima della generazione del sistema di garbage collection 0. Consente di generazione 0 e dei segmenti maggiori `DWORD`.|  
  
## <a name="remarks"></a>Note  
 Questa interfaccia eredita il [ICLRGCManager (interfaccia)](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md).  
  
 Common language runtime (CLR) implementa il meccanismo di garbage collection con gestito <xref:System.GC> tipo. Per ulteriori informazioni sul sistema di garbage collection, vedere [Garbage Collection](../../../../docs/standard/garbage-collection/index.md).  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Mscoree. H  
  
 **Libreria:** inclusa come risorsa in MSCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Gestione automatica della memoria](../../../../docs/standard/automatic-memory-management.md)  
 [COR_GC_STATS (struttura)](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)  
 [ICLRControl (interfaccia)](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [Interfacce di Hosting CLR aggiunte in .NET Framework 4 e 4.5](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)  
 [Interfacce di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [Hosting](../../../../docs/framework/unmanaged-api/hosting/index.md)
