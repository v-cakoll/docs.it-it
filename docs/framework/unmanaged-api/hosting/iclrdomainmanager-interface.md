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
ms.openlocfilehash: dda243ccbf18f396c1bcc03358997ea0f06c42a8
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615709"
---
# <a name="iclrdomainmanager-interface"></a>Interfaccia ICLRDomainManager
Consente all'host di specificare il gestore di dominio dell'applicazione che verrà utilizzato per inizializzare il dominio applicazione predefinito e per specificare le proprietà di inizializzazione.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo SetAppDomainManagerType](iclrdomainmanager-setappdomainmanagertype-method.md)|Specifica il tipo, derivato dalla <xref:System.AppDomainManager?displayProperty=nameWithType> classe, del gestore del dominio dell'applicazione che verrà usato per inizializzare il dominio applicazione predefinito.|  
|[Metodo SetPropertiesForDefaultAppDomain](iclrdomainmanager-setpropertiesfordefaultappdomain-method.md)|Imposta le proprietà che verranno utilizzate per inizializzare il dominio applicazione predefinito.|  
  
## <a name="remarks"></a>Osservazioni  
 Per ottenere un'istanza di questa interfaccia, chiamare il metodo [ICLRControl:: GetCLRManager](iclrcontrol-getclrmanager-method.md) con l'IID di tipo Manager `IID_ICLRDomainManager` .  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** Metahost. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di hosting](hosting-interfaces.md)
- [Hosting](index.md)
