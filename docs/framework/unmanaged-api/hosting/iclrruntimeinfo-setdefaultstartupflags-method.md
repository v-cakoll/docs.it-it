---
title: Metodo ICLRRuntimeInfo::SetDefaultStartupFlags
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRRuntimeInfo.SetDefaultStartupFlags
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRRuntimeInfo::SetDefaultStartupFlags
helpviewer_keywords:
- ICLRRuntimeInfo::SetDefaultStartupFlags method [.NET Framework hosting]
- SetDefaultStartupFlags method [.NET Framework hosting]
ms.assetid: 98ae174f-bff0-48f1-9e05-6cb63b451824
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1732073b9799453bd32447e7a688b0280e66f1ae
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="iclrruntimeinfosetdefaultstartupflags-method"></a>Metodo ICLRRuntimeInfo::SetDefaultStartupFlags
Imposta i flag di avvio e il file di configurazione di host che verrà utilizzato per avviare il runtime. Questo metodo sostituisce l'uso del `startupFlags` parametro il [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) e [CorBindToRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md) funzioni.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT SetDefaultStartupFlags(  
           [in]  DWORD dwStartupFlags,  
           [in]  LPCWSTR pwzHostConfigFile);  
```  
  
#### <a name="parameters"></a>Parametri  
 `dwStartupFlags`  
 [in] I flag di avvio di host da impostare. Utilizzare gli stessi flag come con la [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) e [CorBindToRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md) funzioni.  
  
 `pwzHostConfigFile`  
 [in] Il percorso della directory del file di configurazione di host da impostare.  
  
## <a name="return-value"></a>Valore restituito  
 Questo metodo restituisce il valore HRESULT specifico seguente nonché gli errori HRESULT che indicano la mancata riuscita del metodo.  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|Metodo completato correttamente.|  
  
## <a name="remarks"></a>Note  
 Un host multithreading deve sincronizzare le chiamate a questo metodo. In caso contrario, il thread può chiamare il `SetStartupFlags` metodo dopo i thread B ha completato una chiamata a `SetStartupFlags` e prima che il thread B avvia il runtime.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Metahost. H  
  
 **Libreria:** inclusa come risorsa in MSCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [ICLRRuntimeInfo (interfaccia)](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)  
 [Interfacce di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [Hosting](../../../../docs/framework/unmanaged-api/hosting/index.md)
