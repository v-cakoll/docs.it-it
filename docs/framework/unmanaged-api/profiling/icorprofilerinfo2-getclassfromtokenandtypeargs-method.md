---
title: Metodo ICorProfilerInfo2::GetClassFromTokenAndTypeArgs
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetClassFromTokenAndTypeArgs
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetClassFromTokenAndTypeArgs
helpviewer_keywords:
- GetClassFromTokenAndTypeArgs method [.NET Framework profiling]
- ICorProfilerInfo2::GetClassFromTokenAndTypeArgs method [.NET Framework profiling]
ms.assetid: b25c88f0-71b9-443b-8eea-1c94db0a44b9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0d4d5ec9119cdcf89e507f133288f569e6fb37ea
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62000688"
---
# <a name="icorprofilerinfo2getclassfromtokenandtypeargs-method"></a>Metodo ICorProfilerInfo2::GetClassFromTokenAndTypeArgs
Ottiene il `ClassID` di un tipo usando il token di metadati specificati e il `ClassID` valori di qualsiasi tipo di argomenti.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetClassFromTokenAndTypeArgs(  
    [in] ModuleID moduleID,  
    [in] mdTypeDef typeDef,  
    [in] ULONG32 cTypeArgs,  
    [in, size_is(cTypeArgs)] ClassID typeArgs[],  
    [out] ClassID* pClassID);  
```  
  
## <a name="parameters"></a>Parametri  
 `moduleID`  
 [in] L'ID del modulo in cui si trova il tipo.  
  
 `typeDef`  
 [in] Un `mdTypeDef` token di metadati che fa riferimento al tipo.  
  
 `cTypeArgs`  
 [in] Il numero di parametri di tipo per il tipo specificato. Questo valore deve essere zero per i tipi non generici.  
  
 `typeArgs`  
 [in] Matrice di `ClassID` valori, ognuno dei quali è un argomento del tipo. Il valore di `typeArgs` può essere NULL se `cTypeArgs` è impostato su zero.  
  
 `pClassID`  
 [out] Un puntatore al `ClassID` del tipo specificato.  
  
## <a name="remarks"></a>Note  
 Chiama il `GetClassFromTokenAndTypeArgs` metodo con un `mdTypeRef` invece di un `mdTypeDef` token di metadati possono produrre risultati imprevisti; i chiamanti devono risolvere il `mdTypeRef` a un `mdTypeDef` quando viene passato.  
  
 Se il tipo non è già stato caricato, la chiamata `GetClassFromTokenAndTypeArgs` attiverà il caricamento, che è un'operazione pericolosa in molti contesti. Ad esempio, si chiama questo metodo durante il caricamento dei moduli o altri tipi di provocare un ciclo infinito come il runtime tenta di caricare in modo circolare le cose.  
  
 In generale, usare di `GetClassFromTokenAndTypeArgs` è sconsigliata. Se profiler sono interessati agli eventi per un determinato tipo, è consigliabile archiviare il `ModuleID` e `mdTypeDef` di quel tipo e usare [ICorProfilerInfo2::GetClassIDInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassidinfo2-method.md) per verificare se un determinato `ClassID` è quello del tipo desiderato.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [Interfaccia ICorProfilerInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
