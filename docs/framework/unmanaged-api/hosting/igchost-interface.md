---
title: Interfaccia IGCHost
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IGCHost
api_location: mscoree.dll
api_type: COM
f1_keywords: IGCHost
helpviewer_keywords: IGCHost interface [.NET Framework hosting]
ms.assetid: 9ad70ffd-6963-4ab2-8c84-3d86c3fb8deb
topic_type: apiref
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 5c0f398c09569a855291a1565ce63b513161a803
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="igchost-interface"></a>Interfaccia IGCHost
Fornisce metodi per ottenere informazioni sul sistema di garbage collection e per controllare alcuni aspetti dell'operazione di garbage collection.  
  
> [!NOTE]
>  A partire dal [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], è possibile utilizzare il [igchost2:: Setgcstartuplimitsex](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) metodo per impostare le dimensioni di un segmento di garbage collection e la dimensione massima della generazione del sistema di garbage collection 0 su valori minori di `DWORD` limite imposto dal [SetGCStartupLimits](../../../../docs/framework/unmanaged-api/hosting/igchost-setgcstartuplimits-method.md) metodo.  
  
> [!NOTE]
>  Questa interfaccia è solo utilizzo esperto di dominio. Le prestazioni di un'applicazione può influire se utilizzato in modo non corretto.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Collect (metodo)](../../../../docs/framework/unmanaged-api/hosting/igchost-collect-method.md)|Forza una raccolta per la generazione specificata, indipendentemente dallo stato dell'operazione di garbage collection corrente.|  
|[GetStats (metodo)](../../../../docs/framework/unmanaged-api/hosting/igchost-getstats-method.md)|Ottiene le statistiche per lo stato corrente del sistema di garbage collection.|  
|[GetThreadStats (metodo)](../../../../docs/framework/unmanaged-api/hosting/igchost-getthreadstats-method.md)|Ottiene le statistiche per ogni thread di garbage collection.|  
|[SetGCStartupLimits (metodo)](../../../../docs/framework/unmanaged-api/hosting/igchost-setgcstartuplimits-method.md)|Imposta le dimensioni del segmento e la dimensione massima per la generazione 0.|  
|[SetVirtualMemLimit (metodo)](../../../../docs/framework/unmanaged-api/hosting/igchost-setvirtualmemlimit-method.md)|Imposta la dimensione massima di memoria virtuale del runtime.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** GCHost. idl, GCHost. H  
  
 **Libreria:** inclusa come risorsa in MSCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfacce di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [Coclasse CorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)
