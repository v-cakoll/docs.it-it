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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ad04e90d1855e2de89aa6515bf16424de95ffa26
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54696438"
---
# <a name="corprfmoduleflags-enumeration"></a>Enumerazione COR_PRF_MODULE_FLAGS
Specifica le proprietà di un modulo.  
  
## <a name="syntax"></a>Sintassi  
  
```  
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
  
|Membro|Descrizione|  
|------------|-----------------|  
|COR_PRF_MODULE_DISK|Il modulo è stato caricato dal disco.|  
|COR_PRF_MODULE_NGEN|Il modulo è stato generato dal generatore di immagini Native (Ngen.exe).|  
|COR_PRF_MODULE_DYNAMIC|Il modulo è stato creato dai metodi nel <xref:System.Reflection.Emit?displayProperty=nameWithType> dello spazio dei nomi.|  
|COR_PRF_MODULE_COLLECTIBLE|La durata del modulo viene gestita dal garbage collector.|  
|COR_PRF_MODULE_RESOURCE|Il modulo non contiene metadati e viene usato esclusivamente come risorsa. L'equivalente gestito di questo bit è la <xref:System.Reflection.Module.IsResource%2A?displayProperty=nameWithType> (metodo).|  
|COR_PRF_MODULE_FLAT_LAYOUT|Il layout del modulo in memoria è flat, non è mappata. Se un modulo ha questo bit impostato, i profiler che leggono informazioni direttamente dall'intestazione del file (PE) eseguibile portabile saranno necessario prestare attenzione durante l'interpretazione di indirizzi virtuali relativi (RVA) nell'intestazione.|  
|COR_PRF_MODULE_WINDOWS_RUNTIME|Il flag di tipo di contenuto di Windows Runtime è impostato nei metadati per l'assembly del modulo. Ciò avviene per tutti i moduli di metadati Windows (con estensione winmd).|  
  
## <a name="remarks"></a>Note  
 BITS da COR_PRF_MODULE_FLAGS vengono restituiti al profiler, vedere la `pdwModuleFlags` parametro di output la [ICorProfilerInfo3::GetModuleInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getmoduleinfo2-method.md) (metodo). Alcune combinazioni di due o più flag sono possibili, ma non tutte le combinazioni possibili.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Enumerazioni di profilatura](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
