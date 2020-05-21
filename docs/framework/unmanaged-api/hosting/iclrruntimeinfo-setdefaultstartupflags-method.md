---
title: Metodo ICLRRuntimeInfo::SetDefaultStartupFlags
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.SetDefaultStartupFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::SetDefaultStartupFlags
helpviewer_keywords:
- ICLRRuntimeInfo::SetDefaultStartupFlags method [.NET Framework hosting]
- SetDefaultStartupFlags method [.NET Framework hosting]
ms.assetid: 98ae174f-bff0-48f1-9e05-6cb63b451824
topic_type:
- apiref
ms.openlocfilehash: 7d201962976d198372226eb686696fcdccf3eb69
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762162"
---
# <a name="iclrruntimeinfosetdefaultstartupflags-method"></a>Metodo ICLRRuntimeInfo::SetDefaultStartupFlags
Imposta i flag di avvio e il file di configurazione host che verranno usati per avviare il Runtime. Questo metodo sostituisce l'utilizzo del `startupFlags` parametro nelle funzioni [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) e [CorBindToRuntimeHost](corbindtoruntimehost-function.md) .  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT SetDefaultStartupFlags(  
           [in]  DWORD dwStartupFlags,  
           [in]  LPCWSTR pwzHostConfigFile);  
```  
  
## <a name="parameters"></a>Parametri  
 `dwStartupFlags`  
 in Flag di avvio dell'host da impostare. Utilizzare gli stessi flag delle funzioni [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) e [CorBindToRuntimeHost](corbindtoruntimehost-function.md) .  
  
 `pwzHostConfigFile`  
 in Percorso della directory del file di configurazione host da impostare.  
  
## <a name="return-value"></a>Valore restituito  
 Questo metodo restituisce il seguente HRESULT specifico, oltre a errori HRESULT che indicano un errore del metodo.  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|Metodo completato correttamente.|  
  
## <a name="remarks"></a>Osservazioni  
 Un host multithread deve sincronizzare le chiamate a questo metodo. In caso contrario, il thread A può chiamare il `SetStartupFlags` metodo dopo che il thread b completa una chiamata a `SetStartupFlags` e prima che il thread b avvii il Runtime.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** Metahost. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRRuntimeInfo](iclrruntimeinfo-interface.md)
- [Interfacce di hosting](hosting-interfaces.md)
- [Hosting](index.md)
