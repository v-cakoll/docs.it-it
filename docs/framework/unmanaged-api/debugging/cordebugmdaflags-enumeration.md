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
ms.openlocfilehash: 34a66a8afa118ecaaaeea0b7b78daaadf1da7509
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76778266"
---
# <a name="cordebugmdaflags-enumeration"></a>Enumerazione CorDebugMDAFlags
Specifica lo stato del thread su cui è attivato l'assistente al debug gestito.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
typedef enum CorDebugMDAFlags {  
    MDA_FLAG_SLIP = 0x2  
} CorDebugMDAFlags;  
```  
  
## <a name="members"></a>Membri  
  
|Member|Descrizione|  
|------------|-----------------|  
|`MDA_FLAG_SLIP`|Il thread in cui è stato attivato l'assistente al debug gestito è stato slittato dopo l'attivazione dell'assistente al debug gestito.|  
  
## <a name="remarks"></a>Note  
 Quando lo stack di chiamate non descrive più la posizione in cui è stato originariamente generato l'assistente al debug gestito, il thread viene considerato *slittato*. Si tratta di una circostanza insolita dall'esecuzione di un'operazione non valida al momento dell'uscita del thread.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazioni di debug](debugging-enumerations.md)
