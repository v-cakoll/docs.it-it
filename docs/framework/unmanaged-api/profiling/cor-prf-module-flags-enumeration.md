---
title: Enumerazione COR_PRF_MODULE_FLAGS
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_PRF_MODULE_FLAGS
api_location: mscorwks.dll
api_type: COM
f1_keywords: COR_PRF_MODULE_FLAGS
helpviewer_keywords: COR_PRF_MODULE_FLAGS enumeration [.NET Framework profiling]
ms.assetid: 7bc3a938-0df1-4739-9ff1-89cff454b704
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 54a8ee366431360f7b653b48f4ce407a35f8465b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
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
|COR_PRF_MODULE_DYNAMIC|Il modulo è stato creato dai metodi di <xref:System.Reflection.Emit?displayProperty=nameWithType> dello spazio dei nomi.|  
|COR_PRF_MODULE_COLLECTIBLE|La durata del modulo viene gestita dal garbage collector.|  
|COR_PRF_MODULE_RESOURCE|Il modulo non contiene metadati e viene utilizzato esclusivamente come risorsa. L'equivalente gestito di questo bit è la <xref:System.Reflection.Module.IsResource%2A?displayProperty=nameWithType> metodo.|  
|COR_PRF_MODULE_FLAT_LAYOUT|Il layout del modulo in memoria non è strutturato, non è stato eseguito il mapping. Se un modulo è questo bit impostato, i profiler che leggono informazioni direttamente dall'intestazione del file (PE) eseguibile portabile saranno necessario prestare attenzione durante l'interpretazione degli indirizzi virtuali relativi (RVA) nell'intestazione.|  
|COR_PRF_MODULE_WINDOWS_RUNTIME|Il flag di tipo di contenuto di Windows Runtime è impostato nei metadati per l'assembly dal modulo. Questo vale per tutti i moduli di metadati di Windows (con estensione winmd).|  
  
## <a name="remarks"></a>Note  
 Bit da COR_PRF_MODULE_FLAGS vengono restituiti al profiler nel `pdwModuleFlags` parametro di output di [ICorProfilerInfo3:: Getmoduleinfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getmoduleinfo2-method.md) metodo. Alcune combinazioni di due o più flag sono possibili, ma non tutte le combinazioni sono possibili.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Enumerazioni di profilatura](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
