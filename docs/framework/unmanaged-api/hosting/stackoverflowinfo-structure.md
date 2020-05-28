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
ms.openlocfilehash: 941093b9a0856c2b716ba359c854473f3c9ea26a
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84006519"
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
  
## <a name="members"></a>Membri  
  
|Membro|Descrizione|  
|------------|-----------------|  
|`soType`|Valore dell'enumerazione [StackOverflowType](stackoverflowtype-enumeration.md) che specifica il tipo di overflow.|  
|`pExceptionInfo`|Puntatore a un oggetto Win32 `EXCEPTION_POINTERS` , che contiene un record di eccezione con una descrizione indipendente dal computer di un'eccezione e un record di contesto con una descrizione dipendente dal computer del contesto del processore al momento dell'eccezione.|  
  
## <a name="remarks"></a>Commenti  
 Un `StackOverflowInfo` oggetto viene passato al metodo [IActionOnCLREvent:: OnEvent](iactiononclrevent-onevent-method.md) per `Event_StackOverflow` gli eventi.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. idl  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Strutture di hosting](hosting-structures.md)
