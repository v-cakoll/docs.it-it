---
title: Metodo ICorProfilerInfo2::GetClassFromTokenAndTypeArgs
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 5a459f8e9ec6d63dc42d6a0a8f752c129d278524
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfo2getclassfromtokenandtypeargs-method"></a>Metodo ICorProfilerInfo2::GetClassFromTokenAndTypeArgs
Ottiene il `ClassID` di un tipo utilizzando il token di metadati specificati e `ClassID` valori di qualsiasi tipo di argomenti.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetClassFromTokenAndTypeArgs(  
    [in] ModuleID moduleID,  
    [in] mdTypeDef typeDef,  
    [in] ULONG32 cTypeArgs,  
    [in, size_is(cTypeArgs)] ClassID typeArgs[],  
    [out] ClassID* pClassID);  
```  
  
#### <a name="parameters"></a>Parametri  
 `moduleID`  
 [in] L'ID del modulo in cui risiede il tipo.  
  
 `typeDef`  
 [in] Un `mdTypeDef` token di metadati che fa riferimento al tipo.  
  
 `cTypeArgs`  
 [in] Il numero di parametri di tipo per il tipo specificato. Questo valore deve essere zero per i tipi non generici.  
  
 `typeArgs`  
 [in] Matrice di `ClassID` valori, ognuno dei quali è un argomento di tipo. Il valore di `typeArgs` può essere NULL se `cTypeArgs` è impostato su zero.  
  
 `pClassID`  
 [out] Un puntatore al `ClassID` del tipo specificato.  
  
## <a name="remarks"></a>Note  
 La chiamata di `GetClassFromTokenAndTypeArgs` metodo con un `mdTypeRef` anziché un `mdTypeDef` token di metadati possono produrre risultati imprevisti, i chiamanti devono risolvere il `mdTypeRef` per un `mdTypeDef` quando viene passato.  
  
 Se il tipo non è già stato caricato, la chiamata `GetClassFromTokenAndTypeArgs` attiverà il caricamento, operazione pericolosa in molti contesti. Ad esempio, questo metodo durante il caricamento dei moduli o altri tipi di provocare un ciclo infinito come il runtime tenta di caricare in modo circolare gli elementi.  
  
 In generale, utilizzare `GetClassFromTokenAndTypeArgs` è sconsigliata. Se i profiler sono interessati agli eventi per un determinato tipo, archiviano il `ModuleID` e `mdTypeDef` di tale tipo e utilizzare [ICorProfilerInfo2:: Getclassidinfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassidinfo2-method.md) per verificare se un determinato `ClassID` è quello del tipo desiderato.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [Interfaccia ICorProfilerInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
