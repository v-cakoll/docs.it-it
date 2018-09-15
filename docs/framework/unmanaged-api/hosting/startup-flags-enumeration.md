---
title: Enumerazione STARTUP_FLAGS
ms.date: 03/30/2017
api_name:
- STARTUP_FLAGS
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- STARTUP_FLAGS
helpviewer_keywords:
- STARTUP_FLAGS enumeration [.NET Framework hosting]
ms.assetid: 4f043594-0c45-4bc6-988e-a6793f0d8d06
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f4680187de7318a6438bf6a5e6bd7c5f3acd05c2
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/14/2018
ms.locfileid: "45624814"
---
# <a name="startupflags-enumeration"></a>Enumerazione STARTUP_FLAGS
Contiene valori che indicano il comportamento di avvio di common language runtime (CLR). Per impostazione predefinita, la garbage collection è non simultanea e solo la libreria di classi di base viene caricata nell'area indipendenti dal dominio.  
  
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
|`STARTUP_CONCURRENT_GC`|Specifica che deve essere utilizzata garbage collection simultanea. Se il chiamante richiede garbage collection simultanea e il server su un computer a processore singolo, la build di workstation e non simultanea garbage collection vengono eseguite in alternativa. **Nota:** garbage collection simultanea non è supportata nelle applicazioni che eseguono il WOW64 x86 dell'emulatore su sistemi a 64 bit che implementino l'architettura Intel Itanium (in precedenza denominato IA-64). Per altre informazioni sull'utilizzo di WOW64 nei sistemi Windows a 64 bit, vedere [delle applicazioni in esecuzione a 32 bit](/windows/desktop/WinProg64/running-32-bit-applications).|  
|`STARTUP_LOADER_OPTIMIZATION_MASK`|Specifica che l'ottimizzazione del caricatore deve verificarsi.|  
|`STARTUP_LOADER_OPTIMIZATION_SINGLE_DOMAIN`|Specifica che nessun assembly viene caricato come indipendenti dal dominio.|  
|`STARTUP_LOADER_OPTIMIZATION_MULTI_DOMAIN`|Specifica che tutti gli assembly vengono caricati come indipendenti dal dominio.|  
|`STARTUP_LOADER_OPTIMIZATION_MULTI_DOMAIN_HOST`|Specifica che tutti gli assembly con nome sicuro vengono caricati come indipendenti dal dominio.|  
|`STARTUP_LOADER_SAFEMODE`|Specifica che i criteri di versione CLR non essere applicati alla versione passata. L'esatta versione specificata di CLR verrà caricato. Lo shim non valutare i criteri per determinare la versione più recente compatibile.|  
|`STARTUP_LOADER_SETPREFERENCE`|Specifica che il runtime preferito verrà impostato, ma non effettivamente avviato.|  
|`STARTUP_SERVER_GC`|Specifica che verrà usata la garbage collection per server.|  
|`STARTUP_HOARD_GC_VM`|Specifica che la garbage collection manterrà l'indirizzo virtuale usato.|  
|`STARTUP_SINGLE_VERSION_HOSTING_INTERFACE`|Specifica che si unisce un'interfaccia di hosting non sarà possibile.|  
|`STARTUP_LEGACY_IMPERSONATION`|Specifica che la rappresentazione non deve passare attraverso punti asincroni per impostazione predefinita.|  
|`STARTUP_DISABLE_COMMITTHREADSTACK`|Specifica che lo stack di thread completo non deve essere eseguito il commit quando viene avviato il thread in esecuzione.|  
|`STARTUP_ALWAYSFLOW_IMPERSONATION`|Specifica che rappresentazioni gestite e rappresentazioni ottenute tramite platform invoke verrà passa attraverso punti asincroni. Per impostazione predefinita, solo le rappresentazioni gestite transiterà attraverso punti asincroni.|  
|`STARTUP_TRIM_GC_COMMIT`|Specifica che la garbage collection utilizzerà meno spazio quando la memoria di sistema è insufficiente. Visualizzare `gcTrimCommitOnLowMemory` nelle [ottimizzazione per l'Hosting Web condiviso](../../../../docs/standard/garbage-collection/optimization-for-shared-web-hosting.md).|  
|`STARTUP_ETW`|Specifica che di event tracing for Windows (ETW) è abilitata per gli eventi di common language runtime. A partire da Windows Vista, la traccia eventi è sempre abilitata, pertanto questo flag non ha alcun effetto. Visualizzare [controllo della registrazione di .NET Framework](../../../../docs/framework/performance/controlling-logging.md).|  
|`STARTUP_ARM`|Specifica che il monitoraggio delle risorse al dominio di applicazione è abilitata. Vedere le <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=nameWithType> proprietà e [ \<appDomainResourceMonitoring > elemento](../../../../docs/framework/configure-apps/file-schema/runtime/appdomainresourcemonitoring-element.md).|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Mscoree. H  
  
 **Libreria:** Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Enumerazioni di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
