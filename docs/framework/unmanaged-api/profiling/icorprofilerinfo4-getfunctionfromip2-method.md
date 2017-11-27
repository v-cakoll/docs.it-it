---
title: Metodo ICorProfilerInfo4::GetFunctionFromIP2
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo4.GetFunctionFromIP2
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo4::GetFunctionFromIP2
helpviewer_keywords:
- ICorProfilerInfo4::GetFunctionFromIP2 method [.NET Framework profiling]
- GetFunctionFromIP2 method, ICorProfilerInfo4 interface [.NET Framework profiling]
ms.assetid: 46ff70f4-13e9-40a0-802a-0a40abcfc6a0
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 2173326c5c67d1f4d3a8e28f84508fd6affb8299
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilerinfo4getfunctionfromip2-method"></a>Metodo ICorProfilerInfo4::GetFunctionFromIP2
Un puntatore all'istruzione di codice gestito viene eseguito il mapping alla versione ricompilata in JIT di una funzione.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetFunctionFromIP2(  
    [in]  LPCBYTE    ip,  
    [out] FunctionID *pFunctionId,  
    [out] ReJITID *pReJitId);  
```  
  
#### <a name="parameters"></a>Parametri  
 `ip`  
 [in] Puntatore all'istruzione nel codice gestito.  
  
 `pFunctionId`  
 [out] L'ID di funzione.  
  
 `pReJitId`  
 [out] L'identità della versione ricompilata in JIT della funzione.  
  
## <a name="remarks"></a>Note  
 `GetFunctionFromIP2`è simile a `GetFunctionFromIP`, ad eccezione del fatto che ottiene l'ID ricompilata in JIT anziché l'ID della funzione della funzione che contiene l'indirizzo IP specificato.  
  
> [!NOTE]
>  `GetFunctionFromIP2`può attivare una garbage collection, mentre `GetFunctionFromIP` No.  Per ulteriori informazioni, vedere [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT](../../../../docs/framework/unmanaged-api/profiling/corprof-e-unsupported-call-sequence-hresult.md).  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
