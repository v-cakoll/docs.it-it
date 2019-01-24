---
title: Metodo ICorProfilerInfo7::GetInMemorySymbolsLength
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo7.GetInMemorySymbolsLength
api_location:
- mscorwks.dll
- icorprof.idl
api_type:
- COM
ms.assetid: d62c4a4c-8a62-45aa-8f01-a8387cf36159
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 64289ee7fbdc440a87df6c8e506317f23e780912
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54722855"
---
# <a name="icorprofilerinfo7getinmemorysymbolslength-method"></a>Metodo ICorProfilerInfo7::GetInMemorySymbolsLength
[Supportata in .NET Framework 4.6.1 e versioni successive]  
  
 Restituisce la lunghezza di un flusso di simboli in memoria.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetInMemorySymbolsLength(  
        [in] ModuleID moduleId,  
        [out] DWORD* pCountSymbolBytes  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `moduleId`  
 [in] L'identificatore del modulo contenente il flusso in memoria.  
  
 pCountSymbolBytes  
 [out] Un puntatore a un `DWORD` valore che, quando il metodo viene restituito, contiene la lunghezza in byte del flusso.  
  
## <a name="return-value"></a>Valore restituito  
 Il metodo restituisce `S_OK` se la lunghezza del flusso di memoria può essere determinata, anche se è zero (0).  
  
 Il metodo restituisce `CORPROF_E_MODULE_IS_DYNAMIC` se il metodo è stato creato utilizzando <xref:System.Reflection.Emit?displayProperty=nameWithType>.  
  
## <a name="remarks"></a>Note  
 Se il modulo include i simboli in memoria, la lunghezza del flusso viene attivata `pCountSymbolBytes`. Se il modulo non dispone di simboli in memoria, `*pCountSymbolBytes = 0`.  
  
> [!NOTE]
>  L'implementazione corrente non supporta Reflection. Emit. Se il modulo è stato creato tramite Reflection. Emit, il metodo restituisce `CORPROF_E_MODULE_IS_DYNAMIC`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Interfaccia ICorProfilerInfo7](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md)
