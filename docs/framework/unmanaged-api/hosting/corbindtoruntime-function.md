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
ms.openlocfilehash: 52594c36c54c74941371f9950fbc6fb543b86de0
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84493552"
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
  
 Alcune versioni di CLR vengono installate con un'istruzione di criteri che specifica la compatibilità con le versioni precedenti di CLR. Per impostazione predefinita, lo shim di avvio valuta le `pwszVersion` istruzioni dei criteri e carica la versione più recente del runtime compatibile con la versione richiesta. Un host può forzare lo shim a ignorare la valutazione dei criteri e caricare la versione esatta specificata in `pwszVersion` passando un valore `STARTUP_LOADER_SAFEMODE` per il `flags` parametro, come descritto di seguito.  
  
 Se il chiamante specifica null per `pwszVersion` , viene caricata la versione più recente del runtime. Il passaggio di valori null consente all'host di non controllare la versione del runtime caricata. Sebbene questo approccio possa essere appropriato in alcuni scenari, si consiglia vivamente all'host di fornire una versione specifica da caricare.  
  
 `pwszBuildFlavor`  
 in Stringa che specifica se caricare il server o la build della workstation di CLR. I valori validi sono `svr` e `wks`. La compilazione server è ottimizzata per sfruttare i vantaggi di più processori per le operazioni di Garbage Collection e la compilazione della workstation è ottimizzata per le applicazioni client in esecuzione su un computer a processore singolo.  
  
 Se `pwszBuildFlavor` è impostato su null, viene caricata la compilazione della workstation. Quando è in esecuzione in un computer a processore singolo, la compilazione della workstation viene sempre caricata, anche se `pwszBuildFlavor` è impostato su `svr` . Tuttavia, se `pwszBuildFlavor` è impostato su `svr` e viene specificato Garbage Collection simultaneo (vedere la descrizione del `flags` parametro), viene caricata la compilazione del server.  
  
 `rclsid`  
 in `CLSID`Della coclasse che implementa l'interfaccia [ICorRuntimeHost](icorruntimehost-interface.md) o [ICLRRuntimeHost](iclrruntimehost-interface.md) . I valori supportati sono CLSID_CorRuntimeHost o CLSID_CLRRuntimeHost.  
  
 `riid`  
 in `IID`Dell'interfaccia richiesta da `rclsid` . I valori supportati sono IID_ICorRuntimeHost o IID_ICLRRuntimeHost.  
  
 `ppv`  
 out Puntatore a interfaccia restituito a `riid` .  
  
## <a name="remarks"></a>Osservazioni  
 Se `pwszVersion` specifica una versione runtime che non esiste, `CorBindToRuntimeEx` restituisce un valore HRESULT pari a CLR_E_SHIM_RUNTIMELOAD.  
  
## <a name="execution-context-and-flow-of-windows-identity"></a>Contesto di esecuzione e flusso di identità Windows  
 Nella versione 1 di CLR, l' <xref:System.Security.Principal.WindowsIdentity> oggetto non scorre tra punti asincroni, ad esempio nuovi thread, pool di thread o callback del timer. Nella versione 2,0 di CLR, un <xref:System.Threading.ExecutionContext> oggetto esegue il wrapping di alcune informazioni sul thread attualmente in esecuzione e lo trasmette attraverso qualsiasi punto asincrono, ma non tra i limiti del dominio applicazione. Analogamente, l' <xref:System.Security.Principal.WindowsIdentity> oggetto fluisce anche su qualsiasi punto asincrono. Quindi, la rappresentazione corrente sul thread, se presente, scorre anche.  
  
 È possibile modificare il flusso in due modi:  
  
1. Modificando le <xref:System.Threading.ExecutionContext> impostazioni per escludere il flusso per ogni singolo thread (vedere i <xref:System.Threading.ExecutionContext.SuppressFlow%2A> metodi, <xref:System.Security.SecurityContext.SuppressFlow%2A> e <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A> ).  
  
2. Modificando la modalità predefinita del processo con la modalità di compatibilità versione 1, in cui l' <xref:System.Security.Principal.WindowsIdentity> oggetto non viene propagato in alcun punto asincrono, indipendentemente dalle <xref:System.Threading.ExecutionContext> impostazioni nel thread corrente. La modalità di modifica della modalità predefinita varia a seconda che si usi un eseguibile gestito o un'interfaccia di hosting non gestita per caricare il CLR:  
  
    1. Per i file eseguibili gestiti, è necessario impostare l' `enabled` attributo dell' [\<legacyImpersonationPolicy>](../../configure-apps/file-schema/runtime/legacyimpersonationpolicy-element.md) elemento su `true` .  
  
    2. Per le interfacce di hosting non gestite, impostare il `STARTUP_LEGACY_IMPERSONATION` flag nel `flags` parametro quando si chiama la `CorBindToRuntimeEx` funzione.  
  
     La modalità di compatibilità versione 1 si applica all'intero processo e a tutti i domini applicazione nel processo.  
  
## <a name="remarks"></a>Osservazioni  
 [CorBindToRuntimeEx](corbindtoruntimeex-function.md) ed `CorBindToRuntime` eseguono la stessa operazione, ma la `CorBindToRuntimeEx` funzione consente di impostare i flag per specificare il comportamento di CLR.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Funzione CorBindToCurrentRuntime](corbindtocurrentruntime-function.md)
- [Funzione CorBindToRuntimeByCfg](corbindtoruntimebycfg-function.md)
- [Funzione CorBindToRuntimeEx](corbindtoruntimeex-function.md)
- [Funzione CorBindToRuntimeHost](corbindtoruntimehost-function.md)
- [Interfaccia ICorRuntimeHost](icorruntimehost-interface.md)
- [Funzioni di hosting CLR deprecate](deprecated-clr-hosting-functions.md)
