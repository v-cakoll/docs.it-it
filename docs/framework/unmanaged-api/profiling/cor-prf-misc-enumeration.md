---
title: Enumerazione COR_PRF_MISC
ms.date: 03/30/2017
api_name:
- COR_PRF_MISC
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_MISC
helpviewer_keywords:
- COR_PRF_MISC enumeration [.NET Framework profiling]
ms.assetid: 619bb5de-e309-48b6-a3af-32d935a0ff46
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c8f4cffd718fffa9145e1082092ecec45b80a2ec
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="corprfmisc-enumeration"></a>Enumerazione COR_PRF_MISC
Contiene valori costanti che specificano identificatori speciali.  
  
## <a name="syntax"></a>Sintassi  
  
```  
typedef enum {  
    PROFILER_PARENT_UNKNOWN = 0xFFFFFFFD,  
    PROFILER_GLOBAL_CLASS   = 0xFFFFFFFE,  
    PROFILER_GLOBAL_MODULE  = 0xFFFFFFFF  
} COR_PRF_MISC;  
```  
  
## <a name="members"></a>Membri  
  
|Membro|Descrizione|  
|------------|-----------------|  
|`PROFILER_PARENT_UNKNOWN`|L'identificatore predefinito utilizzato dai [ICorProfilerInfo:: GetModuleInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmoduleinfo-method.md) per un modulo che non è stato ancora associato a un assembly.|  
|`PROFILER_GLOBAL_CLASS`|L'identificatore di classe predefinito per le costanti globali che non appartengono a una classe.|  
|`PROFILER_GLOBAL_MODULE`|Identificatore del modulo predefinito per oggetti globali che non appartengono a un modulo.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Enumerazioni di profilatura](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
