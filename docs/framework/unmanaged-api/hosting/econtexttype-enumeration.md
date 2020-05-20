---
title: Enumerazione EContextType
ms.date: 03/30/2017
api_name:
- EContextType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EContextType
helpviewer_keywords:
- EContextType enumeration [.NET Framework hosting]
ms.assetid: 92b926a9-b87e-408a-9036-df7b752c9492
topic_type:
- apiref
ms.openlocfilehash: ceb68410e808bf7843149e3f05a39c7a98d0c000
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616294"
---
# <a name="econtexttype-enumeration"></a>Enumerazione EContextType
Descrive il contesto di sicurezza del thread attualmente in esecuzione.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
typedef enum {  
    eCurrentContext    = 0x00,  
    eRestrictedContext = 0x01  
} EContextType;  
```  
  
## <a name="members"></a>Membri  
  
|Membro|Description|  
|------------|-----------------|  
|`eCurrentContext`|Indica il contesto nel thread corrente nel momento in cui il Common Language Runtime (CLR) chiama il metodo [IHostSecurityManager:: GetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md) o il contesto richiesto da CLR in una chiamata al metodo [IHostSecurityManager:: SetSecurityContext](ihostsecuritymanager-setsecuritycontext-method.md) .|  
|`eRestrictedContext`|Indica un contesto in cui l'host dispone di privilegi più bassi, ad esempio i costruttori di Garbage Collector o di classe o di modulo.|  
  
## <a name="remarks"></a>Osservazioni  
 CLR fornisce uno dei `EContextType` valori come valore di parametro nelle chiamate ai `IHostSecurityManager::GetSecurityContext` `IHostSecurityManager::SetSecurityContext` metodi e.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IHostSecurityContext](ihostsecuritycontext-interface.md)
- [Interfaccia IHostSecurityManager](ihostsecuritymanager-interface.md)
- [Enumerazioni di hosting](hosting-enumerations.md)
