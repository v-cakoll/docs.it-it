---
title: Interfaccia IGCHost
ms.date: 03/30/2017
api_name:
- IGCHost
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IGCHost
helpviewer_keywords:
- IGCHost interface [.NET Framework hosting]
ms.assetid: 9ad70ffd-6963-4ab2-8c84-3d86c3fb8deb
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 167e2477e5185112408793e145bc5a4fabea7fc8
ms.sourcegitcommit: 4735bb7741555bcb870d7b42964d3774f4897a6e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/30/2019
ms.locfileid: "66377622"
---
# <a name="igchost-interface"></a>Interfaccia IGCHost
Fornisce metodi di recupero di informazioni sul sistema di garbage collection e di controllo di alcuni aspetti del processo di garbage collection.  
  
> [!NOTE]
>  A partire da .NET Framework 4.5, è possibile usare la [IGCHost2::SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) metodo per impostare le dimensioni di un segmento di garbage collection e le dimensioni massime della generazione del sistema di garbage collection 0 sui valori maggiore di il `DWORD` limite imposto per la [SetGCStartupLimits](../../../../docs/framework/unmanaged-api/hosting/igchost-setgcstartuplimits-method.md) (metodo).  
  
> [!NOTE]
>  Questa interfaccia è per solo all'utilizzo degli esperti. Se usato in modo corretto le prestazioni di un'applicazione può influire sulla.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo Collect](../../../../docs/framework/unmanaged-api/hosting/igchost-collect-method.md)|Forza una raccolta Garbage Collection per la generazione specificata, indipendentemente dallo stato di garbage collection corrente.|  
|[Metodo GetStats](../../../../docs/framework/unmanaged-api/hosting/igchost-getstats-method.md)|Ottiene le statistiche per lo stato corrente del sistema di garbage collection.|  
|[Metodo GetThreadStats](../../../../docs/framework/unmanaged-api/hosting/igchost-getthreadstats-method.md)|Ottiene le statistiche per ogni thread di garbage collection.|  
|[Metodo SetGCStartupLimits](../../../../docs/framework/unmanaged-api/hosting/igchost-setgcstartuplimits-method.md)|Imposta le dimensioni del segmento e le dimensioni massime per la generazione 0.|  
|[Metodo SetVirtualMemLimit](../../../../docs/framework/unmanaged-api/hosting/igchost-setvirtualmemlimit-method.md)|Imposta la dimensione massima di memoria virtuale del runtime.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** GCHost.idl, GCHost.h  
  
 **Libreria:** Inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [Coclasse CorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)
