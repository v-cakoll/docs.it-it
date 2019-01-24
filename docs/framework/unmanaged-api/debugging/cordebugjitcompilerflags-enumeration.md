---
title: Enumerazione CorDebugJITCompilerFlags
ms.date: 03/30/2017
api_name:
- CorDebugJITCompilerFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugJITCompilerFlags
helpviewer_keywords:
- CorDebugJITCompilerFlags enumeration [.NET Framework debugging]
ms.assetid: c0774f70-5bed-45e8-9922-fdad778c4c33
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 512122d264e0817b89e8a371f57f11d31f7c4380
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54639638"
---
# <a name="cordebugjitcompilerflags-enumeration"></a>Enumerazione CorDebugJITCompilerFlags
Contiene valori che influenzano il comportamento del compilatore JIT gestito.  
  
## <a name="syntax"></a>Sintassi  
  
```  
typedef enum CorDebugJITCompilerFlags {  
  
    CORDEBUG_JIT_DEFAULT = 0x1,  
    CORDEBUG_JIT_DISABLE_OPTIMIZATION = 0x3,  
    CORDEBUG_JIT_ENABLE_ENC = 0x7  
  
} CorDebugJITCompilerFlags;  
```  
  
## <a name="members"></a>Membri  
  
|Membro|Descrizione|  
|------------|-----------------|  
|`CORDEBUG_JIT_DEFAULT`|Specifica che il compilatore deve tenere traccia dei dati di compilazione e consentire l'ottimizzazione.|  
|`CORDEBUG_JIT_DISABLE_OPTIMIZATION`|Specifica che il compilatore deve tenere traccia dei dati di compilazione, ma disabilitare le ottimizzazioni.|  
|`CORDEBUG_JIT_ENABLE_ENC`|Specifica che il compilatore deve tenere traccia dei dati di compilazione, disabilitare le ottimizzazioni e Abilita modifica e continuazione tecnologie.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Enumerazioni di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
