---
title: Funzione CorBindToRuntimeEx
ms.date: 03/30/2017
api_name:
- CorBindToRuntimeEx
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- CorBindToRuntimeEx
helpviewer_keywords:
- CorBindToRuntimeEx function [.NET Framework hosting]
ms.assetid: aae9fb17-5d01-41da-9773-1b5b5b642d81
topic_type:
- apiref
ms.openlocfilehash: 3520af5f55f43183920dce7fbd24b70359c023a2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176500"
---
# <a name="corbindtoruntimeex-function"></a>Funzione CorBindToRuntimeEx
Consente agli host non gestiti di caricare Common Language Runtime (CLR) in un processo. Le funzioni [CorBindToRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md) e `CorBindToRuntimeEx` eseguono `CorBindToRuntimeEx` la stessa operazione, ma la funzione consente di impostare flag per specificare il comportamento di CLR.  
  
 Questa funzione è stata deprecata in .NET Framework 4.  
  
 Questa funzione accetta un set di parametri che consentono a un host di eseguire le operazioni seguenti:This function takes a set of parameters that allow a host to do the following:  
  
- Specificare la versione del runtime che verrà caricata.  
  
- Indicare se la build del server o della workstation deve essere caricata.  
  
- Controllare se viene eseguita l'operazione di Garbage Collection simultanea o non simultanea.  
  
> [!NOTE]
> La Garbage Collection simultanea non è supportata nelle applicazioni che eseguono l'emulatore WOW64 x86 su sistemi a 64 bit che implementano l'architettura Intel Itanium (precedentemente denominata IA-64). Per ulteriori informazioni sull'utilizzo di WOW64 nei sistemi Windows a 64 bit, vedere Esecuzione di applicazioni a [32 bit](/windows/desktop/WinProg64/running-32-bit-applications).  
  
- Controllare se gli assembly vengono caricati come indipendenti dal dominio.  
  
