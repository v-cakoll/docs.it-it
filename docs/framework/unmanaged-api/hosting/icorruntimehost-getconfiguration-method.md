---
title: Metodo ICorRuntimeHost::GetConfiguration
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.GetConfiguration
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::GetConfiguration
helpviewer_keywords:
- ICorRuntimeHost::GetConfiguration method [.NET Framework hosting]
- GetConfiguration method [.NET Framework hosting]
ms.assetid: c431617a-b055-44a0-8730-48b7a86d9610
topic_type:
- apiref
ms.openlocfilehash: 87549118742da797ef0dd1b08ae9e72c466f7841
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139572"
---
# <a name="icorruntimehostgetconfiguration-method"></a>Metodo ICorRuntimeHost::GetConfiguration
Ottiene un oggetto che consente all'host di specificare la configurazione di callback del Common Language Runtime (CLR).  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetConfiguration(  
    [out] ICorConfiguration** pConfiguration  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pConfiguration`  
 out Puntatore all'indirizzo di un oggetto [ICorConfiguration](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md) che può essere utilizzato per configurare CLR.  
  
## <a name="remarks"></a>Note  
 CLR deve essere configurato prima dell'inizializzazione. in caso contrario, il metodo `GetConfiguration` restituisce un valore HRESULT che indica un errore.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:** 1,0, 1,1  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
