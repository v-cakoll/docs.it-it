---
title: Metodo ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetFunctionFromTokenAndTypeArgs
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs
helpviewer_keywords:
- ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs method [.NET Framework profiling]
- GetFunctionFromTokenAndTypeArgs method [.NET Framework profiling]
ms.assetid: ce8f6aa6-4ebf-4a86-b429-4bbc8af41a8f
topic_type:
- apiref
ms.openlocfilehash: 41021a524142afe34727584265aee578e31a64b3
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74433218"
---
# <a name="icorprofilerinfo2getfunctionfromtokenandtypeargs-method"></a>Metodo ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs
Ottiene l'`FunctionID` di una funzione utilizzando il token di metadati specificato, la classe contenente e i valori di `ClassID` di qualsiasi argomento di tipo.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetFunctionFromTokenAndTypeArgs(  
    [in] ModuleID moduleID,  
    [in] mdMethodDef funcDef,  
    [in] ClassID classId,  
    [in] ULONG32 cTypeArgs,  
    [in, size_is(cTypeArgs)] ClassID typeArgs[],  
    [out] FunctionID* pFunctionID);  
```  
  
## <a name="parameters"></a>Parametri  
 `moduleID`  
 in ID del modulo in cui risiede la funzione.  
  
 `funcDef`  
 in Token di metadati `mdMethodDef` che fa riferimento alla funzione.  
  
 `classId`  
 in ID della classe che contiene la funzione.  
  
 `cTypeArgs`  
 in Numero di parametri di tipo per la funzione specificata. Questo valore deve essere zero per le funzioni non generiche.  
  
 `typeArgs`  
 in Matrice di valori di `ClassID`, ognuno dei quali è un argomento della funzione. Se `cTypeArgs` è impostato su zero, il valore di `typeArgs` può essere NULL.  
  
 `pFunctionID`  
 out Puntatore al `FunctionID` della funzione specificata.  
  
## <a name="remarks"></a>Osservazioni  
 La chiamata al metodo `GetFunctionFromTokenAndTypeArgs` con un `mdMethodRef` metadati anziché un token di metadati `mdMethodDef` può avere risultati imprevedibili. I chiamanti devono risolvere il `mdMethodRef` in un `mdMethodDef` quando viene passato.  
  
 Se la funzione non è già caricata, la chiamata `GetFunctionFromTokenAndTypeArgs` provocherà il caricamento, che è un'operazione pericolosa in molti contesti. Ad esempio, la chiamata di questo metodo durante il caricamento di moduli o tipi può causare un ciclo infinito perché il runtime tenta di caricare elementi in modo circolare.  
  
 In generale, l'uso di `GetFunctionFromTokenAndTypeArgs` è sconsigliato. Se i profiler sono interessati agli eventi per una funzione specifica, devono archiviare il `ModuleID` e `mdMethodDef` di tale funzione e usare [ICorProfilerInfo2:: GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) per verificare se un determinato `FunctionID` è quello della funzione desiderata.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [Interfaccia ICorProfilerInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
