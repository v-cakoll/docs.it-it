---
title: Metodo ICLRMetaHost::ExitProcess
ms.date: 03/30/2017
api_name:
- ICLRMetaHost.ExitProcess
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost::ExitProcess
helpviewer_keywords:
- ICLRMetaHost::ExitProcess method [.NET Framework hosting]
- ExitProcess method, ICLRMetaHost interface [.NET Framework hosting]
ms.assetid: b4df98cc-4e4e-407b-b8f4-e0076afef3a4
topic_type:
- apiref
ms.openlocfilehash: d8643c54950486b6374045ff83928c8c7fb568a9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140944"
---
# <a name="iclrmetahostexitprocess-method"></a>Metodo ICLRMetaHost::ExitProcess
Tenta di arrestare correttamente tutti i runtime caricati, quindi termina il processo. Sostituisce la funzione [CorExitProcess](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md) .  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT ExitProcess (  
    [in] INT32 iExitCode);  
```  
  
## <a name="parameters"></a>Parametri  
 `iExitCode`  
 in Codice di uscita del processo.  
  
## <a name="return-value"></a>Valore restituito  
 Questo metodo non restituisce mai, quindi il valore restituito non è definito.  
  
## <a name="remarks"></a>Note  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Metahost. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRMetaHost](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)
- [Hosting](../../../../docs/framework/unmanaged-api/hosting/index.md)
