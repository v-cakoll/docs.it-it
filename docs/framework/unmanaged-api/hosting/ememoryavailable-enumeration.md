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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 76fc5f578e6da731ffd6406344d00cda8b57f493
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67772400"
---
# <a name="ememoryavailable-enumeration"></a>Enumerazione EMemoryAvailable
Contiene valori che indicano la quantità di memoria fisica disponibile nel computer. Questi valori eseguire il mapping logico agli eventi massimo e minimo della memoria restituita dal `CreateMemoryResourceNotification` funzione nell'API di Windows.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
typedef enum {  
    eMemoryAvailableLow     = 1,  
    eMemoryAvailableNeutral = 2,  
    eMemoryAvailableHigh    = 3   
} EMemoryAvailable;  
```  
  
## <a name="members"></a>Membri  
  
|Member|Descrizione|  
|------------|-----------------|  
|`eMemoryAvailableHigh`|Una notevole quantità di memoria fisica disponibile.|  
|`eMemoryAvailableLow`|Memoria fisica minima è disponibile.|  
|`eMemoryAvailableNeutral`|La memoria fisica disponibile è neutra.|  
  
## <a name="remarks"></a>Note  
 Questo valore viene passato dall'host per common language runtime (CLR) da tramite una chiamata ai [ICLRMemoryNotificationCallback](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md) (metodo).  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE.h  
  
 **Libreria:** MSCorEE.dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazioni di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
