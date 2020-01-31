---
title: 'Metodo ICorProfilerInfo7:: ApplyMetaData'
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
ms.openlocfilehash: b9e488a512ad506a8975bfff44ae02cd84c29f74
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76861697"
---
# <a name="icorprofilerinfo7applymetadata-method"></a>Metodo ICorProfilerInfo7:: ApplyMetaData
[Supportata in .NET Framework 4.6.1 e versioni successive]  
  
 Applica i metadati appena definiti dal `IMetadataEmit::Define*` metodi a un modulo specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp
HRESULT ApplyMetaData(  
        [in] ModuleID moduleID  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `moduleID`  
 in Identificatore del modulo i cui metadati sono stati modificati.  
  
## <a name="remarks"></a>Note  
 Se vengono apportate modifiche ai metadati dopo il callback [ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) , è necessario chiamare questo metodo prima di utilizzare i nuovi metadati.  
  
 `ApplyMetaData` supporta solo l'aggiunta dei seguenti tipi di metadati:  
  
- `AssemblyRef` record, che è possibile creare chiamando [IMetaDataAssemblyEmit::D efineassemblyref](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md). ProcessOnStatus.  
  
- `TypeRef` record, creato chiamando il metodo [IMetaDataEmit::D efinetyperefbyname](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetyperefbyname-method.md) .  
  
- `TypeSpec` record, che è possibile creare chiamando il metodo [IMetaDataEmit:: GetTokenFromTypeSpec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromtypespec-method.md) .  
  
- `MemberRef` record, creato chiamando il metodo [IMetaDataEmit::D efinememberref](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md) .  
  
- `MemberSpec` record, che è possibile creare chiamando il metodo [IMetaDataEmit2::D efinemethodspec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definemethodspec-method.md) .  
  
- `UserString` record, creato chiamando il metodo [IMetaDataEmit::D efineuserstring](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineuserstring-method.md) .  

A partire da .NET Core 3,0, `ApplyMetaData` supporta anche i tipi seguenti:

- `TypeDef` record, creato chiamando il metodo [IMetaDataEmit::D efinetypedef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md) .

- `MethodDef` record, creato chiamando il metodo [IMetaDataEmit::D efinemethod](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethod-method.md) . Tuttavia, l'aggiunta di metodi virtuali a un tipo esistente non è supportata. È necessario aggiungere i metodi virtuali prima del callback di [ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) .

## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerInfo7](icorprofilerinfo7-interface.md)
