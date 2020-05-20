---
title: Interfaccia ICLRAppDomainResourceMonitor
ms.date: 03/30/2017
api_name:
- ICLRAppDomainResourceMonitor
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAppDomainResourceMonitor
helpviewer_keywords:
- ICLRAppDomainResourceMonitor interface [.NET Framework hosting]
ms.assetid: 72fa83a1-8997-41d7-b355-ab177a24a303
topic_type:
- apiref
ms.openlocfilehash: 08dc0f0891d960cb7b402b30455e606aaff7bcea
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616008"
---
# <a name="iclrappdomainresourcemonitor-interface"></a>Interfaccia ICLRAppDomainResourceMonitor
Fornisce metodi che controllano l'utilizzo della CPU e della memoria del dominio dell'applicazione.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo GetCurrentAllocated](iclrappdomainresourcemonitor-getcurrentallocated-method.md)|Ottiene le dimensioni totali, in byte, di tutte le allocazioni di memoria effettuate dal dominio applicazione da quando è stato creato, senza sottrarre memoria che è stata sottoposta a Garbage Collection.|  
|[Metodo GetCurrentSurvived](iclrappdomainresourcemonitor-getcurrentsurvived-method.md)|Ottiene il numero di byte esclusi dall'ultimo blocco completo Garbage Collection e a cui fa riferimento il dominio applicazione corrente.|  
|[Metodo GetCurrentCpuTime](iclrappdomainresourcemonitor-getcurrentcputime-method.md)|Ottiene il tempo totale del processore utilizzato da tutti i thread durante l'esecuzione nel dominio dell'applicazione corrente, dal momento in cui è stato creato il dominio dell'applicazione.|  
  
## <a name="remarks"></a>Osservazioni  
 L' `ICLRAppDomainResourceMonitor` interfaccia fornisce funzionalità simili alle seguenti proprietà gestite:  
  
- <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=nameWithType>  
  
- <xref:System.AppDomain.MonitoringTotalProcessorTime%2A?displayProperty=nameWithType>  
  
- <xref:System.AppDomain.MonitoringTotalAllocatedMemorySize%2A?displayProperty=nameWithType>  
  
- <xref:System.AppDomain.MonitoringSurvivedProcessMemorySize%2A?displayProperty=nameWithType>  
  
- <xref:System.AppDomain.MonitoringSurvivedMemorySize%2A?displayProperty=nameWithType>  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** Metahost. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [\<Elemento> appDomainResourceMonitoring](../../configure-apps/file-schema/runtime/appdomainresourcemonitoring-element.md)
- [Monitoraggio delle risorse del dominio applicazione](../../../standard/garbage-collection/app-domain-resource-monitoring.md)
- [Interfacce di hosting](hosting-interfaces.md)
- [Hosting](index.md)
