---
title: Enumerazione CorDebugMDAFlags
ms.date: 03/30/2017
api_name:
- CorDebugMDAFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugMDAFlags
helpviewer_keywords:
- CorDebugMDAFlags enumeration [.NET Framework debugging]
ms.assetid: 7c0c92fe-8bd2-477f-b307-aca0143732ca
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b7f20dec86a85be85472037f58a2bd2002d9be1e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54620393"
---
# <a name="cordebugmdaflags-enumeration"></a>Enumerazione CorDebugMDAFlags
Specifica lo stato del thread su cui è attivato l'assistente al debug gestito.  
  
## <a name="syntax"></a>Sintassi  
  
```  
typedef enum CorDebugMDAFlags {  
    MDA_FLAG_SLIP = 0x2  
} CorDebugMDAFlags;  
```  
  
## <a name="members"></a>Membri  
  
|Membro|Descrizione|  
|------------|-----------------|  
|`MDA_FLAG_SLIP`|Il thread in cui è stato attivato l'assistente al debug gestito è stato ignorato poiché è stato attivato l'assistente al debug gestito.|  
  
## <a name="remarks"></a>Note  
 Quando lo stack di chiamate non descrive in cui è stato originariamente generato l'assistente al debug gestito, il thread è considerato *slittato*. Si tratta di una situazione insolita causata dall'esecuzione del thread di un'operazione non valida all'uscita dal.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Enumerazioni di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
