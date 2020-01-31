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
ms.openlocfilehash: 0f6fb469aa9d6d40b762bfd2feec28c28299732f
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76867113"
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
  
|Member|Descrizione|  
|------------|-----------------|  
|COR_PRF_MODULE_DISK|Il modulo è stato caricato dal disco.|  
|COR_PRF_MODULE_NGEN|Il modulo è stato generato dal generatore di immagini native (Ngen. exe).|  
|COR_PRF_MODULE_DYNAMIC|Il modulo è stato creato da metodi nello spazio dei nomi <xref:System.Reflection.Emit?displayProperty=nameWithType>.|  
|COR_PRF_MODULE_COLLECTIBLE|La durata del modulo viene gestita dal Garbage Collector.|  
|COR_PRF_MODULE_RESOURCE|Il modulo non contiene metadati e viene usato esclusivamente come risorsa. L'equivalente gestito di questo bit è il metodo <xref:System.Reflection.Module.IsResource%2A?displayProperty=nameWithType>.|  
|COR_PRF_MODULE_FLAT_LAYOUT|Il layout del modulo in memoria è flat e non è mappato. Se questo bit è impostato in un modulo, i profiler che leggono le informazioni direttamente dall'intestazione del file eseguibile portabile (PE) dovranno prestare attenzione durante l'interpretazione degli indirizzi virtuali relativi (RVA) nell'intestazione.|  
|COR_PRF_MODULE_WINDOWS_RUNTIME|Il flag del tipo di contenuto Windows Runtime viene impostato nei metadati per l'assembly di questo modulo. Questo è il caso per tutti i moduli di metadati di Windows (. winmd).|  
  
## <a name="remarks"></a>Note  
 I bit da COR_PRF_MODULE_FLAGS vengono restituiti al profiler nel parametro di output `pdwModuleFlags` del metodo [ICorProfilerInfo3:: GetModuleInfo2](icorprofilerinfo3-getmoduleinfo2-method.md) . Alcune combinazioni di due o più flag sono possibili, ma non tutte le combinazioni sono possibili.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazioni di profilatura](profiling-enumerations.md)
