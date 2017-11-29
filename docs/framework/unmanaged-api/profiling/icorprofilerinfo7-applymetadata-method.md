---
title: 'Metodo icorprofilerinfo7:: Applymetadata'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: cpp
api_name: ICorProfilerInfo7.ApplyMetaData
api_location: mscorwks.dll
api_type: COM
ms.assetid: a1bfb649-4584-4d35-b3e6-8fe59b53992a
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e3724555df58392e5ab59ccb4f52dd2de860b8d4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilerinfo7applymetadata-method"></a><span data-ttu-id="24dde-102">Metodo icorprofilerinfo7:: Applymetadata</span><span class="sxs-lookup"><span data-stu-id="24dde-102">ICorProfilerInfo7::ApplyMetaData Method</span></span>
<span data-ttu-id="24dde-103">[Supportata in .NET Framework 4.6.1 e versioni successive]</span><span class="sxs-lookup"><span data-stu-id="24dde-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="24dde-104">Applica i metadati appena definito per il `IMetadataEmit::Define*` metodi a un modulo specificato.</span><span class="sxs-lookup"><span data-stu-id="24dde-104">Applies the metadata newly defined by the `IMetadataEmit::Define*` methods to a specified module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24dde-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="24dde-105">Syntax</span></span>  
  
```cpp
HRESULT ApplyMetaData(  
        [in] ModuleID moduleID  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="24dde-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="24dde-106">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="24dde-107">[in] L'identificatore del modulo i cui metadati è stato modificato.</span><span class="sxs-lookup"><span data-stu-id="24dde-107">[in] The identifier of the module whose metadata was changed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="24dde-108">Note</span><span class="sxs-lookup"><span data-stu-id="24dde-108">Remarks</span></span>  
 <span data-ttu-id="24dde-109">Se vengono apportate modifiche ai metadati dopo la [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback, è necessario chiamare questo metodo prima di utilizzare i nuovi metadati.</span><span class="sxs-lookup"><span data-stu-id="24dde-109">If metadata changes are made after the [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback, you must call this method before using the new metadata.</span></span>  
  
 <span data-ttu-id="24dde-110">`ApplyMetaData`supporta solo l'aggiunta di tipi di metadati seguenti:</span><span class="sxs-lookup"><span data-stu-id="24dde-110">`ApplyMetaData` only supports adding the following types of metadata:</span></span>  
  
-   <span data-ttu-id="24dde-111">`AssemblyRef`i record, che è possibile creare chiamando il [IMetaDataAssemblyEmit:: DefineAssemblyRef](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md).</span><span class="sxs-lookup"><span data-stu-id="24dde-111">`AssemblyRef` records, which you create by calling the [IMetaDataAssemblyEmit::DefineAssemblyRef](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md).</span></span> <span data-ttu-id="24dde-112">ProcessOnStatus.</span><span class="sxs-lookup"><span data-stu-id="24dde-112">method.</span></span>  
  
-   <span data-ttu-id="24dde-113">`TypeRef`i record, che è possibile creare chiamando il [IMetaDataEmit:: DefineTypeRefByName](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetyperefbyname-method.md) metodo.</span><span class="sxs-lookup"><span data-stu-id="24dde-113">`TypeRef` records, which you create by calling the [IMetaDataEmit::DefineTypeRefByName](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetyperefbyname-method.md) method.</span></span>  
  
-   <span data-ttu-id="24dde-114">`TypeSpec`i record, che è possibile creare chiamando il [IMetaDataEmit:: GetTokenFromTypeSpec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromtypespec-method.md) metodo.</span><span class="sxs-lookup"><span data-stu-id="24dde-114">`TypeSpec` records, which you create by calling the [IMetaDataEmit::GetTokenFromTypeSpec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromtypespec-method.md) method.</span></span>  
  
-   <span data-ttu-id="24dde-115">`MemberRef`i record, che è possibile creare chiamando il [IMetaDataEmit:: DefineMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md) metodo.</span><span class="sxs-lookup"><span data-stu-id="24dde-115">`MemberRef` records, which you create by calling the [IMetaDataEmit::DefineMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md) method.</span></span>  
  
-   <span data-ttu-id="24dde-116">`MemberSpec`i record, che è possibile creare chiamando il [IMetaDataEmit2:: DefineMethodSpec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definemethodspec-method.md) metodo.</span><span class="sxs-lookup"><span data-stu-id="24dde-116">`MemberSpec` records, which you create by calling the [IMetaDataEmit2::DefineMethodSpec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definemethodspec-method.md) method.</span></span>  
  
-   <span data-ttu-id="24dde-117">`UserString`i record, che è possibile creare chiamando il [IMetaDataEmit:: DefineUserString](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineuserstring-method.md) metodo.</span><span class="sxs-lookup"><span data-stu-id="24dde-117">`UserString` records, which you create by calling the [IMetaDataEmit::DefineUserString](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineuserstring-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="24dde-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="24dde-118">Requirements</span></span>  
 <span data-ttu-id="24dde-119">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="24dde-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="24dde-120">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="24dde-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="24dde-121">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="24dde-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="24dde-122">**Versioni di .NET Framework:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="24dde-122">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24dde-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="24dde-123">See Also</span></span>  
 [<span data-ttu-id="24dde-124">Interfaccia ICorProfilerInfo7</span><span class="sxs-lookup"><span data-stu-id="24dde-124">ICorProfilerInfo7 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md)
