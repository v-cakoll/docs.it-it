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
ms.openlocfilehash: 739b491d343c0eba76160c15719069ffae385f46
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73097966"
---
# <a name="cordebugjitcompilerflags-enumeration"></a>Enumerazione CorDebugJITCompilerFlags
Contiene valori che influenzano il comportamento del compilatore JIT gestito.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
typedef enum CorDebugJITCompilerFlags {  
  
    CORDEBUG_JIT_DEFAULT = 0x1,  
    CORDEBUG_JIT_DISABLE_OPTIMIZATION = 0x3,  
    CORDEBUG_JIT_ENABLE_ENC = 0x7  
  
} CorDebugJITCompilerFlags;  
```  
  
## <a name="members"></a>Members  
  
|Member|Descrizione|  
|------------|-----------------|  
|`CORDEBUG_JIT_DEFAULT`|Specifica che il compilatore deve tenere traccia dei dati di compilazione e consente le ottimizzazioni.|  
|`CORDEBUG_JIT_DISABLE_OPTIMIZATION`|Specifica che il compilatore deve tenere traccia dei dati di compilazione, ma disabilita le ottimizzazioni.|  
|`CORDEBUG_JIT_ENABLE_ENC`|Specifica che il compilatore deve tenere traccia dei dati di compilazione, Disabilita le ottimizzazioni e Abilita le tecnologie di modifica e continuazione.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazioni di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
