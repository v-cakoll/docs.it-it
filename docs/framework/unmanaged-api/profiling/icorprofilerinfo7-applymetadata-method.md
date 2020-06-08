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
ms.openlocfilehash: c30206145d08a22af49c4a6a0dc83fd7382bcc06
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84495508"
---
# <a name="icorprofilerinfo7applymetadata-method"></a>Metodo ICorProfilerInfo7:: ApplyMetaData
[Supportata in .NET Framework 4.6.1 e versioni successive]  
  
 Applica i metadati appena definiti dai `IMetadataEmit::Define*` metodi a un modulo specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp
HRESULT ApplyMetaData(  
        [in] ModuleID moduleID  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `moduleID`  
 in Identificatore del modulo i cui metadati sono stati modificati.  
  
## <a name="remarks"></a>Osservazioni  
 Se vengono apportate modifiche ai metadati dopo il callback [ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) , è necessario chiamare questo metodo prima di utilizzare i nuovi metadati.  
  
 `ApplyMetaData`supporta solo l'aggiunta dei seguenti tipi di metadati:  
  
- `AssemblyRef`record creati chiamando [IMetaDataAssemblyEmit::D efineassemblyref](../metadata/imetadataassemblyemit-defineassemblyref-method.md). ProcessOnStatus.  
  
- `TypeRef`record, che vengono creati chiamando il metodo [IMetaDataEmit::D efinetyperefbyname](../metadata/imetadataemit-definetyperefbyname-method.md) .  
  
- `TypeSpec`record, che vengono creati chiamando il metodo [IMetaDataEmit:: GetTokenFromTypeSpec](../metadata/imetadataemit-gettokenfromtypespec-method.md) .  
  
- `MemberRef`record, che vengono creati chiamando il metodo [IMetaDataEmit::D efinememberref](../metadata/imetadataemit-definememberref-method.md) .  
  
- `MemberSpec`record, che vengono creati chiamando il metodo [IMetaDataEmit2::D efinemethodspec](../metadata/imetadataemit2-definemethodspec-method.md) .  
  
- `UserString`record, che vengono creati chiamando il metodo [IMetaDataEmit::D efineuserstring](../metadata/imetadataemit-defineuserstring-method.md) .  

A partire da .NET Core 3,0, `ApplyMetaData` supporta anche i tipi seguenti:

- `TypeDef`record, che vengono creati chiamando il metodo [IMetaDataEmit::D efinetypedef](../metadata/imetadataemit-definetypedef-method.md) .

- `MethodDef`record, che vengono creati chiamando il metodo [IMetaDataEmit::D efinemethod](../metadata/imetadataemit-definemethod-method.md) . Tuttavia, l'aggiunta di metodi virtuali a un tipo esistente non è supportata. È necessario aggiungere i metodi virtuali prima del callback di [ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) .

## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerInfo7](icorprofilerinfo7-interface.md)
