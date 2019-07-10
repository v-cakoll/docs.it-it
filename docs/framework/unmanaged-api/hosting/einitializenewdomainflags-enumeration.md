---
title: Enumerazione EInitializeNewDomainFlags
ms.date: 03/30/2017
api_name:
- EInitializeNewDomainFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EInitializeNewDomainFlags
helpviewer_keywords:
- EInitializeNewDomainFlags enumeration [.NET Framework hosting]
ms.assetid: 3a120ab2-f5ef-4c9b-8595-d3ed7247c342
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d69b12404459de5dbc1c7748deee6ca09c1e5182
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67772416"
---
# <a name="einitializenewdomainflags-enumeration"></a>Enumerazione EInitializeNewDomainFlags
Consente all'host di fornire il runtime con informazioni sull'inizializzazione di un dominio dell'applicazione.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
typedef enum {  
    eInitializeNewDomainFlags_None              = 0x0000,  
    eInitializeNewDomainFlags_NoSecurityChanges = 0x0002  
} EInitializeNewDomainFlags;  
```  
  
## <a name="members"></a>Membri  
  
|Member|Descrizione|  
|------------|-----------------|  
|`eInitializeNewDomainFlags_None`|Nessun flag.|  
|`eInitializeNewDomainFlags_NoSecurityChanges`|Indica che l'host non apporterà le modifiche allo stato di sicurezza del dominio dell'applicazione in a common language runtime (CLR) di <xref:System.AppDomainManager.InitializeNewDomain%2A> (metodo).|  
  
## <a name="remarks"></a>Note  
 Il [ICLRDomainManager](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setappdomainmanagertype-method.md) metodo accetta un parametro di tipo `EInitializeNewDomainFlags`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE.h  
  
 **Libreria:** MSCorEE.dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazioni di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
- [Metodo SetAppDomainManagerType](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setappdomainmanagertype-method.md)
