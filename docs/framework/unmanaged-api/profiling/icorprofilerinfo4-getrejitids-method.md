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
ms.openlocfilehash: 9069498a4f62f4d9dbb50a7075323b14c3cc5ab9
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868447"
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
 in `FunctionID` dell'istanza della funzione per la quale enumerare le versioni.  
  
 `cReJitIds`  
 in Numero di ID ricompilati in modalità JIT allocati nella matrice `reJitIds`.  
  
 `pcReJitIds`  
 out Numero effettivo di ID ricompilati in JIT.  
  
 `reJitIds`  
 out Matrice allocata dal chiamante che conterrà gli ID ricompilati JIT per la funzione specificata.  
  
## <a name="remarks"></a>Note  
 `GetReJITIDs` enumera gli ID ricompilati JIT attivi per un'istanza di funzione specificata. Segue lo stesso modello di utilizzo di altre funzioni `ICorProfilerInfo` che accettano buffer allocati dal chiamante.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerInfo4](icorprofilerinfo4-interface.md)
- [Interfacce di profilatura](profiling-interfaces.md)
- [Profilatura](index.md)
