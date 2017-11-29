---
title: Enumerazione EMemoryAvailable
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: EMemoryAvailable
api_location: mscoree.dll
api_type: COM
f1_keywords: EMemoryAvailable
helpviewer_keywords: EMemoryAvailable enumeration [.NET Framework hosting]
ms.assetid: 38e72a06-dbed-473b-a59b-7e0b3ea4f2af
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c378f2cd9b033e578ff15472a10a6dc295ad6539
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="ememoryavailable-enumeration"></a>Enumerazione EMemoryAvailable
Contiene valori che indicano la quantità di memoria fisica disponibile nel computer. Questi valori sono logicamente associati agli eventi massimo e minimo della memoria restituita dal `CreateMemoryResourceNotification` funzione nell'API Win32.  
  
## <a name="syntax"></a>Sintassi  
  
```  
typedef enum {  
    eMemoryAvailableLow     = 1,  
    eMemoryAvailableNeutral = 2,  
    eMemoryAvailableHigh    = 3   
} EMemoryAvailable;  
```  
  
## <a name="members"></a>Membri  
  
|Membro|Descrizione|  
|------------|-----------------|  
|`eMemoryAvailableHigh`|Una notevole quantità di memoria fisica disponibile.|  
|`eMemoryAvailableLow`|Poca memoria fisica disponibile.|  
|`eMemoryAvailableNeutral`|La memoria fisica disponibile è neutra.|  
  
## <a name="remarks"></a>Note  
 Questo valore viene passato dall'host per common language runtime (CLR) tramite una chiamata al [:: OnMemoryNotification](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md) metodo.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Mscoree. H  
  
 **Libreria:** MSCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Enumerazioni di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
