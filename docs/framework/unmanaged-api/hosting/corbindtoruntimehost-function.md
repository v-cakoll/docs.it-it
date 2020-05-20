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
ms.openlocfilehash: afb25ad9e1760f390aa8dfb3e1de39ea60f185c2
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616619"
---
# <a name="corbindtoruntimehost-function"></a>Funzione CorBindToRuntimeHost
Consente agli host di caricare una versione specificata del Common Language Runtime (CLR) in un processo.  
  
 Questa funzione è stata deprecata nel .NET Framework 4.  
  
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
 in Stringa che descrive la versione di CLR che si desidera caricare.  
  
 Un numero di versione nel .NET Framework è costituito da quattro parti separate da punti: *Major. minor. Build. Revision*. La stringa passata come `pwszVersion` deve iniziare con il carattere "v" seguito dalle prime tre parti del numero di versione (ad esempio, "v 1.0.1529").  
  
 Alcune versioni di CLR vengono installate con un'istruzione di criteri che specifica la compatibilità con le versioni precedenti di CLR. Per impostazione predefinita, lo shim di avvio valuta le `pwszVersion` istruzioni dei criteri e carica la versione più recente del runtime compatibile con la versione richiesta. Un host può forzare lo shim a ignorare la valutazione dei criteri e caricare la versione esatta specificata in `pwszVersion` passando il valore STARTUP_LOADER_SAFEMODE per il `startupFlags` parametro.  
  
 Se `pwszVersion` è `null,` , il metodo non carica alcuna versione di CLR. Restituisce invece CLR_E_SHIM_RUNTIMELOAD, che indica che non è stato possibile caricare il Runtime.  
  
 `pwszBuildFlavor`  
 in Stringa che specifica se caricare il server o la build della workstation di CLR. I valori validi sono `svr` e `wks`. La compilazione server è ottimizzata per sfruttare i vantaggi di più processori per le operazioni di Garbage Collection e la compilazione della workstation è ottimizzata per le applicazioni client in esecuzione su un computer a processore singolo.  
  
 Se `pwszBuildFlavor` è impostato su null, viene caricata la compilazione della workstation. Quando è in esecuzione in un computer a processore singolo, la compilazione della workstation viene sempre caricata, anche se `pwszBuildFlavor` è impostato su `svr` . Tuttavia, se `pwszBuildFlavor` è impostato su `svr` e viene specificato Garbage Collection simultaneo (vedere la descrizione del `startupFlags` parametro), viene caricata la compilazione del server.  
  
> [!NOTE]
> La Garbage Collection simultanea non è supportata nelle applicazioni che eseguono l'emulatore WOW64 x86 nei sistemi a 64 bit che implementano l'architettura Intel Itanium (denominata in precedenza IA-64). Per ulteriori informazioni sull'utilizzo di WOW64 in sistemi Windows a 64 bit, vedere [esecuzione di applicazioni a 32 bit](/windows/desktop/WinProg64/running-32-bit-applications).  
  
 `pwszHostConfigFile`  
 in Nome di un file di configurazione host che specifica la versione di CLR da caricare. Se il nome file non include un percorso completo, si presuppone che il file si trovi nella stessa directory del file eseguibile che effettua la chiamata.  
  
 `pReserved`  
 in Riservato per l'estendibilità futura.  
  
 `startupFlags`  
 in Set di flag che controlla il Garbage Collection simultaneo, il codice indipendente dal dominio e il comportamento del `pwszVersion` parametro. Il valore predefinito è Single Domain se non è impostato alcun flag. Per un elenco dei valori supportati, vedere l' [enumerazione STARTUP_FLAGS](startup-flags-enumeration.md).  
  
 `rclsid`  
 in `CLSID`Della coclasse che implementa l'interfaccia [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) o [ICLRRuntimeHost](iclrruntimehost-interface.md) . I valori supportati sono CLSID_CorRuntimeHost o CLSID_CLRRuntimeHost.  
  
 `riid`  
 in `IID`Dell'interfaccia richiesta. I valori supportati sono IID_ICorRuntimeHost o IID_ICLRRuntimeHost.  
  
 `ppv`  
 out Puntatore di interfaccia alla versione del runtime che è stata caricata.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. idl  
  
 **Libreria:** MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Funzione CorBindToCurrentRuntime](corbindtocurrentruntime-function.md)
- [Funzione CorBindToRuntime](corbindtoruntime-function.md)
- [Funzione CorBindToRuntimeByCfg](corbindtoruntimebycfg-function.md)
- [Funzione CorBindToRuntimeEx](corbindtoruntimeex-function.md)
- [Interfaccia ICorRuntimeHost](icorruntimehost-interface.md)
- [Funzioni di hosting CLR deprecate](deprecated-clr-hosting-functions.md)
