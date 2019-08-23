---
title: Interfaccia ICLRGCManager2
ms.date: 03/30/2017
api_name:
- ICLRGCManager2
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRGCManager2
helpviewer_keywords:
- ICLRGCManager2 interface [.NET Framework hosting]
ms.assetid: 4b5ffd7b-9ad7-41cd-9bba-34030ae3da7e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c54707d4c767fbb644ed892767be8351d2fd95b5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966193"
---
# <a name="iclrgcmanager2-interface"></a>Interfaccia ICLRGCManager2
Fornisce metodi che consentono a un host di interagire con il sistema di Garbage Collection del Common Language Runtime.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|DESCRIZIONE|  
|------------|-----------------|  
|[Metodo SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md)|Imposta la dimensione di un segmento di Garbage Collection e la dimensione massima della generazione 0 del sistema Garbage Collection. Abilita la generazione 0 e le dimensioni dei `DWORD`segmenti maggiori di.|  
  
## <a name="remarks"></a>Note  
 Questa interfaccia eredita dall' [Interfaccia ICLRGCManager](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md).  
  
 Il Common Language Runtime (CLR) implementa il meccanismo Garbage Collection con il tipo <xref:System.GC> gestito. Per ulteriori informazioni sul sistema di Garbage Collection, vedere [Garbage Collection](../../../standard/garbage-collection/index.md).  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Gestione automatica della memoria](../../../standard/automatic-memory-management.md)
- [Struttura COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)
- [Interfaccia ICLRControl](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [Interfacce di hosting CLR aggiunte in .NET Framework 4 e 4.5](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)
- [Interfacce di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [Hosting](../../../../docs/framework/unmanaged-api/hosting/index.md)
