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
ms.openlocfilehash: 7f1276e1adeece086ca7b6791eb6e870faf4d010
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502873"
---
# <a name="icorprofilerinfo2getfunctionfromtokenandtypeargs-method"></a>Metodo ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs
Ottiene l'oggetto `FunctionID` di una funzione utilizzando il token di metadati specificato, la classe contenente e `ClassID` i valori di qualsiasi argomento di tipo.  
  
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
 in `mdMethodDef`Token di metadati che fa riferimento alla funzione.  
  
 `classId`  
 in ID della classe che contiene la funzione.  
  
 `cTypeArgs`  
 in Numero di parametri di tipo per la funzione specificata. Questo valore deve essere zero per le funzioni non generiche.  
  
 `typeArgs`  
 in Matrice di `ClassID` valori, ognuno dei quali è un argomento della funzione. Il valore di `typeArgs` può essere null se `cTypeArgs` è impostato su zero.  
  
 `pFunctionID`  
 out Puntatore alla `FunctionID` della funzione specificata.  
  
## <a name="remarks"></a>Osservazioni  
 La chiamata al `GetFunctionFromTokenAndTypeArgs` metodo con i `mdMethodRef` metadati anziché un `mdMethodDef` token di metadati può avere risultati imprevedibili. I chiamanti devono risolvere `mdMethodRef` in un oggetto `mdMethodDef` quando lo passano.  
  
 Se la funzione non è già caricata, la chiamata a provocherà il `GetFunctionFromTokenAndTypeArgs` caricamento, che è un'operazione pericolosa in molti contesti. Ad esempio, la chiamata di questo metodo durante il caricamento di moduli o tipi può causare un ciclo infinito perché il runtime tenta di caricare elementi in modo circolare.  
  
 In generale, l'uso di `GetFunctionFromTokenAndTypeArgs` è sconsigliato. Se i profiler sono interessati agli eventi per una funzione specifica, devono archiviare `ModuleID` e `mdMethodDef` della funzione e usare [ICorProfilerInfo2:: GetFunctionInfo2](icorprofilerinfo2-getfunctioninfo2-method.md) per verificare se un dato `FunctionID` è quello della funzione desiderata.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerInfo](icorprofilerinfo-interface.md)
- [Interfaccia ICorProfilerInfo2](icorprofilerinfo2-interface.md)
