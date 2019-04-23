---
title: Metodo IAppDomainBinding::OnAppDomain
ms.date: 03/30/2017
api_name:
- IAppDomainBinding.OnAppDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- OnAppDomain
helpviewer_keywords:
- IAppDomainBinding::OnAppDomain method [.NET Framework hosting]
- OnAppDomain method [.NET Framework hosting]
ms.assetid: b419dcc9-e8aa-484b-af0d-0f40358edb99
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2903395f5f834f2435b14d0b3f3e8bfe24af2867
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59183053"
---
# <a name="iappdomainbindingonappdomain-method"></a>Metodo IAppDomainBinding::OnAppDomain
Chiamato da common language runtime (CLR) per notificare all'host che è stato creato un dominio dell'applicazione.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT OnAppDomain (  
    [in] IUnknown* pAppdomain  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pAppdomain`  
 [in] Un puntatore a un [IUnknown](/cpp/atl/iunknown) oggetto di interfaccia che rappresenta il nuovo dominio applicazione.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE.h  
  
 **Libreria:** Inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IAppDomainBinding](../../../../docs/framework/unmanaged-api/hosting/iappdomainbinding-interface.md)
