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
ms.openlocfilehash: b7fa8e2f06faa399734c44b1a52b41246296ef3f
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57498913"
---
# <a name="icorprofilerinfo7applymetadata-method"></a><span data-ttu-id="2ea6e-102">Metodo ICorProfilerInfo7::ApplyMetaData</span><span class="sxs-lookup"><span data-stu-id="2ea6e-102">ICorProfilerInfo7::ApplyMetaData Method</span></span>
<span data-ttu-id="2ea6e-103">[Supportata in .NET Framework 4.6.1 e versioni successive]</span><span class="sxs-lookup"><span data-stu-id="2ea6e-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="2ea6e-104">Applica i metadati appena definito dal `IMetadataEmit::Define*` metodi a un modulo specificato.</span><span class="sxs-lookup"><span data-stu-id="2ea6e-104">Applies the metadata newly defined by the `IMetadataEmit::Define*` methods to a specified module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ea6e-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2ea6e-105">Syntax</span></span>  
  
```cpp
HRESULT ApplyMetaData(  
        [in] ModuleID moduleID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2ea6e-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="2ea6e-106">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="2ea6e-107">[in] L'identificatore del modulo i cui metadati è stato modificato.</span><span class="sxs-lookup"><span data-stu-id="2ea6e-107">[in] The identifier of the module whose metadata was changed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2ea6e-108">Note</span><span class="sxs-lookup"><span data-stu-id="2ea6e-108">Remarks</span></span>  
 <span data-ttu-id="2ea6e-109">Se vengono apportate modifiche ai metadati dopo il [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback, è necessario chiamare questo metodo prima di usare i nuovi metadati.</span><span class="sxs-lookup"><span data-stu-id="2ea6e-109">If metadata changes are made after the [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback, you must call this method before using the new metadata.</span></span>  
  
 <span data-ttu-id="2ea6e-110">`ApplyMetaData` supporta solo aggiungendo i tipi di metadati seguenti:</span><span class="sxs-lookup"><span data-stu-id="2ea6e-110">`ApplyMetaData` only supports adding the following types of metadata:</span></span>  
  
-   <span data-ttu-id="2ea6e-111">`AssemblyRef` i record, che è possibile creare chiamando il [DefineAssemblyRef](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md).</span><span class="sxs-lookup"><span data-stu-id="2ea6e-111">`AssemblyRef` records, which you create by calling the [IMetaDataAssemblyEmit::DefineAssemblyRef](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md).</span></span> <span data-ttu-id="2ea6e-112">ProcessOnStatus.</span><span class="sxs-lookup"><span data-stu-id="2ea6e-112">method.</span></span>  
  
-   <span data-ttu-id="2ea6e-113">`TypeRef` i record, che è possibile creare chiamando il [DefineTypeRefByName](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetyperefbyname-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="2ea6e-113">`TypeRef` records, which you create by calling the [IMetaDataEmit::DefineTypeRefByName](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetyperefbyname-method.md) method.</span></span>  
  
-   <span data-ttu-id="2ea6e-114">`TypeSpec` i record, che è possibile creare chiamando il [GetTokenFromTypeSpec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromtypespec-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="2ea6e-114">`TypeSpec` records, which you create by calling the [IMetaDataEmit::GetTokenFromTypeSpec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromtypespec-method.md) method.</span></span>  
  
-   <span data-ttu-id="2ea6e-115">`MemberRef` i record, che è possibile creare chiamando il [DefineMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="2ea6e-115">`MemberRef` records, which you create by calling the [IMetaDataEmit::DefineMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md) method.</span></span>  
  
-   <span data-ttu-id="2ea6e-116">`MemberSpec` i record, che è possibile creare chiamando il [IMetaDataEmit2::DefineMethodSpec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definemethodspec-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="2ea6e-116">`MemberSpec` records, which you create by calling the [IMetaDataEmit2::DefineMethodSpec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definemethodspec-method.md) method.</span></span>  
  
-   <span data-ttu-id="2ea6e-117">`UserString` i record, che è possibile creare chiamando il [DefineUserString](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineuserstring-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="2ea6e-117">`UserString` records, which you create by calling the [IMetaDataEmit::DefineUserString](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineuserstring-method.md) method.</span></span>  

<span data-ttu-id="2ea6e-118">A partire da .NET Core 3.0, `ApplyMetaData` supporta anche i tipi seguenti:</span><span class="sxs-lookup"><span data-stu-id="2ea6e-118">Starting with .NET Core 3.0, `ApplyMetaData` also supports the following types:</span></span>

- <span data-ttu-id="2ea6e-119">`TypeDef` i record, che è possibile creare chiamando il [DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="2ea6e-119">`TypeDef` records, which you create by calling the [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md) method.</span></span>

- <span data-ttu-id="2ea6e-120">`MethodDef` i record, che è possibile creare chiamando il [DefineMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethod-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="2ea6e-120">`MethodDef` records, which you create by calling the [IMetaDataEmit::DefineMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethod-method.md) method.</span></span> <span data-ttu-id="2ea6e-121">Tuttavia, l'aggiunta di metodi virtuali a un tipo esistente non è supportata.</span><span class="sxs-lookup"><span data-stu-id="2ea6e-121">However, adding virtual methods to an existing type is not supported.</span></span> <span data-ttu-id="2ea6e-122">Metodi virtuali devono essere aggiunto prima la [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback.</span><span class="sxs-lookup"><span data-stu-id="2ea6e-122">Virtual methods must be added before the [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback.</span></span>

## <a name="requirements"></a><span data-ttu-id="2ea6e-123">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2ea6e-123">Requirements</span></span>  
 <span data-ttu-id="2ea6e-124">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2ea6e-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2ea6e-125">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2ea6e-125">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2ea6e-126">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2ea6e-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2ea6e-127">**Versioni di .NET Framework:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2ea6e-127">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ea6e-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2ea6e-128">See also</span></span>
- [<span data-ttu-id="2ea6e-129">Interfaccia ICorProfilerInfo7</span><span class="sxs-lookup"><span data-stu-id="2ea6e-129">ICorProfilerInfo7 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md)
