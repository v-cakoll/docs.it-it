---
title: Metodo ICorProfilerInfo4::GetReJITIDs
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4.GetReJITIDs
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::GetReJITIDs
helpviewer_keywords:
- GetReJITIDs method, ICorProfilerInfo4 interface [.NET Framework profiling]
- ICorProfilerInfo4::GetReJITIDs method [.NET Framework profiling]
ms.assetid: 634ac28c-a5b7-4fc3-af84-256c24ca8177
topic_type:
- apiref
ms.openlocfilehash: ba15440df79dded95a8afa9438657d064e167f36
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84495970"
---
# <a name="icorprofilerinfo4getrejitids-method"></a>Metodo ICorProfilerInfo4::GetReJITIDs
Restituisce una matrice di ID che identificano tutte le versioni ricompilate in JIT della funzione specificata ancora allocate. Sono incluse le versioni ricompilate tramite JIT di funzioni che sono state successivamente ripristinate ma non ancora liberate, ad esempio quando il dominio dell'applicazione che contiene la funzione ripristinata è ancora in uso.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp
HRESULT GetReJITIDs (  
     [in]  FunctionID          functionId,  
     [in]  ULONG               cReJitIds,  
     [out] ULONG *             pcReJitIds,  
     [out, size_is(cReJitIds), length_is(*pcReJitIds)]   ReJITID        reJitIds[]);  
```  
  
## <a name="parameters"></a>Parametri  
 `functionId`  
 in `FunctionID`Dell'istanza della funzione per la quale enumerare le versioni.  
  
 `cReJitIds`  
 in Numero di ID ricompilati in modalità JIT allocati nella `reJitIds` matrice.  
  
 `pcReJitIds`  
 out Numero effettivo di ID ricompilati in JIT.  
  
 `reJitIds`  
 out Matrice allocata dal chiamante che conterrà gli ID ricompilati JIT per la funzione specificata.  
  
## <a name="remarks"></a>Osservazioni  
 `GetReJITIDs`Enumera gli ID ricompilati JIT attivi per un'istanza di funzione specificata. Segue lo stesso modello di utilizzo di altre `ICorProfilerInfo` funzioni che accettano buffer allocati dal chiamante.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerInfo4](icorprofilerinfo4-interface.md)
- [Interfacce di profilatura](profiling-interfaces.md)
- [Profilatura](index.md)
