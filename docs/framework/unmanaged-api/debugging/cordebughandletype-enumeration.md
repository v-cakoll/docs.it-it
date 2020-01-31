---
title: Enumerazione CorDebugHandleType
ms.date: 03/30/2017
api_name:
- CorDebugHandleType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugHandleType
helpviewer_keywords:
- CorDebugHandleType enumeration [.NET Framework debugging]
ms.assetid: 84296b55-c2c5-424c-ac9c-8e28e2895945
topic_type:
- apiref
ms.openlocfilehash: 15572037940f7c45ec5dcb7e34599756e15fd3bd
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793904"
---
# <a name="cordebughandletype-enumeration"></a>Enumerazione CorDebugHandleType
Indica il tipo di handle.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
typedef enum CorDebugHandleType {  
    HANDLE_STRONG                  = 1,  
    HANDLE_WEAK_TRACK_RESURRECTION = 2  
} CorDebugHandleType;  
```  
  
## <a name="members"></a>Membri  
  
|Member|Descrizione|  
|------------|-----------------|  
|`HANDLE_STRONG`|Il punto di controllo è sicuro e impedisce a un oggetto di essere recuperato da Garbage Collection.|  
|`HANDLE_WEAK_TRACK_RESURRECTION`|L'handle è debole, che non impedisce che un oggetto venga recuperato dal Garbage Collection.<br /><br /> Quando l'oggetto viene raccolto, l'handle diventa non valido.|  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazioni di debug](debugging-enumerations.md)
