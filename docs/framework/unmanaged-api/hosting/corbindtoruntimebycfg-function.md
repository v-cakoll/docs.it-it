---
title: Funzione CorBindToRuntimeByCfg
ms.date: 03/30/2017
api_name:
- CorBindToRuntimeByCfg
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- CorBindToRuntimeByCfg
helpviewer_keywords:
- CorBindToRuntimeByCfg function [.NET Framework hosting]
ms.assetid: ded1e492-a782-4185-9c66-709e421c1782
topic_type:
- apiref
ms.openlocfilehash: 8b7dcdcc6d9d0106af1bb83ee591cff76239b416
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504433"
---
# <a name="corbindtoruntimebycfg-function"></a>Funzione CorBindToRuntimeByCfg
Carica il Common Language Runtime (CLR) in un processo utilizzando le informazioni sulla versione lette da un file XML.  
  
 Questa funzione è stata deprecata nel .NET Framework 4.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT CorBindToRuntimeByCfg (  
    [in]  IStream     *pCfgStream,  
    [in]  DWORD        reserved,  
    [in]  DWORD        startupFlags,  
    [in]  REFCLSID     rclsid,  
    [in]  REFIID       riid,
    [out] LPVOID FAR*  ppv  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pCfgStream`  
 in Puntatore a un `IStream` oggetto che legge il file XML.  
  
 `reserved`  
 [in] Riservato per un utilizzo futuro. Usare 0 (zero) come valore.  
  
 `startupFlags`  
 in Valore dell'enumerazione [STARTUP_FLAGS](startup-flags-enumeration.md) che specifica il comportamento di avvio di CLR.  
  
 `rclsid`  
 in `CLSID`Della coclasse che implementa l'interfaccia [ICorRuntimeHost](icorruntimehost-interface.md) o [ICLRRuntimeHost](iclrruntimehost-interface.md) . I valori supportati sono CLSID_CorRuntimeHost o CLSID_CLRRuntimeHost.  
  
 `riid`  
 in Oggetto `IID` dell' `ICorRuntimeHost` `ICLRRuntimeHost` interfaccia o. I valori supportati sono IID_ICorRuntimeHost o IID_ICLRRuntimeHost.  
  
 `ppv`  
 out Puntatore all'indirizzo dell'interfaccia restituita.  
  
## <a name="remarks"></a>Osservazioni  
 Il formato del file XML viene modellato dopo il file di configurazione dell'applicazione standard. Per ulteriori informazioni sui file XML, vedere [schema del file di configurazione](../../configure-apps/file-schema/index.md).  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Funzione CorBindToCurrentRuntime](corbindtocurrentruntime-function.md)
- [Funzione CorBindToRuntime](corbindtoruntime-function.md)
- [Funzione CorBindToRuntimeEx](corbindtoruntimeex-function.md)
- [Funzione CorBindToRuntimeHost](corbindtoruntimehost-function.md)
- [Interfaccia ICorRuntimeHost](icorruntimehost-interface.md)
- [Funzioni di hosting CLR deprecate](deprecated-clr-hosting-functions.md)
