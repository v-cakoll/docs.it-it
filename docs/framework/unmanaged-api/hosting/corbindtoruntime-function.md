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
ms.openlocfilehash: 9d4b8bb7d5b3da15f665849c8d18c3a10dbe600b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138306"
---
# <a name="corbindtoruntime-function"></a>Funzione CorBindToRuntime
Consente agli host non gestiti di caricare il Common Language Runtime (CLR) in un processo.  
  
 Questa funzione è stata deprecata nel .NET Framework 4.  
  
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
 in Stringa che descrive la versione di CLR che si desidera caricare.  
  
 Un numero di versione nel .NET Framework è costituito da quattro parti separate da punti: *Major. minor. Build. Revision*. La stringa passata come `pwszVersion` deve iniziare con il carattere "v" seguito dalle prime tre parti del numero di versione (ad esempio, "v 1.0.1529").  
  
 Alcune versioni di CLR vengono installate con un'istruzione di criteri che specifica la compatibilità con le versioni precedenti di CLR. Per impostazione predefinita, lo shim di avvio valuta `pwszVersion` rispetto alle istruzioni dei criteri e carica la versione più recente del runtime compatibile con la versione richiesta. Un host può forzare lo shim a ignorare la valutazione dei criteri e caricare la versione esatta specificata in `pwszVersion` passando un valore `STARTUP_LOADER_SAFEMODE` per il parametro `flags`, come descritto di seguito.  
  
 Se il chiamante specifica null per `pwszVersion`, viene caricata la versione più recente del runtime. Il passaggio di valori null consente all'host di non controllare la versione del runtime caricata. Sebbene questo approccio possa essere appropriato in alcuni scenari, si consiglia vivamente all'host di fornire una versione specifica da caricare.  
  
 `pwszBuildFlavor`  
 in Stringa che specifica se caricare il server o la build della workstation di CLR. I valori validi sono `svr` e `wks`. La compilazione server è ottimizzata per sfruttare i vantaggi di più processori per le operazioni di Garbage Collection e la compilazione della workstation è ottimizzata per le applicazioni client in esecuzione su un computer a processore singolo.  
  
 Se `pwszBuildFlavor` è impostato su null, viene caricata la compilazione della workstation. Quando è in esecuzione in un computer a processore singolo, la compilazione della workstation viene sempre caricata, anche se `pwszBuildFlavor` è impostata su `svr`. Tuttavia, se `pwszBuildFlavor` è impostato su `svr` e viene specificata la Garbage Collection simultanea (vedere la descrizione del parametro `flags`), viene caricata la build del server.  
  
 `rclsid`  
 in `CLSID` della coclasse che implementa l'interfaccia [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) o [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) . I valori supportati sono CLSID_CorRuntimeHost o CLSID_CLRRuntimeHost.  
  
 `riid`  
 in `IID` dell'interfaccia richiesta da `rclsid`. I valori supportati sono IID_ICorRuntimeHost o IID_ICLRRuntimeHost.  
  
 `ppv`  
 out Puntatore a interfaccia restituito per `riid`.  
  
## <a name="remarks"></a>Note  
 Se `pwszVersion` specifica una versione di Runtime inesistente, `CorBindToRuntimeEx` restituisce un valore HRESULT di CLR_E_SHIM_RUNTIMELOAD.  
  
## <a name="execution-context-and-flow-of-windows-identity"></a>Contesto di esecuzione e flusso di identità Windows  
 Nella versione 1 di CLR, l'oggetto <xref:System.Security.Principal.WindowsIdentity> non viene propagato tra punti asincroni, ad esempio nuovi thread, pool di thread o callback del timer. Nella versione 2,0 di CLR, un oggetto <xref:System.Threading.ExecutionContext> esegue il wrapping di alcune informazioni sul thread attualmente in esecuzione e lo trasmette attraverso qualsiasi punto asincrono, ma non tra i limiti del dominio applicazione. Analogamente, anche l'oggetto <xref:System.Security.Principal.WindowsIdentity> scorre in qualsiasi punto asincrono. Quindi, la rappresentazione corrente sul thread, se presente, scorre anche.  
  
 È possibile modificare il flusso in due modi:  
  
1. Modificando le impostazioni di <xref:System.Threading.ExecutionContext> per disattivare il flusso in base ai singoli thread (vedere i metodi <xref:System.Threading.ExecutionContext.SuppressFlow%2A>, <xref:System.Security.SecurityContext.SuppressFlow%2A>e <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A>).  
  
2. Modificando la modalità predefinita del processo con la modalità di compatibilità versione 1, in cui l'oggetto <xref:System.Security.Principal.WindowsIdentity> non viene propagato in alcun punto asincrono, indipendentemente dalle impostazioni <xref:System.Threading.ExecutionContext> sul thread corrente. La modalità di modifica della modalità predefinita varia a seconda che si usi un eseguibile gestito o un'interfaccia di hosting non gestita per caricare il CLR:  
  
    1. Per i file eseguibili gestiti, è necessario impostare l'attributo `enabled` dell'elemento [\<> legacyImpersonationPolicy](../../../../docs/framework/configure-apps/file-schema/runtime/legacyimpersonationpolicy-element.md) su `true`.  
  
    2. Per le interfacce di hosting non gestite, impostare il flag `STARTUP_LEGACY_IMPERSONATION` nel parametro `flags` quando si chiama la funzione `CorBindToRuntimeEx`.  
  
     La modalità di compatibilità versione 1 si applica all'intero processo e a tutti i domini applicazione nel processo.  
  
## <a name="remarks"></a>Note  
 [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) e `CorBindToRuntime` eseguono la stessa operazione, ma la funzione `CorBindToRuntimeEx` consente di impostare i flag per specificare il comportamento di CLR.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** MSCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Funzione CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)
- [Funzione CorBindToRuntimeByCfg](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)
- [Funzione CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)
- [Funzione CorBindToRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md)
- [Interfaccia ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
- [Funzioni di hosting CLR deprecate](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
