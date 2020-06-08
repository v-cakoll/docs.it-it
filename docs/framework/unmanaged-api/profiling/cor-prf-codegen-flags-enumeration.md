---
title: Enumerazione COR_PRF_CODEGEN_FLAGS
ms.date: 03/30/2017
api_name:
- COR_PRF_CODEGEN_FLAGS
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_CODEGEN_FLAGS
helpviewer_keywords:
- COR_PRF_CODEGEN_FLAGS enumeration [.NET Framework profiling]
ms.assetid: 3e184022-0247-4824-a23d-6b29593d8d01
topic_type:
- apiref
ms.openlocfilehash: c2c7ae7a8930949c79b5e24e2da75f3b4649e7f6
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500988"
---
# <a name="cor_prf_codegen_flags-enumeration"></a>Enumerazione COR_PRF_CODEGEN_FLAGS
Definisce i flag di generazione del codice che possono essere impostati con il metodo [ICorProfilerFunctionControl:: SetCodegenFlags](icorprofilerfunctioncontrol-setcodegenflags-method.md) .  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
typedef enum {  
    COR_PRF_CODEGEN_DISABLE_INLINING =          0x0001,  
    COR_PRF_CODEGEN_DISABLE_ALL_OPTIMIZATIONS = 0x0002,  
} COR_PRF_CODEGEN_FLAGS;  
```  
  
## <a name="members"></a>Membri  
  
|Membro|Descrizione|  
|------------|-----------------|  
|`COR_PRF_CODEGEN_DISABLE_INLINING`|Nessuna funzione verrà inline nel corpo di questa funzione. Tuttavia, la funzione stessa può essere inline nei relativi chiamanti.|  
|`COR_PRF_CODEGEN_DISABLE_ALL_OPTIMIZATIONS`|Tutte le ottimizzazioni verranno disabilitate per il corpo di questa funzione. Tuttavia, la funzione stessa può comunque essere inline nei relativi chiamanti.|  
  
## <a name="remarks"></a>Osservazioni  
 L' `COR_PRF_CODEGEN_FLAGS` enumerazione viene usata dal metodo [ICorProfilerFunctionControl:: SetCodegenFlags](icorprofilerfunctioncontrol-setcodegenflags-method.md) per consentire al profiler di controllare la generazione del codice per la funzione ricompilata in JIT.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazioni di profilatura](profiling-enumerations.md)
