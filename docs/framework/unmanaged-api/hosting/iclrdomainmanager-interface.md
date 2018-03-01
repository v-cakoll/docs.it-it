---
title: Interfaccia ICLRDomainManager
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICLRDomainManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDomainManager
helpviewer_keywords:
- ICLRDomainManager interface [.NET Framework hosting]
ms.assetid: f08b2390-d872-4521-a815-e9c237c4c45d
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 5681d4776205569ea23aef2acb6d07c059419018
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="iclrdomainmanager-interface"></a>Interfaccia ICLRDomainManager
Consente all'host specificare la gestione del dominio applicazione che verrà utilizzata per inizializzare il dominio applicazione predefinito e per specificare le proprietà di inizializzazione.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo SetAppDomainManagerType](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setappdomainmanagertype-method.md)|Specifica il tipo, derivato dal <xref:System.AppDomainManager?displayProperty=nameWithType> (classe), l'applicazione del gestore di dominio che verrà utilizzato per inizializzare il dominio applicazione predefinito.|  
|[Metodo SetPropertiesForDefaultAppDomain](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setpropertiesfordefaultappdomain-method.md)|Imposta le proprietà che verranno utilizzate per inizializzare il dominio applicazione predefinito.|  
  
## <a name="remarks"></a>Note  
 Per ottenere un'istanza di questa interfaccia, chiamare il [ICLRControl::](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) metodo con il tipo di gestore IID `IID_ICLRDomainManager`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Metahost. H  
  
 **Libreria:** inclusa come risorsa in MSCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfacce di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [Hosting](../../../../docs/framework/unmanaged-api/hosting/index.md)
