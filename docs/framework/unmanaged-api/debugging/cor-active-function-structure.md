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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c0400da0cd29d642a1be42be7e2b22213ae54b94
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59121771"
---
# <a name="coractivefunction-structure"></a>Struttura COR_ACTIVE_FUNCTION
Contiene informazioni sulle funzioni attualmente attive nei frame di un thread. Questa struttura viene utilizzata per la [ICorDebugThread2::GetActiveFunctions](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-getactivefunctions-method.md) (metodo).  
  
## <a name="syntax"></a>Sintassi  
  
```  
typedef struct  _COR_ACTIVE_FUNCTION {  
    ICorDebugAppDomain   *pAppDomain;  
    ICorDebugModule      *pModule;  
    ICorDebugFunction2   *pFunction;  
    ULONG32              ilOffset;  
    ULONG32              flags;  
} COR_ACTIVE_FUNCTION;  
```  
  
## <a name="members"></a>Membri  
  
|Member|Descrizione|  
|------------|-----------------|  
|`pAppDomain`|Puntatore al proprietario del dominio dell'applicazione dei `ilOffset` campo.|  
|`pModule`|Puntatore al proprietario del modulo di `ilOffset` campo.|  
|`pFunction`|Puntatore al proprietario della funzione di `ilOffset` campo.|  
|`ilOffset`|Offset Microsoft intermediate language (MSIL) del frame.|  
|`flags`|Riservato per un'estendibilità futura.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Strutture di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [Debug](../../../../docs/framework/unmanaged-api/debugging/index.md)
