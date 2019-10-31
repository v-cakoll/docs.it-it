---
title: Struttura StackOverflowInfo
ms.date: 03/30/2017
api_name:
- StackOverflowInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- StackOverflowInfo
helpviewer_keywords:
- StackOverflowInfo structure [.NET Framework hosting]
ms.assetid: 519389f2-0217-436c-99d4-93a76ebce5b5
topic_type:
- apiref
ms.openlocfilehash: 1072026f92edbc646653c6dd74ec8e22d5b887e5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73105916"
---
# <a name="stackoverflowinfo-structure"></a>Struttura StackOverflowInfo
Archivia il tipo di overflow che si è verificato e le informazioni sull'eccezione generata a causa dell'overflow.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
typedef struct _StackOverflowInfo {  
    StackOverflowType   soType;  
    EXCEPTION_POINTERS  *pExceptionInfo;  
} StackOverflowInfo;  
```  
  
## <a name="members"></a>Members  
  
|Member|Descrizione|  
|------------|-----------------|  
|`soType`|Valore dell'enumerazione [StackOverflowType](../../../../docs/framework/unmanaged-api/hosting/stackoverflowtype-enumeration.md) che specifica il tipo di overflow.|  
|`pExceptionInfo`|Puntatore a un oggetto `EXCEPTION_POINTERS` Win32, che contiene un record di eccezione con una descrizione indipendente dal computer di un'eccezione e un record di contesto con una descrizione dipendente dal computer del contesto del processore al momento dell'eccezione.|  
  
## <a name="remarks"></a>Note  
 Un oggetto `StackOverflowInfo` viene passato al metodo [IActionOnCLREvent:: OnEvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md) per `Event_StackOverflow` eventi.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. idl  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Strutture di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
