---
title: Interfaccia ICLRDomainManager
ms.date: 03/30/2017
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
ms.openlocfilehash: aa874205cf14232e7a69ed2215086e33c0beab4d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129335"
---
# <a name="iclrdomainmanager-interface"></a>Interfaccia ICLRDomainManager
Consente all'host di specificare il gestore di dominio dell'applicazione che verrà utilizzato per inizializzare il dominio applicazione predefinito e per specificare le proprietà di inizializzazione.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo SetAppDomainManagerType](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setappdomainmanagertype-method.md)|Specifica il tipo, derivato dalla classe <xref:System.AppDomainManager?displayProperty=nameWithType>, del gestore del dominio dell'applicazione che verrà usato per inizializzare il dominio applicazione predefinito.|  
|[Metodo SetPropertiesForDefaultAppDomain](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setpropertiesfordefaultappdomain-method.md)|Imposta le proprietà che verranno utilizzate per inizializzare il dominio applicazione predefinito.|  
  
## <a name="remarks"></a>Note  
 Per ottenere un'istanza di questa interfaccia, chiamare il metodo [ICLRControl:: GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) con l'IID del tipo di gestione `IID_ICLRDomainManager`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Metahost. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [Hosting](../../../../docs/framework/unmanaged-api/hosting/index.md)
