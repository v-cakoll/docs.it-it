---
title: Enumerazione HOST_TYPE
ms.date: 03/30/2017
api_name:
- HOST_TYPE
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- HOST_TYPE
helpviewer_keywords:
- HOST_TYPE enumeration [.NET Framework hosting]
ms.assetid: 51f848be-84c5-4036-9839-c762c576bbf5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: caf76fa7962de9392b06591777ac862aa548d20d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779557"
---
# <a name="hosttype-enumeration"></a>Enumerazione HOST_TYPE
Contiene valori che specificano il tipo di host che esegue un'applicazione.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
typedef enum {  
    HOST_TYPE_DEFAULT     = 0x0,  
    HOST_TYPE_APPLAUNCH   = 0x1,  
    HOST_TYPE_CORFLAG     = 0x2  
} HOST_TYPE;  
```  
  
## <a name="members"></a>Membri  
  
|Member|Descrizione|  
|------------|-----------------|  
|`HOST_TYPE_APPLAUNCH`|Avviare l'applicazione da AppLaunch.exe.<br /><br /> Utilizzare questo valore per le applicazioni parzialmente attendibili.|  
|`HOST_TYPE_CORFLAG`|Avviare l'applicazione direttamente. Vale a dire, avviare l'applicazione da un proprio file .exe.<br /><br /> Utilizzare questo valore per le applicazioni completamente attendibili.|  
|`HOST_TYPE_DEFAULT`|Uguale a HOST_TYPE_APPLAUNCH.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE.h  
  
 **Libreria:** MSCorEE.dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazioni di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
