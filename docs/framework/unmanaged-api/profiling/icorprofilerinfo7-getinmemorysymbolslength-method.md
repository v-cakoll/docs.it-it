---
title: 'Metodo ICorProfilerInfo7:: GetInMemorySymbolsLength'
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo7.GetInMemorySymbolsLength
api_location:
- mscorwks.dll
- icorprof.idl
api_type:
- COM
ms.assetid: d62c4a4c-8a62-45aa-8f01-a8387cf36159
ms.openlocfilehash: 43d6bdeae5f522bd73b0bdf3a5c403ec69ee384c
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84495438"
---
# <a name="icorprofilerinfo7getinmemorysymbolslength-method"></a>Metodo ICorProfilerInfo7:: GetInMemorySymbolsLength
[Supportata in .NET Framework 4.6.1 e versioni successive]  
  
 Restituisce la lunghezza di un flusso di simboli in memoria.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetInMemorySymbolsLength(  
        [in] ModuleID moduleId,  
        [out] DWORD* pCountSymbolBytes  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `moduleId`  
 in Identificatore del modulo contenente il flusso in memoria.  
  
 pCountSymbolBytes  
 out Puntatore a un `DWORD` valore che, quando il metodo viene restituito, contiene la lunghezza del flusso in byte.  
  
## <a name="return-value"></a>Valore restituito  
 Il metodo restituisce `S_OK` se è possibile determinare la lunghezza del flusso di memoria, anche se è zero (0).  
  
 Il metodo restituisce `CORPROF_E_MODULE_IS_DYNAMIC` se il metodo è stato creato utilizzando <xref:System.Reflection.Emit?displayProperty=nameWithType> .  
  
## <a name="remarks"></a>Osservazioni  
 Se il modulo dispone di simboli in memoria, la lunghezza del flusso viene posizionata in `pCountSymbolBytes` . Se il modulo non dispone di simboli in memoria, `*pCountSymbolBytes = 0` .  
  
> [!NOTE]
> L'implementazione corrente non supporta Reflection. Emit. Se il modulo è stato creato usando Reflection. Emit, il metodo restituisce `CORPROF_E_MODULE_IS_DYNAMIC` .  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerInfo7](icorprofilerinfo7-interface.md)
