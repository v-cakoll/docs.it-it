---
title: Metodo ICorProfilerInfo4::GetReJITIDs
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo4.GetReJITIDs
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo4::GetReJITIDs
helpviewer_keywords:
- GetReJITIDs method, ICorProfilerInfo4 interface [.NET Framework profiling]
- ICorProfilerInfo4::GetReJITIDs method [.NET Framework profiling]
ms.assetid: 634ac28c-a5b7-4fc3-af84-256c24ca8177
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: cc16cd932fc2ce0cf5cb53c227081501e79ed2d5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerinfo4getrejitids-method"></a>Metodo ICorProfilerInfo4::GetReJITIDs
Restituisce una matrice di ID che identifica tutte ricompilata in JIT le versioni della funzione specificata che sono ancora allocate. Sono incluse versioni ricompilata in JIT di funzioni che sono state ripristinate in seguito, ma non ancora liberate (ad esempio, quando il dominio applicazione che contiene la funzione ripristinata è ancora in uso).  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetReJITIDs (  
     [in]  FunctionID          functionId,  
     [in]  ULONG               cReJitIds,  
     [out] ULONG *             pcReJitIds,  
     [out, size_is(cReJitIds), length_is(*pcReJitIds)]   ReJITID        reJitIds[]);  
```  
  
#### <a name="parameters"></a>Parametri  
 `functionId`  
 [in] Il `FunctionID` dell'istanza di funzione per cui si desidera ottenere le versioni.  
  
 `cReJitIds`  
 [in] Il numero di ID ricompilata in JIT allocata nel `reJitIds` matrice.  
  
 `pcReJitIds`  
 [out] Il numero effettivo di ID ricompilata in JIT.  
  
 `reJitIds`  
 [out] Una matrice allocata dal chiamante che conterrà gli ID ricompilata in JIT per la funzione specificata.  
  
## <a name="remarks"></a>Note  
 `GetReJITIDs`Enumera gli ID active ricompilata in JIT per un'istanza della funzione specificata. Segue lo stesso modello di utilizzo delle altre `ICorProfilerInfo` funzioni che accettano i buffer allocati dal chiamante.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [ICorProfilerInfo4 (interfaccia)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)  
 [Interfacce di profilatura](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [Profilatura](../../../../docs/framework/unmanaged-api/profiling/index.md)
