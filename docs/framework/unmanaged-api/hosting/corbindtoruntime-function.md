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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: eb5c05a88c12b5124c77b0d0a7f834b405dd289f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61697420"
---
# <a name="corbindtoruntime-function"></a>Funzione CorBindToRuntime
Consente l'host non gestiti di caricare common language runtime (CLR) in un processo.  
  
 Questa funzione è stata deprecata nel [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].  
  
## <a name="syntax"></a>Sintassi  
  
```  
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
 [in] Stringa che descrive la versione di CLR a cui si desidera caricare.  
  
 Un numero di versione in .NET Framework è costituito da quattro parti separate da punti: *revisione*. La stringa passata come `pwszVersion` deve iniziare con il carattere "v" seguito dalle prime tre parti del numero di versione (ad esempio, "v 1.0.1529").  
  
 Alcune versioni di CLR installate con un'istruzione di criteri che specifica la compatibilità con le versioni precedenti di CLR. Per impostazione predefinita, valuta lo shim di avvio `pwszVersion` contro le istruzioni dei criteri e carichi la versione più recente del runtime che è compatibile con la versione richiesta. Un host può forzare lo shim per ignorare la valutazione dei criteri e caricare la versione esatta specificata nel `pwszVersion` passando un valore di `STARTUP_LOADER_SAFEMODE` per il `flags` parametro, come descritto di seguito.  
  
 Se il chiamante specifica null per `pwszVersion`, viene caricata la versione più recente del runtime. Passaggio di null non consente all'host di alcun controllo sulla quale versione del runtime è caricata. Sebbene questo approccio potrebbe essere appropriato in alcuni scenari, è consigliabile che l'host di fornisca una versione specifica di caricare.  
  
 `pwszBuildFlavor`  
 [in] Stringa che specifica se caricare il server o la compilazione di workstation di CLR. I valori validi sono `svr` e `wks`. La compilazione di server è ottimizzata per sfruttare più processori per operazioni di garbage collection e la compilazione di workstation è ottimizzata per le applicazioni client in esecuzione in un computer a processore singolo.  
  
 Se `pwszBuildFlavor` è impostato su null, la compilazione di workstation viene caricata. Durante l'esecuzione in un computer a processore singolo, la compilazione di workstation viene sempre caricata, anche se `pwszBuildFlavor` è impostata su `svr`. Tuttavia, se `pwszBuildFlavor` è impostata su `svr` e garbage collection simultanea è specificata (vedere la descrizione del `flags` parametro), viene caricata la compilazione di server.  
  
 `rclsid`  
 [in] Il `CLSID` della coclasse che implementa il [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) o il [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) interfaccia. I valori supportati sono CLSID_CorRuntimeHost o CLSID_CLRRuntimeHost.  
  
 `riid`  
 [in] Il `IID` dell'interfaccia richiesta da `rclsid`. Valori supportati sono IID_ICorRuntimeHost o IID_ICLRRuntimeHost.  
  
 `ppv`  
 [out] Il puntatore a interfaccia restituito `riid`.  
  
## <a name="remarks"></a>Note  
 Se `pwszVersion` specifica una versione di runtime che non esiste, `CorBindToRuntimeEx` restituisce un valore HRESULT di CLR_E_SHIM_RUNTIMELOAD.  
  
## <a name="execution-context-and-flow-of-windows-identity"></a>Contesto di esecuzione e il flusso dell'identità di Windows  
 Nella versione 1 di CLR, il <xref:System.Security.Principal.WindowsIdentity> oggetto non passa attraverso punti asincroni, ad esempio nuovi thread, i pool di thread o i callback di timer. Nella versione 2.0 di CLR, un <xref:System.Threading.ExecutionContext> oggetto esegue il wrapping di alcune informazioni relative al thread attualmente in esecuzione e ne effettua attraverso punti asincroni qualsiasi, ma non tra i limiti del dominio applicazione. Analogamente, il <xref:System.Security.Principal.WindowsIdentity> oggetto anche passa attraverso punti asincroni qualsiasi. Pertanto, la rappresentazione corrente nel thread, se presente, flussi troppo.  
  
 È possibile modificare il flusso in due modi:  
  
1. Modificando la <xref:System.Threading.ExecutionContext> le impostazioni per sopprimere il flusso in un singolo thread (vedere la <xref:System.Threading.ExecutionContext.SuppressFlow%2A>, <xref:System.Security.SecurityContext.SuppressFlow%2A>, e <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A> metodi).  
  
2. Modificando la modalità predefinita del processo per la modalità di compatibilità di versione 1, in cui il <xref:System.Security.Principal.WindowsIdentity> oggetto non passa attraverso punti asincroni, qualsiasi indipendentemente il <xref:System.Threading.ExecutionContext> impostazioni sul thread corrente. Come si modifica la modalità predefinita varia a seconda se si usa un file eseguibile gestito o un'interfaccia di hosting non gestita per caricamento di CLR:  
  
    1. Per gli eseguibili gestiti, è necessario impostare il `enabled` attributo del [ \<legacyImpersonationPolicy >](../../../../docs/framework/configure-apps/file-schema/runtime/legacyimpersonationpolicy-element.md) elemento `true`.  
  
    2. Per non gestiti di interfacce di hosting, impostare il `STARTUP_LEGACY_IMPERSONATION` flag nel `flags` parametro quando si chiama il `CorBindToRuntimeEx` (funzione).  
  
     La modalità di compatibilità di versione 1 si applica all'intero processo e per tutti i domini applicazione nel processo.  
  
## <a name="remarks"></a>Note  
 [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) e `CorBindToRuntime` eseguire la stessa operazione, ma il `CorBindToRuntimeEx` funzione consente di impostare i flag per specificare il comportamento di CLR.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE.h  
  
 **Libreria:** MSCorEE.dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Funzione CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)
- [Funzione CorBindToRuntimeByCfg](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)
- [Funzione CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)
- [Funzione CorBindToRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md)
- [Interfaccia ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
- [Funzioni di hosting CLR deprecate](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
