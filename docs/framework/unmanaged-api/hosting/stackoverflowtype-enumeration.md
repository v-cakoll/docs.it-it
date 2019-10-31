---
title: Enumerazione StackOverflowType
ms.date: 03/30/2017
api_name:
- StackOverflowType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- StackOverflowType
helpviewer_keywords:
- StackOverflowType enumeration [.NET Framework hosting]
ms.assetid: dab648ad-972b-479c-b129-b4c1dcbd932e
topic_type:
- apiref
ms.openlocfilehash: f09c6bb79d7bd28f4d8b74237b6f343a07b79062
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141478"
---
# <a name="stackoverflowtype-enumeration"></a>Enumerazione StackOverflowType
Contiene valori che indicano la cause sottostante di un evento di overflow dello stack.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
typedef enum {  
    SO_Managed,  
    SO_ClrEngine,  
    SO_Other  
} StackOverflowType;  
```  
  
## <a name="members"></a>Members  
  
|Member|Descrizione|  
|------------|-----------------|  
|`SO_ClrEngine`|L'overflow dello stack è stato causato dal motore di esecuzione.|  
|`SO_Managed`|L'overflow dello stack è stato causato dal codice gestito.|  
|`SO_Other`|L'overflow dello stack è stato causato da codice non gestito.|  
  
## <a name="remarks"></a>Note  
 Queste informazioni vengono passate all'host tramite una chiamata al metodo [IActionOnCLREvent:: OnEvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md) .  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** MSCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazioni di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
