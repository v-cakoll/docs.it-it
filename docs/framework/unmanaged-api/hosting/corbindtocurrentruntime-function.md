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
ms.openlocfilehash: 348ca9d157a668dcd180076475f1fe9861197174
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616666"
---
# <a name="corbindtocurrentruntime-function"></a>Funzione CorBindToCurrentRuntime
Carica il Common Language Runtime (CLR) in un processo utilizzando le informazioni sulla versione archiviate in un file XML. Il formato del file XML viene modellato dopo il file di configurazione dell'applicazione standard. Per altre informazioni sui file di configurazione, vedere [Schema dei file di configurazione](../../configure-apps/file-schema/index.md).  
  
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
  
 La versione del runtime da caricare è descritta dall'attributo Version nell'elemento [ \< requiredRuntime>](../../configure-apps/file-schema/startup/requiredruntime-element.md) del file di configurazione.  
  
 Se non viene specificata alcuna versione o se l' `<requiredRuntime>` elemento non viene trovato, viene caricata la versione più recente di CLR installata nel computer.  
  
 `rclsid`  
 in `CLSID`Della coclasse che implementa l'interfaccia [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) o [ICLRRuntimeHost](iclrruntimehost-interface.md) . I valori supportati sono CLSID_CorRuntimeHost o CLSID_CLRRuntimeHost.  
  
 `riid`  
 in `IID`Dell'interfaccia richiesta. I valori supportati sono IID_ICorRuntimeHost o IID_ICLRRuntimeHost.  
  
 `ppv`  
 out Puntatore a interfaccia restituito.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Funzione CorBindToRuntime](corbindtoruntime-function.md)
- [Funzione CorBindToRuntimeByCfg](corbindtoruntimebycfg-function.md)
- [Funzione CorBindToRuntimeEx](corbindtoruntimeex-function.md)
- [Funzione CorBindToRuntimeHost](corbindtoruntimehost-function.md)
- [Interfaccia ICorRuntimeHost](icorruntimehost-interface.md)
- [Funzioni di hosting CLR deprecate](deprecated-clr-hosting-functions.md)
