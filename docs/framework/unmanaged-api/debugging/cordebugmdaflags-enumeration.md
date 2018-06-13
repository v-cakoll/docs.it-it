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
ms.openlocfilehash: ac4a8a0c13ba6aa0d5c65ec7fa1aa3b771c964eb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33404859"
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
|`MDA_FLAG_SLIP`|Il thread su cui è stato attivato l'assistente al debug gestito è stato ignorato poiché è stato attivato l'assistente al debug gestito.|  
  
## <a name="remarks"></a>Note  
 Quando lo stack di chiamate non descrive in cui è stato originariamente generato l'assistente al debug gestito, il thread è considerato *ignorato*. Si tratta di una situazione insolita causata dall'esecuzione del thread dell'operazione non valida all'uscita.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cordebug. idl, Cordebug. H  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Enumerazioni di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