- Ottenere un puntatore a interfaccia a un [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) che può essere utilizzato per impostare opzioni aggiuntive per la configurazione di un'istanza di CLR prima che venga avviato.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT CorBindToRuntimeEx (  
    [in]  LPCWSTR      pwszVersion,
    [in]  LPCWSTR      pwszBuildFlavor,
    [in]  DWORD        startupFlags,
    [in]  REFCLSID     rclsid,
    [in]  REFIID       riid,
    [out] LPVOID FAR  *ppv  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pwszVersion`  
 [in] Stringa che descrive la versione di CLR che si desidera caricare.  
  
 Un numero di versione in .NET Framework è costituito da quattro parti separate da punti: *major.minor.build.revision*. La stringa `pwszVersion` passata come deve iniziare con il carattere "v" seguito dalle prime tre parti del numero di versione (ad esempio, "v1.0.1529").  
  
 Alcune versioni di CLR vengono installate con un'istruzione dei criteri che specifica la compatibilità con le versioni precedenti di CLR. Per impostazione predefinita, lo `pwszVersion` shim di avvio valuta rispetto alle istruzioni dei criteri e carica la versione più recente del runtime compatibile con la versione richiesta. Un host può forzare lo shim a ignorare `pwszVersion` la valutazione dei `STARTUP_LOADER_SAFEMODE` criteri `startupFlags` e caricare la versione esatta specificata in passando un valore di per il parametro, come descritto di seguito.  
  
 Se il chiamante `pwszVersion`specifica `CorBindToRuntimeEx` null per , identifica il set di runtime installati i cui numeri di versione sono inferiori al runtime di .NET Framework 4 e carica la versione più recente del runtime da tale set. Non caricherà .NET Framework 4 o versione successiva e non riesce se non è installata alcuna versione precedente. Si noti che il passaggio di null non fornisce all'host alcun controllo sulla versione del runtime caricata. Anche se questo approccio può essere appropriato in alcuni scenari, è consigliabile che l'host fornisse una versione specifica da caricare.  
  
 `pwszBuildFlavor`  
 [in] Stringa che specifica se caricare il server o la build della workstation di CLR. I valori validi sono `svr` e `wks`. La build server è ottimizzata per sfruttare più processori per le operazioni di Garbage Collection e la build workstation è ottimizzata per le applicazioni client in esecuzione su un computer a processore singolo.  
  
 Se `pwszBuildFlavor` è impostato su null, viene caricata la build della workstation. Quando viene eseguita su un computer a processore singolo, la build della workstation viene sempre caricata, anche se `pwszBuildFlavor` è impostata su `svr`. Tuttavia, `pwszBuildFlavor` se `svr` è impostata su e viene specificata `startupFlags` l'operazione di Garbage Collection simultanea (vedere la descrizione del parametro), viene caricata la compilazione del server.  
  
 `startupFlags`  
 [in] Combinazione di valori dell'enumerazione [STARTUP_FLAGS.](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) Questi flag controllano la Garbage Collection simultanea, il `pwszVersion` codice indipendente dal dominio e il comportamento del parametro. Il valore predefinito è dominio singolo se non è impostato alcun flag. I valori seguenti sono validi:  
  
- `STARTUP_CONCURRENT_GC`  
  
- `STARTUP_LOADER_OPTIMIZATION_SINGLE_DOMAIN`  
  
- `STARTUP_LOADER_OPTIMIZATION_MULTI_DOMAIN`  
  
- `STARTUP_LOADER_OPTIMIZATION_MULTI_DOMAIN_HOST`  
  
- `STARTUP_LOADER_SAFEMODE`  
  
- `STARTUP_LEGACY_IMPERSONATION`  
  
- `STARTUP_LOADER_SETPREFERENCE`  
  
- `STARTUP_SERVER_GC`  
  
- `STARTUP_HOARD_GC_VM`  
  
- `STARTUP_SINGLE_VERSION_HOSTING_INTERFACE`  
  
- `STARTUP_LEGACY_IMPERSONATION`  
  
- `STARTUP_DISABLE_COMMITTHREADSTACK`  
  
- `STARTUP_ALWAYSFLOW_IMPERSONATION`  
  
 Per le descrizioni di questi flag, vedere l'enumerazione [STARTUP_FLAGS.](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md)  
  
 `rclsid`  
 [in] La `CLSID` della coclasse che implementa il [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) o [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) interfaccia. I valori supportati sono CLSID_CorRuntimeHost o CLSID_CLRRuntimeHost.  
  
 `riid`  
 [in] L'interfaccia `IID` richiesta `rclsid`da . I valori supportati sono IID_ICorRuntimeHost o IID_ICLRRuntimeHost.  
  
 `ppv`  
 [fuori] Puntatore a interfaccia `riid`restituito a .  
  
## <a name="remarks"></a>Osservazioni  
 Se `pwszVersion` specifica una versione di runtime `CorBindToRuntimeEx` che non esiste, restituisce un valore HRESULT di CLR_E_SHIM_RUNTIMELOAD.  
  
## <a name="execution-context-and-flow-of-windows-identity"></a>Contesto di esecuzione e flusso dell'identità di WindowsExecution Context and Flow of Windows Identity  
 Nella versione 1 di <xref:System.Security.Principal.WindowsIdentity> CLR, l'oggetto non passa attraverso punti asincroni, ad esempio nuovi thread, pool di thread o callback del timer. Nella versione 2.0 di <xref:System.Threading.ExecutionContext> CLR, un oggetto esegue il wrapping di alcune informazioni sul thread attualmente in esecuzione e lo scorre attraverso qualsiasi punto asincrono, ma non attraverso i limiti del dominio applicazione. Analogamente, <xref:System.Security.Principal.WindowsIdentity> l'oggetto scorre anche attraverso qualsiasi punto asincrono. Pertanto, la rappresentazione corrente nel thread, se presente, scorre troppo.  
  
 È possibile modificare il flusso in due modi:  
  
1. Modificando le <xref:System.Threading.ExecutionContext> impostazioni per sopprimere il flusso <xref:System.Threading.ExecutionContext.SuppressFlow%2A>in <xref:System.Security.SecurityContext.SuppressFlow%2A>base <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A> al thread (vedere i metodi , e ).  
  
2. Modificando la modalità predefinita del processo alla <xref:System.Security.Principal.WindowsIdentity> modalità di compatibilità della versione 1, in cui l'oggetto non passa attraverso alcun punto asincrono, indipendentemente dalle <xref:System.Threading.ExecutionContext> impostazioni nel thread corrente. La modalità di modifica della modalità predefinita dipende dall'utilizzo di un eseguibile gestito o di un'interfaccia di hosting non gestita per caricare CLR:  
  
    1. Per gli eseguibili gestiti, è necessario impostare l'attributo `enabled` dell'elemento `true` [ \<legacyImpersonationPolicy>](../../../../docs/framework/configure-apps/file-schema/runtime/legacyimpersonationpolicy-element.md) su .  
  
    2. Per le interfacce di `STARTUP_LEGACY_IMPERSONATION` hosting non `startupFlags` gestite, `CorBindToRuntimeEx` impostare il flag nel parametro quando si chiama la funzione.  
  
     La modalità di compatibilità versione 1 si applica all'intero processo e a tutti i domini applicazione del processo.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE.h  
  
 **Biblioteca:** Mscoree  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Funzione CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)
- [Funzione CorBindToRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md)
- [Funzione CorBindToRuntimeByCfg](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)
- [Funzione CorBindToRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md)
- [Interfaccia ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
- [Funzioni di hosting CLR deprecate](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
