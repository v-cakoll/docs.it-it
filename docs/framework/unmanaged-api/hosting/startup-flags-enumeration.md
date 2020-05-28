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
ms.openlocfilehash: b4694efffa0a3dd6fed1f97fc2359c5eb335d440
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84006415"
---
# <a name="startup_flags-enumeration"></a>Enumerazione STARTUP_FLAGS
Contiene valori che indicano il comportamento di avvio del Common Language Runtime (CLR). Per impostazione predefinita, Garbage Collection non è simultanea e solo la libreria di classi di base viene caricata nell'area indipendente dal dominio.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
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
|`STARTUP_CONCURRENT_GC`|Specifica che deve essere utilizzata la Garbage Collection simultanea. Se il chiamante richiede la compilazione del server e la Garbage Collection simultanea in un computer a processore singolo, vengono eseguite invece le Garbage Collection di compilazione e non simultanee della workstation. **Nota:**  La Garbage Collection simultanea non è supportata nelle applicazioni che eseguono l'emulatore WOW64 x86 nei sistemi a 64 bit che implementano l'architettura Intel Itanium (denominata in precedenza IA-64). Per ulteriori informazioni sull'utilizzo di WOW64 in sistemi Windows a 64 bit, vedere [esecuzione di applicazioni a 32 bit](/windows/desktop/WinProg64/running-32-bit-applications).|  
|`STARTUP_LOADER_OPTIMIZATION_MASK`|Specifica che deve essere eseguita l'ottimizzazione del caricatore.|  
|`STARTUP_LOADER_OPTIMIZATION_SINGLE_DOMAIN`|Specifica che nessun assembly viene caricato come indipendente dal dominio.|  
|`STARTUP_LOADER_OPTIMIZATION_MULTI_DOMAIN`|Specifica che tutti gli assembly vengono caricati come indipendenti dal dominio.|  
|`STARTUP_LOADER_OPTIMIZATION_MULTI_DOMAIN_HOST`|Specifica che tutti gli assembly con nome sicuro vengono caricati come indipendenti dal dominio.|  
|`STARTUP_LOADER_SAFEMODE`|Specifica che i criteri della versione CLR non verranno applicati alla versione passata. Verrà caricata la versione esatta specificata di CLR. Lo shim non valuta i criteri per determinare la versione compatibile più recente.|  
|`STARTUP_LOADER_SETPREFERENCE`|Specifica che verrà impostato il runtime preferito, ma non effettivamente avviato.|  
|`STARTUP_SERVER_GC`|Specifica che verrà utilizzato il server Garbage Collection.|  
|`STARTUP_HOARD_GC_VM`|Specifica che Garbage Collection manterrà l'indirizzo virtuale usato.|  
|`STARTUP_SINGLE_VERSION_HOSTING_INTERFACE`|Specifica che la combinazione di un'interfaccia di hosting non sarà consentita.|  
|`STARTUP_LEGACY_IMPERSONATION`|Specifica che la rappresentazione non deve fluire tra i punti asincroni per impostazione predefinita.|  
|`STARTUP_DISABLE_COMMITTHREADSTACK`|Specifica che non deve essere eseguito il commit dello stack di thread completo all'avvio dell'esecuzione del thread.|  
|`STARTUP_ALWAYSFLOW_IMPERSONATION`|Specifica che le rappresentazioni gestite e le rappresentazioni realizzate tramite platform invoke propagano tra punti asincroni. Per impostazione predefinita, solo le rappresentazioni gestite si propagano tra punti asincroni.|  
|`STARTUP_TRIM_GC_COMMIT`|Specifica che Garbage Collection utilizzerà uno spazio meno vincolato quando la memoria di sistema è insufficiente. Vedere `gcTrimCommitOnLowMemory` in [ottimizzazione per l'hosting Web condiviso](../../../standard/garbage-collection/optimization-for-shared-web-hosting.md).|  
|`STARTUP_ETW`|Specifica che traccia eventi per Windows (ETW) è abilitato per gli eventi Common Language Runtime. A partire da Windows Vista, la traccia eventi è sempre abilitata, quindi questo flag non ha alcun effetto. Vedere [controllo .NET Framework registrazione](../../performance/controlling-logging.md).|  
|`STARTUP_ARM`|Specifica che il monitoraggio delle risorse del dominio applicazione è abilitato. Vedere la <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=nameWithType> proprietà e l' [ \<appDomainResourceMonitoring> elemento](../../configure-apps/file-schema/runtime/appdomainresourcemonitoring-element.md).|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazioni di hosting](hosting-enumerations.md)
