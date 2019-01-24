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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 12524de994264d83abf5b5338654e89a0964adff
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54667700"
---
# <a name="icorprofilerinfogetclassfromtoken-method"></a>Metodo ICorProfilerInfo::GetClassFromToken
Ottiene l'ID della classe, dato il token di metadati. Questo metodo è obsoleto in .NET Framework versione 2.0. Uso [ICorProfilerInfo2::GetClassFromTokenAndTypeArgs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassfromtokenandtypeargs-method.md) invece.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetClassFromToken(  
    [in]  ModuleID  moduleId,  
    [in]  mdTypeDef typeDef,  
    [out] ClassID   *pClassId);  
```  
  
#### <a name="parameters"></a>Parametri  
 `moduleID`  
 [in] L'ID del modulo che contiene la classe.  
  
 `typeDef`  
 [in] Un `mdTypeDef` token di metadati che fa riferimento alla classe.  
  
 `cTypeArgs`  
 [out] Un puntatore all'ID di classe.  
  
## <a name="remarks"></a>Note  
 Questo metodo è obsoleto. Usare invece `ICorProfilerInfo2::GetClassFromTokenAndTypeArgs` per tutti i tipi.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:** 1.0, 1.1  
  
## <a name="see-also"></a>Vedere anche
- [Interfaccia ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
