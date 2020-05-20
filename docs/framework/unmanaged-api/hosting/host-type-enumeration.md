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
ms.openlocfilehash: e8dda83df8a320733f45dbcc13599cdf37d26492
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83617152"
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
  
## <a name="members"></a>Membri  
  
|Membro|Description|  
|------------|-----------------|  
|`HOST_TYPE_APPLAUNCH`|Avviare l'applicazione da AppLaunch. exe.<br /><br /> Utilizzare questo valore per le applicazioni parzialmente attendibili.|  
|`HOST_TYPE_CORFLAG`|Avviare direttamente l'applicazione. Ovvero avviare l'applicazione dal proprio file con estensione exe.<br /><br /> Utilizzare questo valore per le applicazioni completamente attendibili.|  
|`HOST_TYPE_DEFAULT`|Uguale a HOST_TYPE_APPLAUNCH.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazioni di hosting](hosting-enumerations.md)
