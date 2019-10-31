---
title: Interfaccia IHostSecurityContext
ms.date: 03/30/2017
api_name:
- IHostSecurityContext
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityContext
helpviewer_keywords:
- IHostSecurityContext interface [.NET Framework hosting]
ms.assetid: 88e2eac0-8ccb-404f-abbc-287d55159842
topic_type:
- apiref
ms.openlocfilehash: 993d16818b25dfefe1f53c7afd06bc9857d9eb24
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121517"
---
# <a name="ihostsecuritycontext-interface"></a>Interfaccia IHostSecurityContext
Consente all'Common Language Runtime (CLR) di mantenere le informazioni sul contesto di sicurezza implementate dall'host.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo Capture](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-capture-method.md)|Ottiene un clone dell'istanza di `IHostSecurityContext` restituita da una chiamata a [IHostSecurityManager:: GetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md).|  
  
## <a name="remarks"></a>Note  
 Un host può controllare l'accesso al codice a token di thread sia dal codice CLR che dal codice utente. Può inoltre garantire che le informazioni complete sul contesto di sicurezza vengano passate tra le operazioni asincrone o i punti di codice con accesso limitato al codice. `IHostSecurityContext` incapsula le informazioni sul contesto di sicurezza, che è opaco per il Runtime. Il runtime acquisisce queste informazioni usando `Capture`e le sposta tra la distribuzione degli elementi di lavoro del pool di thread, l'esecuzione del finalizzatore e i costruttori di moduli e classi.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRHostProtectionManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)
- [Interfaccia IHostSecurityManager](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
- [Interfacce di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
