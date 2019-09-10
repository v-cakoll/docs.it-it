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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 805ceb60d2ac122df2382656b95b7bf5e7509bfc
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855947"
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
 in Dell' `FunctionID` istanza della funzione per la quale enumerare le versioni.  
  
 `cReJitIds`  
 in Numero di ID ricompilati in modalità JIT allocati nella `reJitIds` matrice.  
  
 `pcReJitIds`  
 out Numero effettivo di ID ricompilati in JIT.  
  
 `reJitIds`  
 out Matrice allocata dal chiamante che conterrà gli ID ricompilati JIT per la funzione specificata.  
  
## <a name="remarks"></a>Note  
 `GetReJITIDs`Enumera gli ID ricompilati JIT attivi per un'istanza di funzione specificata. Segue lo stesso modello di utilizzo di altre `ICorProfilerInfo` funzioni che accettano buffer allocati dal chiamante.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf. idl, CorProf. h  
  
 **Libreria** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerInfo4](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)
- [Interfacce di profilatura](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [Profilatura](../../../../docs/framework/unmanaged-api/profiling/index.md)
