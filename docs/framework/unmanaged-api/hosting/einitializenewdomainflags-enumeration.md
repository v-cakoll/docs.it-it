---
title: Enumerazione EInitializeNewDomainFlags
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: EInitializeNewDomainFlags
api_location: mscoree.dll
api_type: COM
f1_keywords: EInitializeNewDomainFlags
helpviewer_keywords: EInitializeNewDomainFlags enumeration [.NET Framework hosting]
ms.assetid: 3a120ab2-f5ef-4c9b-8595-d3ed7247c342
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: bee1c5086502a9675e8149e7d6c9bc72f573815c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="einitializenewdomainflags-enumeration"></a>Enumerazione EInitializeNewDomainFlags
Consente all'host di fornire il runtime con informazioni sull'inizializzazione di un dominio applicazione.  
  
## <a name="syntax"></a>Sintassi  
  
```  
typedef enum {  
    eInitializeNewDomainFlags_None              = 0x0000,  
    eInitializeNewDomainFlags_NoSecurityChanges = 0x0002  
} EInitializeNewDomainFlags;  
```  
  
## <a name="members"></a>Membri  
  
|Membro|Descrizione|  
|------------|-----------------|  
|`eInitializeNewDomainFlags_None`|Nessun flag.|  
|`eInitializeNewDomainFlags_NoSecurityChanges`|Informa common language runtime (CLR) che l'host non verrà apportate modifiche allo stato di sicurezza del dominio applicazione di <xref:System.AppDomainManager.InitializeNewDomain%2A> metodo.|  
  
## <a name="remarks"></a>Note  
 Il [ICLRDomainManager](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setappdomainmanagertype-method.md) metodo accetta un parametro di tipo `EInitializeNewDomainFlags`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Mscoree. H  
  
 **Libreria:** MSCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Enumerazioni di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)  
 [SetAppDomainManagerType (metodo)](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setappdomainmanagertype-method.md)
