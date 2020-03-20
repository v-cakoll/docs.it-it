---
title: Funzione CorBindToRuntime
ms.date: 03/30/2017
api_name:
- CorBindToRuntime
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- CorBindToRuntime
helpviewer_keywords:
- CorBindToRuntime function [.NET Framework hosting]
ms.assetid: 799740aa-46ec-4532-95da-6444565b4971
topic_type:
- apiref
ms.openlocfilehash: 2db9d26ef2dec150977c468b16334a7cb4b3d49c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176513"
---
# <a name="corbindtoruntime-function"></a>Funzione CorBindToRuntime
Consente agli host non gestiti di caricare Common Language Runtime (CLR) in un processo.  
  
 Questa funzione è stata deprecata in .NET Framework 4.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT CorBindToRuntime (  
    [in]  LPCWSTR     pwszVersion,
    [in]  LPCWSTR     pwszBuildFlavor,
    [in]  REFCLSID    rclsid,
    [in]  REFIID      riid,
    [out] LPVOID FAR  *ppv  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pwszVersion`  
 [in] Stringa che descrive la versione di CLR che si desidera caricare.  
  
 Un numero di versione in .NET Framework è costituito da quattro parti separate da punti: *major.minor.build.revision*. La stringa `pwszVersion` passata come deve iniziare con il carattere "v" seguito dalle prime tre parti del numero di versione (ad esempio, "v1.0.1529").  
  
 Alcune versioni di CLR vengono installate con un'istruzione dei criteri che specifica la compatibilità con le versioni precedenti di CLR. Per impostazione predefinita, lo `pwszVersion` shim di avvio valuta rispetto alle istruzioni dei criteri e carica la versione più recente del runtime compatibile con la versione richiesta. Un host può forzare lo shim a ignorare `pwszVersion` la valutazione dei `STARTUP_LOADER_SAFEMODE` criteri `flags` e caricare la versione esatta specificata in passando un valore di per il parametro, come descritto di seguito.  
  
 Se il chiamante `pwszVersion`specifica null per , viene caricata la versione più recente del runtime. Il passaggio di null non fornisce all'host alcun controllo sulla versione del runtime caricata. Anche se questo approccio può essere appropriato in alcuni scenari, è consigliabile che l'host fornisse una versione specifica da caricare.  
  
 `pwszBuildFlavor`  
 [in] Stringa che specifica se caricare il server o la build della workstation di CLR. I valori validi sono `svr` e `wks`. La build server è ottimizzata per sfruttare più processori per le operazioni di Garbage Collection e la build workstation è ottimizzata per le applicazioni client in esecuzione su un computer a processore singolo.  
  
 Se `pwszBuildFlavor` è impostato su null, viene caricata la build della workstation. Quando viene eseguita su un computer a processore singolo, la build della workstation viene sempre caricata, anche se `pwszBuildFlavor` è impostata su `svr`. Tuttavia, `pwszBuildFlavor` se `svr` è impostata su e viene specificata `flags` l'operazione di Garbage Collection simultanea (vedere la descrizione del parametro), viene caricata la compilazione del server.  
  
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
  
    2. Per le interfacce di `STARTUP_LEGACY_IMPERSONATION` hosting non `flags` gestite, `CorBindToRuntimeEx` impostare il flag nel parametro quando si chiama la funzione.  
  
     La modalità di compatibilità versione 1 si applica all'intero processo e a tutti i domini applicazione del processo.  
  
## <a name="remarks"></a>Osservazioni  
 [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) `CorBindToRuntime` ed eseguire la stessa `CorBindToRuntimeEx` operazione, ma la funzione consente di impostare i flag per specificare il comportamento di CLR.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE.h  
  
 **Biblioteca:** Mscoree  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Funzione CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)
- [Funzione CorBindToRuntimeByCfg](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)
- [Funzione CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)
- [Funzione CorBindToRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md)
- [Interfaccia ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
- [Funzioni di hosting CLR deprecate](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
