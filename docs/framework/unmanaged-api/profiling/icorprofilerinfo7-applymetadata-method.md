---
title: Metodo ICorProfilerInfo7::ApplyMetaData
ms.date: 02/15/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo7.ApplyMetaData
api_location:
- mscorwks.dll
api_type:
- COM
ms.assetid: a1bfb649-4584-4d35-b3e6-8fe59b53992a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: aff6f63bb9f41fe45b22854787667070929bf987
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59213766"
---
# <a name="icorprofilerinfo7applymetadata-method"></a>Metodo ICorProfilerInfo7::ApplyMetaData
[Supportata in .NET Framework 4.6.1 e versioni successive]  
  
 Applica i metadati appena definito dal `IMetadataEmit::Define*` metodi a un modulo specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp
HRESULT ApplyMetaData(  
        [in] ModuleID moduleID  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `moduleID`  
 [in] L'identificatore del modulo i cui metadati è stato modificato.  
  
## <a name="remarks"></a>Note  
 Se vengono apportate modifiche ai metadati dopo il [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback, è necessario chiamare questo metodo prima di usare i nuovi metadati.  
  
 `ApplyMetaData` supporta solo aggiungendo i tipi di metadati seguenti:  
  
-   `AssemblyRef` i record, che è possibile creare chiamando il [DefineAssemblyRef](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md). ProcessOnStatus.  
  
-   `TypeRef` i record, che è possibile creare chiamando il [DefineTypeRefByName](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetyperefbyname-method.md) (metodo).  
  
-   `TypeSpec` i record, che è possibile creare chiamando il [GetTokenFromTypeSpec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromtypespec-method.md) (metodo).  
  
-   `MemberRef` i record, che è possibile creare chiamando il [DefineMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md) (metodo).  
  
-   `MemberSpec` i record, che è possibile creare chiamando il [IMetaDataEmit2::DefineMethodSpec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definemethodspec-method.md) (metodo).  
  
-   `UserString` i record, che è possibile creare chiamando il [DefineUserString](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineuserstring-method.md) (metodo).  

A partire da .NET Core 3.0, `ApplyMetaData` supporta anche i tipi seguenti:

- `TypeDef` i record, che è possibile creare chiamando il [DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md) (metodo).

- `MethodDef` i record, che è possibile creare chiamando il [DefineMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethod-method.md) (metodo). Tuttavia, l'aggiunta di metodi virtuali a un tipo esistente non è supportata. Metodi virtuali devono essere aggiunto prima la [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback.

## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerInfo7](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md)
