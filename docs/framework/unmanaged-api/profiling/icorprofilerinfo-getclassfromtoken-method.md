---
title: Metodo ICorProfilerInfo::GetClassFromToken
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetClassFromToken
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetClassFromToken
helpviewer_keywords:
- ICorProfilerInfo::GetClassFromToken method [.NET Framework profiling]
- GetClassFromToken method, ICorProfilerInfo interface [.NET Framework profiling]
ms.assetid: 0afc1197-2a5b-424f-8b82-9cb59a7e00db
topic_type:
- apiref
ms.openlocfilehash: 12b4b897f9dc51175037d39c0368b6ce59fefefb
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84498479"
---
# <a name="icorprofilerinfogetclassfromtoken-method"></a>Metodo ICorProfilerInfo::GetClassFromToken
Ottiene l'ID della classe, dato il token di metadati. Questo metodo è obsoleto nella versione .NET Framework 2,0. Usare invece [ICorProfilerInfo2:: GetClassFromTokenAndTypeArgs](icorprofilerinfo2-getclassfromtokenandtypeargs-method.md) .  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetClassFromToken(  
    [in]  ModuleID  moduleId,  
    [in]  mdTypeDef typeDef,  
    [out] ClassID   *pClassId);  
```  
  
## <a name="parameters"></a>Parametri  
 `moduleID`  
 in ID del modulo che contiene la classe.  
  
 `typeDef`  
 in `mdTypeDef`Token di metadati che fa riferimento alla classe.  
  
 `cTypeArgs`  
 out Puntatore all'ID della classe.  
  
## <a name="remarks"></a>Osservazioni  
 Questo metodo è obsoleto; usare invece `ICorProfilerInfo2::GetClassFromTokenAndTypeArgs` per tutti i tipi.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** 1,0, 1,1  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerInfo](icorprofilerinfo-interface.md)
