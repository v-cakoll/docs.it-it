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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7e1498ec3ce1e5258546cec8d8f8172739af6d9d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59179764"
---
# <a name="icorprofilerinfo2getfunctionfromtokenandtypeargs-method"></a>Metodo ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs
Ottiene il `FunctionID` di una funzione usando il token di metadati specificato, contenente (classe), e `ClassID` valori di qualsiasi tipo di argomenti.  
  
## <a name="syntax"></a>Sintassi  
  
```  
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
 [in] L'ID del modulo in cui risiede la funzione.  
  
 `funcDef`  
 [in] Un `mdMethodDef` token di metadati che fa riferimento alla funzione.  
  
 `classId`  
 [in] ID della classe contenitore della funzione.  
  
 `cTypeArgs`  
 [in] Il numero di parametri di tipo per la funzione specificata. Questo valore deve essere zero per le funzioni non generica.  
  
 `typeArgs`  
 [in] Matrice di `ClassID` valori, ognuno dei quali è un argomento della funzione. Il valore di `typeArgs` può essere NULL se `cTypeArgs` è impostato su zero.  
  
 `pFunctionID`  
 [out] Un puntatore al `FunctionID` della funzione specificata.  
  
## <a name="remarks"></a>Note  
 Chiama il `GetFunctionFromTokenAndTypeArgs` metodo con un `mdMethodRef` metadati anziché un `mdMethodDef` token di metadati possono produrre risultati imprevisti. I chiamanti devono risolvere le `mdMethodRef` a un `mdMethodDef` quando viene passato.  
  
 Se la funzione non è già stata caricata, la chiamata `GetFunctionFromTokenAndTypeArgs` causerà il caricamento si verifichi, ovvero un'operazione pericolosa in molti contesti. Ad esempio, chiama questo metodo durante il caricamento di moduli o tipi di provocare un ciclo infinito come il runtime tenta di caricare in modo circolare le cose.  
  
 In generale, usare di `GetFunctionFromTokenAndTypeArgs` è sconsigliata. Se profiler sono interessati agli eventi per una particolare funzione, devono archiviare il `ModuleID` e `mdMethodDef` di tale funzione e utilizzo [ICorProfilerInfo2::GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) per verificare se un determinato `FunctionID` è quello della funzione desiderata.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [Interfaccia ICorProfilerInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
