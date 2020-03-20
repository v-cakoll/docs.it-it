---
title: Enumerazione EMemoryAvailable
ms.date: 03/30/2017
api_name:
- EMemoryAvailable
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EMemoryAvailable
helpviewer_keywords:
- EMemoryAvailable enumeration [.NET Framework hosting]
ms.assetid: 38e72a06-dbed-473b-a59b-7e0b3ea4f2af
topic_type:
- apiref
ms.openlocfilehash: 0073a532f680d8764ec9e76ea22326a630457043
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176435"
---
# <a name="ememoryavailable-enumeration"></a>Enumerazione EMemoryAvailable
Contiene valori che indicano la quantità di memoria fisica libera nel computer. Questi valori mappano logicamente agli eventi per la `CreateMemoryResourceNotification` memoria alta e bassa restituita dalla funzione nell'API di Windows.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
typedef enum {  
    eMemoryAvailableLow     = 1,  
    eMemoryAvailableNeutral = 2,  
    eMemoryAvailableHigh    = 3
} EMemoryAvailable;  
```  
  
## <a name="members"></a>Members  
  
|Membro|Descrizione|  
|------------|-----------------|  
|`eMemoryAvailableHigh`|È disponibile un'molta memoria fisica.|  
|`eMemoryAvailableLow`|Pochissima memoria fisica è disponibile.|  
|`eMemoryAvailableNeutral`|La memoria fisica disponibile è neutra.|  
  
## <a name="remarks"></a>Osservazioni  
 Questo valore viene passato dall'host a Common Language Runtime (CLR) utilizzando una chiamata al metodo [ICLRMemoryNotificationCallback::OnMemoryNotification](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md) .  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE.h  
  
 **Biblioteca:** Mscoree  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazioni di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
