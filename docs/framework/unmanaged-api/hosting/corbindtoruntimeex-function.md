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
ms.openlocfilehash: dcf2ce8bdb7cec1f567e548ff3314e160fffe9fd
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616632"
---
# <a name="corbindtoruntimeex-function"></a>Funzione CorBindToRuntimeEx
Consente agli host non gestiti di caricare il Common Language Runtime (CLR) in un processo. Le funzioni [CorBindToRuntime](corbindtoruntime-function.md) e `CorBindToRuntimeEx` eseguono la stessa operazione, ma la `CorBindToRuntimeEx` funzione consente di impostare i flag per specificare il comportamento di CLR.  
  
 Questa funzione è stata deprecata nel .NET Framework 4.  
  
 Questa funzione accetta un set di parametri che consentono a un host di eseguire le operazioni seguenti:  
  
- Consente di specificare la versione del runtime da caricare.  
  
- Indica se è necessario caricare la build del server o della workstation.  
  
- Controllare se viene eseguita la Garbage Collection simultanea Garbage Collection o non simultanea.  
  
> [!NOTE]
> La Garbage Collection simultanea non è supportata nelle applicazioni che eseguono l'emulatore WOW64 x86 nei sistemi a 64 bit che implementano l'architettura Intel Itanium (denominata in precedenza IA-64). Per ulteriori informazioni sull'utilizzo di WOW64 in sistemi Windows a 64 bit, vedere [esecuzione di applicazioni a 32 bit](/windows/desktop/WinProg64/running-32-bit-applications).  
  
- Controllare se gli assembly vengono caricati come indipendenti dal dominio.  
  
- Ottenere un puntatore a interfaccia a un [ICorRuntimeHost](icorruntimehost-interface.md) che può essere utilizzato per impostare opzioni aggiuntive per la configurazione di un'istanza di CLR prima che venga avviata.  
  
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
 in Stringa che descrive la versione di CLR che si desidera caricare.  
  
 Un numero di versione nel .NET Framework è costituito da quattro parti separate da punti: *Major. minor. Build. Revision*. La stringa passata come `pwszVersion` deve iniziare con il carattere "v" seguito dalle prime tre parti del numero di versione (ad esempio, "v 1.0.1529").  
  
 Alcune versioni di CLR vengono installate con un'istruzione di criteri che specifica la compatibilità con le versioni precedenti di CLR. Per impostazione predefinita, lo shim di avvio valuta le `pwszVersion` istruzioni dei criteri e carica la versione più recente del runtime compatibile con la versione richiesta. Un host può forzare lo shim a ignorare la valutazione dei criteri e caricare la versione esatta specificata in `pwszVersion` passando un valore `STARTUP_LOADER_SAFEMODE` per il `startupFlags` parametro, come descritto di seguito.  
  
 Se il chiamante specifica null per `pwszVersion` , `CorBindToRuntimeEx` identifica il set di runtime installati i cui numeri di versione sono inferiori al runtime di .NET Framework 4 e carica la versione più recente del runtime da tale set. Non caricherà il .NET Framework 4 o versione successiva e avrà esito negativo se non è installata alcuna versione precedente. Si noti che il passaggio di valori null consente all'host di non controllare la versione del runtime caricata. Sebbene questo approccio possa essere appropriato in alcuni scenari, si consiglia vivamente all'host di fornire una versione specifica da caricare.  
  
 `pwszBuildFlavor`  
 in Stringa che specifica se caricare il server o la build della workstation di CLR. I valori validi sono `svr` e `wks`. La compilazione server è ottimizzata per sfruttare i vantaggi di più processori per le operazioni di Garbage Collection e la compilazione della workstation è ottimizzata per le applicazioni client in esecuzione su un computer a processore singolo.  
  
 Se `pwszBuildFlavor` è impostato su null, viene caricata la compilazione della workstation. Quando è in esecuzione in un computer a processore singolo, la compilazione della workstation viene sempre caricata, anche se `pwszBuildFlavor` è impostato su `svr` . Tuttavia, se `pwszBuildFlavor` è impostato su `svr` e viene specificato Garbage Collection simultaneo (vedere la descrizione del `startupFlags` parametro), viene caricata la compilazione del server.  
  
 `startupFlags`  
 in Combinazione di valori dell'enumerazione [STARTUP_FLAGS](startup-flags-enumeration.md) . Questi flag controllano Garbage Collection simultanee, il codice indipendente dal dominio e il comportamento del `pwszVersion` parametro. Il valore predefinito è Single Domain se non è impostato alcun flag. I valori seguenti sono validi:  
  
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
  
 Per una descrizione di questi flag, vedere l'enumerazione [STARTUP_FLAGS](startup-flags-enumeration.md) .  
  
 `rclsid`  
 in `CLSID`Della coclasse che implementa l'interfaccia [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) o [ICLRRuntimeHost](iclrruntimehost-interface.md) . I valori supportati sono CLSID_CorRuntimeHost o CLSID_CLRRuntimeHost.  
  
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
  
    1. Per i file eseguibili gestiti, è necessario impostare l' `enabled` attributo dell'elemento [ \<>legacyImpersonationPolicy](../../configure-apps/file-schema/runtime/legacyimpersonationpolicy-element.md) su `true` .  
  
    2. Per le interfacce di hosting non gestite, impostare il `STARTUP_LEGACY_IMPERSONATION` flag nel `startupFlags` parametro quando si chiama la `CorBindToRuntimeEx` funzione.  
  
     La modalità di compatibilità versione 1 si applica all'intero processo e a tutti i domini applicazione nel processo.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Funzione CorBindToCurrentRuntime](corbindtocurrentruntime-function.md)
- [Funzione CorBindToRuntime](corbindtoruntime-function.md)
- [Funzione CorBindToRuntimeByCfg](corbindtoruntimebycfg-function.md)
- [Funzione CorBindToRuntimeHost](corbindtoruntimehost-function.md)
- [Interfaccia ICorRuntimeHost](icorruntimehost-interface.md)
- [Funzioni di hosting CLR deprecate](deprecated-clr-hosting-functions.md)
