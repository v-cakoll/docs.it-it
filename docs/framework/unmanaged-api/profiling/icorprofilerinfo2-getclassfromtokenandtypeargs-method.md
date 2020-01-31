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
ms.openlocfilehash: e0663ff122397ba639a0a219e513be2f3f0cbbef
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76862763"
---
# <a name="icorprofilerinfo2getclassfromtokenandtypeargs-method"></a>Metodo ICorProfilerInfo2::GetClassFromTokenAndTypeArgs
Ottiene l'`ClassID` di un tipo utilizzando il token di metadati specificato e i valori di `ClassID` di qualsiasi argomento di tipo.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetClassFromTokenAndTypeArgs(  
    [in] ModuleID moduleID,  
    [in] mdTypeDef typeDef,  
    [in] ULONG32 cTypeArgs,  
    [in, size_is(cTypeArgs)] ClassID typeArgs[],  
    [out] ClassID* pClassID);  
```  
  
## <a name="parameters"></a>Parametri  
 `moduleID`  
 in ID del modulo in cui risiede il tipo.  
  
 `typeDef`  
 in Token di metadati `mdTypeDef` che fa riferimento al tipo.  
  
 `cTypeArgs`  
 in Numero di parametri di tipo per il tipo specificato. Questo valore deve essere zero per i tipi non generici.  
  
 `typeArgs`  
 in Matrice di valori di `ClassID`, ognuno dei quali è un argomento del tipo. Se `cTypeArgs` è impostato su zero, il valore di `typeArgs` può essere NULL.  
  
 `pClassID`  
 out Puntatore al `ClassID` del tipo specificato.  
  
## <a name="remarks"></a>Note  
 La chiamata al metodo `GetClassFromTokenAndTypeArgs` con un `mdTypeRef` anziché un token di metadati `mdTypeDef` può avere risultati imprevedibili. i chiamanti devono risolvere il `mdTypeRef` in un `mdTypeDef` quando viene passato.  
  
 Se il tipo non è già caricato, la chiamata `GetClassFromTokenAndTypeArgs` attiverà il caricamento, che è un'operazione pericolosa in molti contesti. Ad esempio, la chiamata di questo metodo durante il caricamento di moduli o altri tipi può causare un ciclo infinito, perché il runtime tenta di caricare elementi in modo circolare.  
  
 In generale, l'uso di `GetClassFromTokenAndTypeArgs` è sconsigliato. Se i profiler sono interessati a eventi per un determinato tipo, devono archiviare il `ModuleID` e `mdTypeDef` di quel tipo e usare [ICorProfilerInfo2:: GetClassIDInfo2](icorprofilerinfo2-getclassidinfo2-method.md) per verificare se un determinato `ClassID` è quello del tipo desiderato.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerInfo](icorprofilerinfo-interface.md)
- [Interfaccia ICorProfilerInfo2](icorprofilerinfo2-interface.md)
