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
ms.openlocfilehash: 7ff10f84d8d270d31c5d560fb3c9bd3c81cf3e24
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616229"
---
# <a name="einitializenewdomainflags-enumeration"></a>Enumerazione EInitializeNewDomainFlags
Consente all'host di fornire al Runtime informazioni sull'inizializzazione di un dominio applicazione.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
typedef enum {  
    eInitializeNewDomainFlags_None              = 0x0000,  
    eInitializeNewDomainFlags_NoSecurityChanges = 0x0002  
} EInitializeNewDomainFlags;  
```  
  
## <a name="members"></a>Membri  
  
|Membro|Description|  
|------------|-----------------|  
|`eInitializeNewDomainFlags_None`|Nessun flag.|  
|`eInitializeNewDomainFlags_NoSecurityChanges`|Informa il Common Language Runtime (CLR) che l'host non apporterà modifiche allo stato di sicurezza del dominio dell'applicazione nel <xref:System.AppDomainManager.InitializeNewDomain%2A> metodo.|  
  
## <a name="remarks"></a>Osservazioni  
 Il metodo [ICLRDomainManager:: SetAppDomainManagerType](iclrdomainmanager-setappdomainmanagertype-method.md) accetta un parametro di tipo `EInitializeNewDomainFlags` .  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazioni di hosting](hosting-enumerations.md)
- [Metodo SetAppDomainManagerType](iclrdomainmanager-setappdomainmanagertype-method.md)
