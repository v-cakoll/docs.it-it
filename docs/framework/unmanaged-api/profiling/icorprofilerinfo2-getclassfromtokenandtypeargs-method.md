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
ms.openlocfilehash: 702c5f9f2bc08c824bdc0607741a6afd65a3e89b
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84497257"
---
# <a name="icorprofilerinfo2getclassfromtokenandtypeargs-method"></a>Metodo ICorProfilerInfo2::GetClassFromTokenAndTypeArgs
Ottiene l'oggetto `ClassID` di un tipo utilizzando il token di metadati specificato e i `ClassID` valori di qualsiasi argomento di tipo.  
  
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
 in `mdTypeDef`Token di metadati che fa riferimento al tipo.  
  
 `cTypeArgs`  
 in Numero di parametri di tipo per il tipo specificato. Questo valore deve essere zero per i tipi non generici.  
  
 `typeArgs`  
 in Matrice di `ClassID` valori, ognuno dei quali è un argomento del tipo. Il valore di `typeArgs` può essere null se `cTypeArgs` è impostato su zero.  
  
 `pClassID`  
 out Puntatore all'oggetto `ClassID` del tipo specificato.  
  
## <a name="remarks"></a>Osservazioni  
 La chiamata al `GetClassFromTokenAndTypeArgs` metodo con un `mdTypeRef` anziché un `mdTypeDef` token di metadati può avere risultati imprevedibili; i chiamanti devono risolvere l'oggetto `mdTypeRef` in un oggetto `mdTypeDef` quando lo passano.  
  
 Se il tipo non è già caricato, la chiamata di attiverà il `GetClassFromTokenAndTypeArgs` caricamento, che è un'operazione pericolosa in molti contesti. Ad esempio, la chiamata di questo metodo durante il caricamento di moduli o altri tipi può causare un ciclo infinito, perché il runtime tenta di caricare elementi in modo circolare.  
  
 In generale, l'uso di `GetClassFromTokenAndTypeArgs` è sconsigliato. Se i profiler sono interessati a eventi per un determinato tipo, devono archiviare `ModuleID` e `mdTypeDef` di quel tipo e usare [ICorProfilerInfo2:: GetClassIDInfo2](icorprofilerinfo2-getclassidinfo2-method.md) per verificare se un dato `ClassID` è quello del tipo desiderato.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerInfo](icorprofilerinfo-interface.md)
- [Interfaccia ICorProfilerInfo2](icorprofilerinfo2-interface.md)
