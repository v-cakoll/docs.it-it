---
title: Metodo ICorProfilerInfo4::GetFunctionFromIP2
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4.GetFunctionFromIP2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::GetFunctionFromIP2
helpviewer_keywords:
- ICorProfilerInfo4::GetFunctionFromIP2 method [.NET Framework profiling]
- GetFunctionFromIP2 method, ICorProfilerInfo4 interface [.NET Framework profiling]
ms.assetid: 46ff70f4-13e9-40a0-802a-0a40abcfc6a0
topic_type:
- apiref
ms.openlocfilehash: 8ad04a7a6705b961686317c9473b885fb90676ce
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76861918"
---
# <a name="icorprofilerinfo4getfunctionfromip2-method"></a>Metodo ICorProfilerInfo4::GetFunctionFromIP2
Esegue il mapping di un puntatore all'istruzione di codice gestito alla versione di una funzione ricompilata in JIT.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetFunctionFromIP2(  
    [in]  LPCBYTE    ip,  
    [out] FunctionID *pFunctionId,  
    [out] ReJITID *pReJitId);  
```  
  
## <a name="parameters"></a>Parametri  
 `ip`  
 in Puntatore all'istruzione nel codice gestito.  
  
 `pFunctionId`  
 out ID funzione.  
  
 `pReJitId`  
 out Identità della versione ricompilata in JIT della funzione.  
  
## <a name="remarks"></a>Note  
 `GetFunctionFromIP2` è simile a `GetFunctionFromIP`, ad eccezione del fatto che ottiene l'ID ricompilata JIT anziché l'ID funzione della funzione che contiene l'indirizzo IP specificato.  
  
> [!NOTE]
> `GetFunctionFromIP2` possibile attivare un Garbage Collection, mentre `GetFunctionFromIP` non lo è.  Per ulteriori informazioni, vedere [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT](corprof-e-unsupported-call-sequence-hresult.md).  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerInfo](icorprofilerinfo-interface.md)
