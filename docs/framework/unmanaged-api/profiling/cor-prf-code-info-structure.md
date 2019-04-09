---
title: Struttura COR_PRF_CODE_INFO
ms.date: 03/30/2017
api_name:
- COR_PRF_CODE_INFO
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_CODE_INFO
helpviewer_keywords:
- COR_PRF_CODE_INFO structure [.NET Framework profiling]
ms.assetid: cf30e27c-1f7e-43a2-ba1e-01e4137301db
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 56734a9971759b78a835917c4914cf55edaa47a4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59103285"
---
# <a name="corprfcodeinfo-structure"></a>Struttura COR_PRF_CODE_INFO
Rappresenta un blocco contiguo di codice nativo archiviato in memoria.  
  
## <a name="syntax"></a>Sintassi  
  
```  
typedef struct _COR_PRF_CODE_INFO {  
    UINT_PTR startAddress;  
    SIZE_T size;  
} COR_PRF_CODE_INFO;  
```  
  
## <a name="members"></a>Membri  
  
|Member|Descrizione|  
|------------|-----------------|  
|`startAddress`|Indirizzo iniziale del blocco contiguo di codice.|  
|`size`|Le dimensioni del blocco.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Strutture di profilatura](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
