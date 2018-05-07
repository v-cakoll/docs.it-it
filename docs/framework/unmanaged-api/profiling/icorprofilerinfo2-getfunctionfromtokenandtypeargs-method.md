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
ms.openlocfilehash: 343cedcf26112f0f2bcc7943ea5ee9f302329a15
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="icorprofilerinfo2getfunctionfromtokenandtypeargs-method"></a>Metodo ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs
Ottiene il `FunctionID` di una funzione con il token di metadati specificato, contenente (classe), e `ClassID` valori di qualsiasi tipo di argomenti.  
  
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
  
#### <a name="parameters"></a>Parametri  
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
 La chiamata di `GetFunctionFromTokenAndTypeArgs` metodo con un `mdMethodRef` metadati anziché un `mdMethodDef` token di metadati possono produrre risultati imprevisti. I chiamanti devono risolvere il `mdMethodRef` per un `mdMethodDef` momento del passaggio.  
  
 Se la funzione non è già stata caricata, la chiamata `GetFunctionFromTokenAndTypeArgs` causerà luogo al caricamento, operazione pericolosa in molti contesti. Ad esempio, questo metodo durante il caricamento di moduli o tipi di provocare un ciclo infinito come il runtime tenta di caricare in modo circolare gli elementi.  
  
 In generale, utilizzare `GetFunctionFromTokenAndTypeArgs` è sconsigliata. Se i profiler sono interessati agli eventi per una determinata funzione, devono archiviare il `ModuleID` e `mdMethodDef` di tale funzione e utilizzare [ICorProfilerInfo2:: Getfunctioninfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) per verificare se un determinato `FunctionID` è quello della funzione desiderata.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [Interfaccia ICorProfilerInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
