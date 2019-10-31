---
title: Funzione CorBindToCurrentRuntime
ms.date: 03/30/2017
api_name:
- CorBindToCurrentRuntime
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- HeaderDef
f1_keywords:
- CorBindToCurrentRuntime
helpviewer_keywords:
- CorBindToCurrentRuntime function [.NET Framework hosting]
ms.assetid: 6105c13e-d9cd-44d2-a95a-924e042830c7
topic_type:
- apiref
ms.openlocfilehash: 77a0a8f58c11673a1958d837b4c3a21a05754c94
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138325"
---
# <a name="corbindtocurrentruntime-function"></a>Funzione CorBindToCurrentRuntime
Carica il Common Language Runtime (CLR) in un processo utilizzando le informazioni sulla versione archiviate in un file XML. Il formato del file XML viene modellato dopo il file di configurazione dell'applicazione standard. Per altre informazioni sui file di configurazione, vedere [Schema dei file di configurazione](../../../../docs/framework/configure-apps/file-schema/index.md).  
  
 Questa funzione è stata deprecata nel .NET Framework 4. Vedere [caricamento di Common Language Runtime in un processo](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/01918c6x(v=vs.100)).  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT CorBindToCurrentRuntime (  
    [in]  LPCWSTR   pwszFileName,  
    [in]  REFCLSID  rclsid,  
    [in]  REFIID    riid,  
    [out] LPVOID    *ppv  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pwszFileName`  
 in Nome di un file di configurazione dell'applicazione che specifica la versione di CLR da caricare. Se il nome del file non è completo, si presuppone che si trovi nella stessa directory del file eseguibile che effettua la chiamata.  
  
 La versione del runtime da caricare è descritta dall'attributo Version nell'elemento [\<requiredRuntime >](../../../../docs/framework/configure-apps/file-schema/startup/requiredruntime-element.md) del file di configurazione.  
  
 Se non viene specificata alcuna versione o se non è possibile trovare l'elemento `<requiredRuntime>`, viene caricata la versione più recente di CLR installata nel computer.  
  
 `rclsid`  
 in `CLSID` della coclasse che implementa l'interfaccia [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) o [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) . I valori supportati sono CLSID_CorRuntimeHost o CLSID_CLRRuntimeHost.  
  
 `riid`  
 in `IID` dell'interfaccia richiesta. I valori supportati sono IID_ICorRuntimeHost o IID_ICLRRuntimeHost.  
  
 `ppv`  
 out Puntatore a interfaccia restituito.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** MSCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Funzione CorBindToRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md)
- [Funzione CorBindToRuntimeByCfg](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)
- [Funzione CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)
- [Funzione CorBindToRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md)
- [Interfaccia ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
- [Funzioni di hosting CLR deprecate](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
