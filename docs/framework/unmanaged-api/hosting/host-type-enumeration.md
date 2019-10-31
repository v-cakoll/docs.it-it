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
ms.openlocfilehash: cc0cea10b4a209583fb7afb551a6b80d52ad7f62
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127021"
---
# <a name="host_type-enumeration"></a>Enumerazione HOST_TYPE
Contiene valori che specificano il tipo di host che avvia un'applicazione.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
typedef enum {  
    HOST_TYPE_DEFAULT     = 0x0,  
    HOST_TYPE_APPLAUNCH   = 0x1,  
    HOST_TYPE_CORFLAG     = 0x2  
} HOST_TYPE;  
```  
  
## <a name="members"></a>Members  
  
|Member|Descrizione|  
|------------|-----------------|  
|`HOST_TYPE_APPLAUNCH`|Avviare l'applicazione da AppLaunch. exe.<br /><br /> Utilizzare questo valore per le applicazioni parzialmente attendibili.|  
|`HOST_TYPE_CORFLAG`|Avviare direttamente l'applicazione. Ovvero avviare l'applicazione dal proprio file con estensione exe.<br /><br /> Utilizzare questo valore per le applicazioni completamente attendibili.|  
|`HOST_TYPE_DEFAULT`|Uguale a HOST_TYPE_APPLAUNCH.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** MSCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazioni di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
