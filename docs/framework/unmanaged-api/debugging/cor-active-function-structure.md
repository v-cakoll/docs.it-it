---
title: Struttura COR_ACTIVE_FUNCTION
ms.date: 03/30/2017
api_name:
- COR_ACTIVE_FUNCTION
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_ACTIVE_FUNCTION
helpviewer_keywords:
- COR_ACTIVE_FUNCTION structure [.NET Framework debugging]
ms.assetid: ed86185f-2152-459c-961f-10c06d62e83f
topic_type:
- apiref
ms.openlocfilehash: cbc272070e9eb6810b34ec1f3fdc9e944c624cd3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132387"
---
# <a name="cor_active_function-structure"></a>Struttura COR_ACTIVE_FUNCTION
Contiene informazioni sulle funzioni attualmente attive nei frame di un thread. Questa struttura viene utilizzata dal metodo [ICorDebugThread2:: GetActiveFunctions](icordebugthread2-getactivefunctions-method.md) .  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
typedef struct  _COR_ACTIVE_FUNCTION {  
    ICorDebugAppDomain   *pAppDomain;  
    ICorDebugModule      *pModule;  
    ICorDebugFunction2   *pFunction;  
    ULONG32              ilOffset;  
    ULONG32              flags;  
} COR_ACTIVE_FUNCTION;  
```  
  
## <a name="members"></a>Members  
  
|Member|Descrizione|  
|------------|-----------------|  
|`pAppDomain`|Puntatore al proprietario del dominio dell'applicazione del campo `ilOffset`.|  
|`pModule`|Puntatore al proprietario del modulo del campo `ilOffset`.|  
|`pFunction`|Puntatore al proprietario della funzione del campo `ilOffset`.|  
|`ilOffset`|Offset MSIL (Microsoft Intermediate Language) del frame.|  
|`flags`|Riservato per l'estendibilità futura.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug. idl  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Strutture di debug](debugging-structures.md)
- [Debug](index.md)
