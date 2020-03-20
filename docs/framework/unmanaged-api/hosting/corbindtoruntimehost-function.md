---
title: Funzione CorBindToRuntimeHost
ms.date: 03/30/2017
api_name:
- CorBindToRuntimeHost
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- CorBindToRuntimeHost
helpviewer_keywords:
- CorBindToRuntimeHost function [.NET Framework hosting]
ms.assetid: 5c826ba3-8258-49bc-a417-78807915fcaf
topic_type:
- apiref
ms.openlocfilehash: 6566adc442034763e0209869404b60b5afa63866
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176487"
---
# <a name="corbindtoruntimehost-function"></a>Funzione CorBindToRuntimeHost
Consente agli host di caricare una versione specificata di Common Language Runtime (CLR) in un processo.  
  
 Questa funzione è stata deprecata in .NET Framework 4.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT CorBindToRuntimeHost (  
    [in] LPCWSTR       pwszVersion,
    [in] LPCWSTR       pwszBuildFlavor,
    [in] LPCWSTR       pwszHostConfigFile,
    [in] VOID*         pReserved,
    [in] DWORD         startupFlags,
    [in] REFCLSID      rclsid,
    [in] REFIID        riid,
    [out] LPVOID FAR  *ppv  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pwszVersion`  
 [in] Stringa che descrive la versione di CLR che si desidera caricare.  
  
 Un numero di versione in .NET Framework è costituito da quattro parti separate da punti: *major.minor.build.revision*. La stringa `pwszVersion` passata come deve iniziare con il carattere "v" seguito dalle prime tre parti del numero di versione (ad esempio, "v1.0.1529").  
  
 Alcune versioni di CLR vengono installate con un'istruzione dei criteri che specifica la compatibilità con le versioni precedenti di CLR. Per impostazione predefinita, lo `pwszVersion` shim di avvio valuta rispetto alle istruzioni dei criteri e carica la versione più recente del runtime compatibile con la versione richiesta. Un host può forzare lo shim a ignorare `pwszVersion` la valutazione dei criteri `startupFlags` e caricare la versione esatta specificata in passando un valore di STARTUP_LOADER_SAFEMODE per il parametro.  
  
 Se `pwszVersion` `null,` il metodo indica che il metodo non carica alcuna versione di CLR. Al contrario, restituisce CLR_E_SHIM_RUNTIMELOAD, che indica che non è riuscito a caricare il runtime.  
  
 `pwszBuildFlavor`  
 [in] Stringa che specifica se caricare il server o la build della workstation di CLR. I valori validi sono `svr` e `wks`. La build server è ottimizzata per sfruttare più processori per le operazioni di Garbage Collection e la build workstation è ottimizzata per le applicazioni client in esecuzione su un computer a processore singolo.  
  
 Se `pwszBuildFlavor` è impostato su null, viene caricata la build della workstation. Quando viene eseguita su un computer a processore singolo, la build della workstation viene sempre caricata, anche se `pwszBuildFlavor` è impostata su `svr`. Tuttavia, `pwszBuildFlavor` se `svr` è impostata su e viene specificata `startupFlags` l'operazione di Garbage Collection simultanea (vedere la descrizione del parametro), viene caricata la compilazione del server.  
  
> [!NOTE]
> La Garbage Collection simultanea non è supportata nelle applicazioni che eseguono l'emulatore WOW64 x86 su sistemi a 64 bit che implementano l'architettura Intel Itanium (precedentemente denominata IA-64). Per ulteriori informazioni sull'utilizzo di WOW64 nei sistemi Windows a 64 bit, vedere Esecuzione di applicazioni a [32 bit](/windows/desktop/WinProg64/running-32-bit-applications).  
  
 `pwszHostConfigFile`  
 [in] Nome di un file di configurazione host che specifica la versione di CLR da caricare. Se il nome del file non include un percorso completo, si presuppone che il file si trova nella stessa directory dell'eseguibile che sta effettuando la chiamata.  
  
 `pReserved`  
 [in] Riservato per l'estendibilità futura.  
  
 `startupFlags`  
 [in] Set di flag che controlla la Garbage Collection simultanea, il `pwszVersion` codice indipendente dal dominio e il comportamento del parametro. Il valore predefinito è dominio singolo se non è impostato alcun flag. Per un elenco dei valori supportati, vedere [l'enumerazione STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md).  
  
 `rclsid`  
 [in] La `CLSID` della coclasse che implementa il [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) o [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) interfaccia. I valori supportati sono CLSID_CorRuntimeHost o CLSID_CLRRuntimeHost.  
  
 `riid`  
 [in] L'interfaccia `IID` che si sta richiedendo. I valori supportati sono IID_ICorRuntimeHost o IID_ICLRRuntimeHost.  
  
 `ppv`  
 [fuori] Puntatore a interfaccia alla versione del runtime caricata.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE.idl  
  
 **Biblioteca:** Mscoree  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Funzione CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)
- [Funzione CorBindToRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md)
- [Funzione CorBindToRuntimeByCfg](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)
- [Funzione CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)
- [Interfaccia ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
- [Funzioni di hosting CLR deprecate](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
