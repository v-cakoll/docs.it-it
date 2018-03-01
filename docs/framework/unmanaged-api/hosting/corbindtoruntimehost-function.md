---
title: Funzione CorBindToRuntimeHost
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e6d69f39aa74665843b0bf91407e764ea67f41d7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="corbindtoruntimehost-function"></a>Funzione CorBindToRuntimeHost
Consente agli host di caricare una versione specifica di common language runtime (CLR) in un processo.  
  
 Questa funzione è stata deprecata nel [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].  
  
## <a name="syntax"></a>Sintassi  
  
```  
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
  
#### <a name="parameters"></a>Parametri  
 `pwszVersion`  
 [in] Una stringa che descrive la versione di CLR a cui si desidera caricare.  
  
 Un numero di versione di .NET Framework è costituito da quattro parti separate da punti: *revisione*. La stringa passata come `pwszVersion` deve iniziare con il carattere "v" seguito dalle prime tre parti del numero di versione (ad esempio, "v 1.0.1529").  
  
 Alcune versioni di Common Language Runtime vengono installati con un'istruzione di criteri che specifica la compatibilità con le versioni precedenti di CLR. Per impostazione predefinita, valuta lo shim di avvio `pwszVersion` contro istruzioni dei criteri e carica la versione più recente del runtime che è compatibile con la versione richiesta. Un host può imporre allo shim di ignorare la valutazione dei criteri e caricare l'esatta versione specificata `pwszVersion` passando un valore STARTUP_LOADER_SAFEMODE per il `startupFlags` parametro.  
  
 Se `pwszVersion` è `null,` il metodo non viene caricato qualsiasi versione di CLR. Restituisce invece CLR_E_SHIM_RUNTIMELOAD, che indica che non è riuscito a caricare il runtime.  
  
 `pwszBuildFlavor`  
 [in] Stringa che specifica se caricare il server o la compilazione di workstation di CLR. I valori validi sono `svr` e `wks`. La compilazione di server è ottimizzata per sfruttare i vantaggi di più processori per operazioni di garbage collection e la compilazione di workstation è ottimizzata per le applicazioni client eseguite in un computer a processore singolo.  
  
 Se `pwszBuildFlavor` è impostato su null, viene caricata la build per workstation. Quando si esegue in un computer a processore singolo, la compilazione della workstation viene sempre caricata, anche se `pwszBuildFlavor` è impostato su `svr`. Tuttavia, se `pwszBuildFlavor` è impostato su `svr` e garbage collection simultanea è specificata (vedere la descrizione del `startupFlags` parametro), verrà caricata la build del server.  
  
> [!NOTE]
>  Garbage collection simultanea non è supportata nelle applicazioni in esecuzione WOW64 x86 emulatore nei sistemi a 64 bit che implementano l'architettura Intel Itanium (IA-64 noto). Per ulteriori informazioni sull'utilizzo di WOW64 nei sistemi Windows a 64 bit, vedere [applicazioni in esecuzione a 32 bit](http://msdn.microsoft.com/library/windows/desktop/aa384249.aspx).  
  
 `pwszHostConfigFile`  
 [in] Il nome di un file di configurazione di host che specifica la versione di Common Language Runtime da caricare. Se il nome del file non include il percorso completo, il file è considerato nella stessa directory del file eseguibile che effettua la chiamata.  
  
 `pReserved`  
 [in] Riservato per l'estensibilità futura.  
  
 `startupFlags`  
 [in] Un set di flag che controlla il comportamento di garbage collection simultanea e codice indipendente dal dominio di `pwszVersion` parametro. Se non è impostato alcun flag, il valore predefinito è singolo dominio. Per un elenco di valori supportati, vedere il [enumerazione STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md).  
  
 `rclsid`  
 [in] Il `CLSID` della coclasse che implementa il [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) o [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) interfaccia. Valori supportati sono CLSID_CorRuntimeHost o CLSID_CLRRuntimeHost.  
  
 `riid`  
 [in] Il `IID` dell'interfaccia richiesta. Valori supportati sono IID_ICorRuntimeHost o IID_ICLRRuntimeHost.  
  
 `ppv`  
 [out] Un puntatore a interfaccia per la versione del runtime che è stato caricato.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Mscoree  
  
 **Libreria:** MSCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Funzione CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)  
 [Funzione CorBindToRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md)  
 [Funzione CorBindToRuntimeByCfg](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)  
 [Funzione CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)  
 [Interfaccia ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)  
 [Funzioni di hosting CLR deprecate](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
