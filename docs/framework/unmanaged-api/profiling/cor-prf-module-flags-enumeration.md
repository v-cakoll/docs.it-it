---
title: Enumerazione COR_PRF_MODULE_FLAGS
ms.date: 03/30/2017
api_name:
- COR_PRF_MODULE_FLAGS
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_MODULE_FLAGS
helpviewer_keywords:
- COR_PRF_MODULE_FLAGS enumeration [.NET Framework profiling]
ms.assetid: 7bc3a938-0df1-4739-9ff1-89cff454b704
topic_type:
- apiref
ms.openlocfilehash: bdbf93ba4df50cf26538f0e527fdc3c982bb274e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447326"
---
# <a name="cor_prf_module_flags-enumeration"></a>Enumerazione COR_PRF_MODULE_FLAGS
Specifica le proprietà di un modulo.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
typedef enum  
{  
    COR_PRF_MODULE_DISK             = 0x00000001,  
    COR_PRF_MODULE_NGEN             = 0x00000002,  
    COR_PRF_MODULE_DYNAMIC          = 0x00000004,  
    COR_PRF_MODULE_COLLECTIBLE      = 0x00000008,  
    COR_PRF_MODULE_RESOURCE         = 0x00000010,  
    COR_PRF_MODULE_FLAT_LAYOUT      = 0x00000020,  
    COR_PRF_MODULE_WINDOWS_RUNTIME  = 0x00000040  
}   COR_PRF_MODULE_FLAGS;  
```  
  
## <a name="members"></a>Membri  
  
|Membro|description|  
|------------|-----------------|  
|COR_PRF_MODULE_DISK|Il modulo è stato caricato dal disco.|  
|COR_PRF_MODULE_NGEN|Il modulo è stato generato dal generatore di immagini native (Ngen. exe).|  
|COR_PRF_MODULE_DYNAMIC|Il modulo è stato creato da metodi nello spazio dei nomi <xref:System.Reflection.Emit?displayProperty=nameWithType>.|  
|COR_PRF_MODULE_COLLECTIBLE|La durata del modulo viene gestita dal Garbage Collector.|  
|COR_PRF_MODULE_RESOURCE|Il modulo non contiene metadati e viene usato esclusivamente come risorsa. L'equivalente gestito di questo bit è il metodo <xref:System.Reflection.Module.IsResource%2A?displayProperty=nameWithType>.|  
|COR_PRF_MODULE_FLAT_LAYOUT|Il layout del modulo in memoria è flat e non è mappato. Se questo bit è impostato in un modulo, i profiler che leggono le informazioni direttamente dall'intestazione del file eseguibile portabile (PE) dovranno prestare attenzione durante l'interpretazione degli indirizzi virtuali relativi (RVA) nell'intestazione.|  
|COR_PRF_MODULE_WINDOWS_RUNTIME|Il flag del tipo di contenuto Windows Runtime viene impostato nei metadati per l'assembly di questo modulo. Questo è il caso per tutti i moduli di metadati di Windows (. winmd).|  
  
## <a name="remarks"></a>Osservazioni  
 I bit da COR_PRF_MODULE_FLAGS vengono restituiti al profiler nel parametro di output `pdwModuleFlags` del metodo [ICorProfilerInfo3:: GetModuleInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getmoduleinfo2-method.md) . Alcune combinazioni di due o più flag sono possibili, ma non tutte le combinazioni sono possibili.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazioni di profilatura](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
