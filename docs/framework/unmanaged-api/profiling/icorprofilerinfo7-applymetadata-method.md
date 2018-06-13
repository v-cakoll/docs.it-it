---
title: 'Metodo icorprofilerinfo7:: Applymetadata'
ms.date: 03/30/2017
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
ms.openlocfilehash: 5b8b6ba429a45c92dc6b6b5dcaa7c8a35b47385f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33458296"
---
# <a name="icorprofilerinfo7applymetadata-method"></a><span data-ttu-id="4c9ea-102">Metodo icorprofilerinfo7:: Applymetadata</span><span class="sxs-lookup"><span data-stu-id="4c9ea-102">ICorProfilerInfo7::ApplyMetaData Method</span></span>
<span data-ttu-id="4c9ea-103">[Supportata in .NET Framework 4.6.1 e versioni successive]</span><span class="sxs-lookup"><span data-stu-id="4c9ea-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="4c9ea-104">Applica i metadati appena definito per il `IMetadataEmit::Define*` metodi a un modulo specificato.</span><span class="sxs-lookup"><span data-stu-id="4c9ea-104">Applies the metadata newly defined by the `IMetadataEmit::Define*` methods to a specified module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4c9ea-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4c9ea-105">Syntax</span></span>  
  
```cpp
HRESULT ApplyMetaData(  
        [in] ModuleID moduleID  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4c9ea-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="4c9ea-106">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="4c9ea-107">[in] L'identificatore del modulo i cui metadati è stato modificato.</span><span class="sxs-lookup"><span data-stu-id="4c9ea-107">[in] The identifier of the module whose metadata was changed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4c9ea-108">Note</span><span class="sxs-lookup"><span data-stu-id="4c9ea-108">Remarks</span></span>  
 <span data-ttu-id="4c9ea-109">Se vengono apportate modifiche ai metadati dopo la [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback, è necessario chiamare questo metodo prima di utilizzare i nuovi metadati.</span><span class="sxs-lookup"><span data-stu-id="4c9ea-109">If metadata changes are made after the [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback, you must call this method before using the new metadata.</span></span>  
  
 <span data-ttu-id="4c9ea-110">`ApplyMetaData` supporta solo aggiungendo i tipi di metadati seguenti:</span><span class="sxs-lookup"><span data-stu-id="4c9ea-110">`ApplyMetaData` only supports adding the following types of metadata:</span></span>  
  
-   <span data-ttu-id="4c9ea-111">`AssemblyRef` i record, che è possibile creare chiamando il [DefineAssemblyRef](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md).</span><span class="sxs-lookup"><span data-stu-id="4c9ea-111">`AssemblyRef` records, which you create by calling the [IMetaDataAssemblyEmit::DefineAssemblyRef](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md).</span></span> <span data-ttu-id="4c9ea-112">ProcessOnStatus.</span><span class="sxs-lookup"><span data-stu-id="4c9ea-112">method.</span></span>  
  
-   <span data-ttu-id="4c9ea-113">`TypeRef` i record, che è possibile creare chiamando il [DefineTypeRefByName](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetyperefbyname-method.md) metodo.</span><span class="sxs-lookup"><span data-stu-id="4c9ea-113">`TypeRef` records, which you create by calling the [IMetaDataEmit::DefineTypeRefByName](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetyperefbyname-method.md) method.</span></span>  
  
-   <span data-ttu-id="4c9ea-114">`TypeSpec` i record, che è possibile creare chiamando il [GetTokenFromTypeSpec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromtypespec-method.md) metodo.</span><span class="sxs-lookup"><span data-stu-id="4c9ea-114">`TypeSpec` records, which you create by calling the [IMetaDataEmit::GetTokenFromTypeSpec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromtypespec-method.md) method.</span></span>  
  
-   <span data-ttu-id="4c9ea-115">`MemberRef` i record, che è possibile creare chiamando il [DefineMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md) metodo.</span><span class="sxs-lookup"><span data-stu-id="4c9ea-115">`MemberRef` records, which you create by calling the [IMetaDataEmit::DefineMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md) method.</span></span>  
  
-   <span data-ttu-id="4c9ea-116">`MemberSpec` i record, che è possibile creare chiamando il [IMetaDataEmit2::DefineMethodSpec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definemethodspec-method.md) metodo.</span><span class="sxs-lookup"><span data-stu-id="4c9ea-116">`MemberSpec` records, which you create by calling the [IMetaDataEmit2::DefineMethodSpec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definemethodspec-method.md) method.</span></span>  
  
-   <span data-ttu-id="4c9ea-117">`UserString` i record, che è possibile creare chiamando il [DefineUserString](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineuserstring-method.md) metodo.</span><span class="sxs-lookup"><span data-stu-id="4c9ea-117">`UserString` records, which you create by calling the [IMetaDataEmit::DefineUserString](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineuserstring-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4c9ea-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4c9ea-118">Requirements</span></span>  
 <span data-ttu-id="4c9ea-119">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4c9ea-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4c9ea-120">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4c9ea-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4c9ea-121">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="4c9ea-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4c9ea-122">**Versioni di .NET Framework:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4c9ea-122">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c9ea-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4c9ea-123">See Also</span></span>  
 [<span data-ttu-id="4c9ea-124">Interfaccia ICorProfilerInfo7</span><span class="sxs-lookup"><span data-stu-id="4c9ea-124">ICorProfilerInfo7 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md)
