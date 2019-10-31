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
ms.openlocfilehash: 00d9bef1e2b59a2d2207d1e343380e0e81bee848
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130355"
---
# <a name="icorprofilerinfo7applymetadata-method"></a><span data-ttu-id="35de7-102">Metodo ICorProfilerInfo7:: ApplyMetaData</span><span class="sxs-lookup"><span data-stu-id="35de7-102">ICorProfilerInfo7::ApplyMetaData Method</span></span>
<span data-ttu-id="35de7-103">[Supportata in .NET Framework 4.6.1 e versioni successive]</span><span class="sxs-lookup"><span data-stu-id="35de7-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="35de7-104">Applica i metadati appena definiti dal `IMetadataEmit::Define*` metodi a un modulo specificato.</span><span class="sxs-lookup"><span data-stu-id="35de7-104">Applies the metadata newly defined by the `IMetadataEmit::Define*` methods to a specified module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35de7-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="35de7-105">Syntax</span></span>  
  
```cpp
HRESULT ApplyMetaData(  
        [in] ModuleID moduleID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="35de7-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="35de7-106">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="35de7-107">in Identificatore del modulo i cui metadati sono stati modificati.</span><span class="sxs-lookup"><span data-stu-id="35de7-107">[in] The identifier of the module whose metadata was changed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="35de7-108">Note</span><span class="sxs-lookup"><span data-stu-id="35de7-108">Remarks</span></span>  
 <span data-ttu-id="35de7-109">Se vengono apportate modifiche ai metadati dopo il callback [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) , è necessario chiamare questo metodo prima di utilizzare i nuovi metadati.</span><span class="sxs-lookup"><span data-stu-id="35de7-109">If metadata changes are made after the [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback, you must call this method before using the new metadata.</span></span>  
  
 <span data-ttu-id="35de7-110">`ApplyMetaData` supporta solo l'aggiunta dei seguenti tipi di metadati:</span><span class="sxs-lookup"><span data-stu-id="35de7-110">`ApplyMetaData` only supports adding the following types of metadata:</span></span>  
  
- <span data-ttu-id="35de7-111">`AssemblyRef` record, che è possibile creare chiamando [IMetaDataAssemblyEmit::D efineassemblyref](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md).</span><span class="sxs-lookup"><span data-stu-id="35de7-111">`AssemblyRef` records, which you create by calling the [IMetaDataAssemblyEmit::DefineAssemblyRef](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md).</span></span> <span data-ttu-id="35de7-112">ProcessOnStatus.</span><span class="sxs-lookup"><span data-stu-id="35de7-112">method.</span></span>  
  
- <span data-ttu-id="35de7-113">`TypeRef` record, creato chiamando il metodo [IMetaDataEmit::D efinetyperefbyname](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetyperefbyname-method.md) .</span><span class="sxs-lookup"><span data-stu-id="35de7-113">`TypeRef` records, which you create by calling the [IMetaDataEmit::DefineTypeRefByName](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetyperefbyname-method.md) method.</span></span>  
  
- <span data-ttu-id="35de7-114">`TypeSpec` record, che è possibile creare chiamando il metodo [IMetaDataEmit:: GetTokenFromTypeSpec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromtypespec-method.md) .</span><span class="sxs-lookup"><span data-stu-id="35de7-114">`TypeSpec` records, which you create by calling the [IMetaDataEmit::GetTokenFromTypeSpec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromtypespec-method.md) method.</span></span>  
  
- <span data-ttu-id="35de7-115">`MemberRef` record, creato chiamando il metodo [IMetaDataEmit::D efinememberref](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md) .</span><span class="sxs-lookup"><span data-stu-id="35de7-115">`MemberRef` records, which you create by calling the [IMetaDataEmit::DefineMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md) method.</span></span>  
  
- <span data-ttu-id="35de7-116">`MemberSpec` record, che è possibile creare chiamando il metodo [IMetaDataEmit2::D efinemethodspec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definemethodspec-method.md) .</span><span class="sxs-lookup"><span data-stu-id="35de7-116">`MemberSpec` records, which you create by calling the [IMetaDataEmit2::DefineMethodSpec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definemethodspec-method.md) method.</span></span>  
  
- <span data-ttu-id="35de7-117">`UserString` record, creato chiamando il metodo [IMetaDataEmit::D efineuserstring](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineuserstring-method.md) .</span><span class="sxs-lookup"><span data-stu-id="35de7-117">`UserString` records, which you create by calling the [IMetaDataEmit::DefineUserString](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineuserstring-method.md) method.</span></span>  

<span data-ttu-id="35de7-118">A partire da .NET Core 3,0, `ApplyMetaData` supporta anche i tipi seguenti:</span><span class="sxs-lookup"><span data-stu-id="35de7-118">Starting with .NET Core 3.0, `ApplyMetaData` also supports the following types:</span></span>

- <span data-ttu-id="35de7-119">`TypeDef` record, creato chiamando il metodo [IMetaDataEmit::D efinetypedef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md) .</span><span class="sxs-lookup"><span data-stu-id="35de7-119">`TypeDef` records, which you create by calling the [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md) method.</span></span>

- <span data-ttu-id="35de7-120">`MethodDef` record, creato chiamando il metodo [IMetaDataEmit::D efinemethod](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethod-method.md) .</span><span class="sxs-lookup"><span data-stu-id="35de7-120">`MethodDef` records, which you create by calling the [IMetaDataEmit::DefineMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethod-method.md) method.</span></span> <span data-ttu-id="35de7-121">Tuttavia, l'aggiunta di metodi virtuali a un tipo esistente non è supportata.</span><span class="sxs-lookup"><span data-stu-id="35de7-121">However, adding virtual methods to an existing type is not supported.</span></span> <span data-ttu-id="35de7-122">È necessario aggiungere i metodi virtuali prima del callback di [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) .</span><span class="sxs-lookup"><span data-stu-id="35de7-122">Virtual methods must be added before the [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback.</span></span>

## <a name="requirements"></a><span data-ttu-id="35de7-123">Requisiti</span><span class="sxs-lookup"><span data-stu-id="35de7-123">Requirements</span></span>  
 <span data-ttu-id="35de7-124">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="35de7-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="35de7-125">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="35de7-125">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="35de7-126">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="35de7-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="35de7-127">**Versioni di .NET Framework:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="35de7-127">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35de7-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="35de7-128">See also</span></span>

- [<span data-ttu-id="35de7-129">Interfaccia ICorProfilerInfo7</span><span class="sxs-lookup"><span data-stu-id="35de7-129">ICorProfilerInfo7 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md)
