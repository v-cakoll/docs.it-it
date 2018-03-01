---
title: 'Metodo icorprofilerinfo7:: Applymetadata'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- cpp
api_name:
- ICorProfilerInfo7.ApplyMetaData
api_location:
- mscorwks.dll
api_type:
- COM
ms.assetid: a1bfb649-4584-4d35-b3e6-8fe59b53992a
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2e79d687d3d777895dea9427e4865c2fc866f50d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfo7applymetadata-method"></a>Metodo icorprofilerinfo7:: Applymetadata
[Supportata in .NET Framework 4.6.1 e versioni successive]  
  
 Applica i metadati appena definito per il `IMetadataEmit::Define*` metodi a un modulo specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp
HRESULT ApplyMetaData(  
        [in] ModuleID moduleID  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `moduleID`  
 [in] L'identificatore del modulo i cui metadati è stato modificato.  
  
## <a name="remarks"></a>Note  
 Se vengono apportate modifiche ai metadati dopo la [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback, è necessario chiamare questo metodo prima di utilizzare i nuovi metadati.  
  
 `ApplyMetaData`supporta solo l'aggiunta di tipi di metadati seguenti:  
  
-   `AssemblyRef`i record, che è possibile creare chiamando il [IMetaDataAssemblyEmit:: DefineAssemblyRef](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md). ProcessOnStatus.  
  
-   `TypeRef`i record, che è possibile creare chiamando il [IMetaDataEmit:: DefineTypeRefByName](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetyperefbyname-method.md) metodo.  
  
-   `TypeSpec`i record, che è possibile creare chiamando il [IMetaDataEmit:: GetTokenFromTypeSpec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromtypespec-method.md) metodo.  
  
-   `MemberRef`i record, che è possibile creare chiamando il [IMetaDataEmit:: DefineMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md) metodo.  
  
-   `MemberSpec`i record, che è possibile creare chiamando il [IMetaDataEmit2:: DefineMethodSpec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definemethodspec-method.md) metodo.  
  
-   `UserString`i record, che è possibile creare chiamando il [IMetaDataEmit:: DefineUserString](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineuserstring-method.md) metodo.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorProfilerInfo7](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md)
