---
title: Enumerazione STARTUP_FLAGS
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: STARTUP_FLAGS
api_location: mscoree.dll
api_type: COM
f1_keywords: STARTUP_FLAGS
helpviewer_keywords: STARTUP_FLAGS enumeration [.NET Framework hosting]
ms.assetid: 4f043594-0c45-4bc6-988e-a6793f0d8d06
topic_type: apiref
caps.latest.revision: "22"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ebfb45e6d568b4fa1db209264e02332df636474f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="startupflags-enumeration"></a>Enumerazione STARTUP_FLAGS
Contiene valori che indicano il comportamento di avvio di common language runtime (CLR). Per impostazione predefinita, la garbage collection è non simultanea e solo la libreria di classi di base viene caricata nell'area indipendente dal dominio.  
  
## <a name="syntax"></a>Sintassi  
  
```  
typedef enum {  
    STARTUP_CONCURRENT_GC                         = 0x1,  
    STARTUP_LOADER_OPTIMIZATION_MASK              = 0x3<<1,  
    STARTUP_LOADER_OPTIMIZATION_SINGLE_DOMAIN     = 0x1<<1,  
    STARTUP_LOADER_OPTIMIZATION_MULTI_DOMAIN      = 0x2<<1,  
    STARTUP_LOADER_OPTIMIZATION_MULTI_DOMAIN_HOST = 0x3<<1,  
  
    STARTUP_LOADER_SAFEMODE                       = 0x10,  
    STARTUP_LOADER_SETPREFERENCE                  = 0x100,  
  
    STARTUP_SERVER_GC                             = 0x1000,  
    STARTUP_HOARD_GC_VM                           = 0x2000,  
  
    STARTUP_SINGLE_VERSION_HOSTING_INTERFACE      = 0x4000,  
    STARTUP_LEGACY_IMPERSONATION                  = 0x10000,  
    STARTUP_DISABLE_COMMITTHREADSTACK             = 0x20000,  
    STARTUP_ALWAYSFLOW_IMPERSONATION              = 0x40000,  
    STARTUP_TRIM_GC_COMMIT                        = 0x80000,  
  
    STARTUP_ETW                                   = 0x100000,  
    STARTUP_ARM                                   = 0x400000  
} STARTUP_FLAGS;  
```  
  
## <a name="members"></a>Membri  
  
|Membro|Descrizione|  
|------------|-----------------|  
|`STARTUP_CONCURRENT_GC`|Specifica che deve essere utilizzata la modalità simultanea. Se il chiamante chiede simultanea e il server in un computer a processore singolo, la compilazione di workstation e non simultanea della garbage collection vengono eseguite invece. **Nota:** garbage collection simultanea non è supportata nelle applicazioni che eseguono WOW64 x86 emulatore nei sistemi a 64 bit che implementano l'architettura Intel Itanium (IA-64 noto). Per ulteriori informazioni sull'utilizzo di WOW64 nei sistemi Windows a 64 bit, vedere [applicazioni in esecuzione a 32 bit](http://msdn.microsoft.com/library/windows/desktop/aa384249.aspx).|  
|`STARTUP_LOADER_OPTIMIZATION_MASK`|Specifica che l'ottimizzazione del caricatore dovrà essere eseguiti.|  
|`STARTUP_LOADER_OPTIMIZATION_SINGLE_DOMAIN`|Specifica che non gli assembly vengono caricati come indipendenti dal dominio.|  
|`STARTUP_LOADER_OPTIMIZATION_MULTI_DOMAIN`|Specifica che tutti gli assembly vengono caricati come indipendenti dal dominio.|  
|`STARTUP_LOADER_OPTIMIZATION_MULTI_DOMAIN_HOST`|Specifica che tutti gli assembly con nome sicuro vengono caricati come indipendenti dal dominio.|  
|`STARTUP_LOADER_SAFEMODE`|Specifica che i criteri di versione CLR non verranno applicati alla versione passata. Verrà caricato l'esatta versione specificata di CLR. Lo shim non valuta i criteri per determinare la versione compatibile più recente.|  
|`STARTUP_LOADER_SETPREFERENCE`|Specifica che il runtime preferito verrà impostato, ma non avviato.|  
|`STARTUP_SERVER_GC`|Specifica che verrà usata la garbage collection per server.|  
|`STARTUP_HOARD_GC_VM`|Specifica che l'operazione di garbage collection manterrà l'indirizzo virtuale utilizzato.|  
|`STARTUP_SINGLE_VERSION_HOSTING_INTERFACE`|Specifica che la combinazione di un'interfaccia di hosting non sono consentita.|  
|`STARTUP_LEGACY_IMPERSONATION`|Specifica che la rappresentazione non deve passare attraverso punti asincroni per impostazione predefinita.|  
|`STARTUP_DISABLE_COMMITTHREADSTACK`|Specifica che lo stack di thread completo non deve essere eseguito il commit quando il thread viene avviata l'esecuzione.|  
|`STARTUP_ALWAYSFLOW_IMPERSONATION`|Specifica che le rappresentazioni gestite e le rappresentazioni ottenute mediante platform invoke verrà passa attraverso punti asincroni. Per impostazione predefinita, solo gestito passano attraverso punti asincroni.|  
|`STARTUP_TRIM_GC_COMMIT`|Specifica che quando la memoria di sistema è insufficiente, la garbage collection utilizzerà meno spazio. Vedere `gcTrimCommitOnLowMemory` in [ottimizzazione per l'Hosting Web condiviso](../../../../docs/standard/garbage-collection/optimization-for-shared-web-hosting.md).|  
|`STARTUP_ETW`|Specifica che l'esecuzione di event tracing for Windows (ETW) è abilitato per gli eventi di common language runtime. A partire da Windows Vista, la traccia eventi è sempre abilitata, pertanto questo flag non ha alcun effetto. Vedere [controllo della registrazione di .NET Framework](../../../../docs/framework/performance/controlling-logging.md).|  
|`STARTUP_ARM`|Specifica che il monitoraggio delle risorse al dominio di applicazione è abilitato. Vedere il <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=nameWithType> proprietà e [ \<appDomainResourceMonitoring > elemento](../../../../docs/framework/configure-apps/file-schema/runtime/appdomainresourcemonitoring-element.md).|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Mscoree. H  
  
 **Libreria:** MSCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Enumerazioni di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
