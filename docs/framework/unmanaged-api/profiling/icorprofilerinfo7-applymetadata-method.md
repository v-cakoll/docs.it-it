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
# <a name="icorprofilerinfo7applymetadata-method"></a><span data-ttu-id="4194a-102">Metodo ICorProfilerInfo7:: ApplyMetaData</span><span class="sxs-lookup"><span data-stu-id="4194a-102">ICorProfilerInfo7::ApplyMetaData Method</span></span>
<span data-ttu-id="4194a-103">[Supportata in .NET Framework 4.6.1 e versioni successive]</span><span class="sxs-lookup"><span data-stu-id="4194a-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="4194a-104">Applica i metadati appena definiti dal `IMetadataEmit::Define*` metodi a un modulo specificato.</span><span class="sxs-lookup"><span data-stu-id="4194a-104">Applies the metadata newly defined by the `IMetadataEmit::Define*` methods to a specified module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4194a-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4194a-105">Syntax</span></span>  
  
```cpp
HRESULT ApplyMetaData(  
        [in] ModuleID moduleID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4194a-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="4194a-106">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="4194a-107">in Identificatore del modulo i cui metadati sono stati modificati.</span><span class="sxs-lookup"><span data-stu-id="4194a-107">[in] The identifier of the module whose metadata was changed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4194a-108">Note</span><span class="sxs-lookup"><span data-stu-id="4194a-108">Remarks</span></span>  
 <span data-ttu-id="4194a-109">Se vengono apportate modifiche ai metadati dopo il callback [ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) , è necessario chiamare questo metodo prima di utilizzare i nuovi metadati.</span><span class="sxs-lookup"><span data-stu-id="4194a-109">If metadata changes are made after the [ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) callback, you must call this method before using the new metadata.</span></span>  
  
 <span data-ttu-id="4194a-110">`ApplyMetaData` supporta solo l'aggiunta dei seguenti tipi di metadati:</span><span class="sxs-lookup"><span data-stu-id="4194a-110">`ApplyMetaData` only supports adding the following types of metadata:</span></span>  
  
- <span data-ttu-id="4194a-111">`AssemblyRef` record, che è possibile creare chiamando [IMetaDataAssemblyEmit::D efineassemblyref](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md).</span><span class="sxs-lookup"><span data-stu-id="4194a-111">`AssemblyRef` records, which you create by calling the [IMetaDataAssemblyEmit::DefineAssemblyRef](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md).</span></span> <span data-ttu-id="4194a-112">ProcessOnStatus.</span><span class="sxs-lookup"><span data-stu-id="4194a-112">method.</span></span>  
  
- <span data-ttu-id="4194a-113">`TypeRef` record, creato chiamando il metodo [IMetaDataEmit::D efinetyperefbyname](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetyperefbyname-method.md) .</span><span class="sxs-lookup"><span data-stu-id="4194a-113">`TypeRef` records, which you create by calling the [IMetaDataEmit::DefineTypeRefByName](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetyperefbyname-method.md) method.</span></span>  
  
- <span data-ttu-id="4194a-114">`TypeSpec` record, che è possibile creare chiamando il metodo [IMetaDataEmit:: GetTokenFromTypeSpec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromtypespec-method.md) .</span><span class="sxs-lookup"><span data-stu-id="4194a-114">`TypeSpec` records, which you create by calling the [IMetaDataEmit::GetTokenFromTypeSpec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromtypespec-method.md) method.</span></span>  
  
- <span data-ttu-id="4194a-115">`MemberRef` record, creato chiamando il metodo [IMetaDataEmit::D efinememberref](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md) .</span><span class="sxs-lookup"><span data-stu-id="4194a-115">`MemberRef` records, which you create by calling the [IMetaDataEmit::DefineMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md) method.</span></span>  
  
- <span data-ttu-id="4194a-116">`MemberSpec` record, che è possibile creare chiamando il metodo [IMetaDataEmit2::D efinemethodspec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definemethodspec-method.md) .</span><span class="sxs-lookup"><span data-stu-id="4194a-116">`MemberSpec` records, which you create by calling the [IMetaDataEmit2::DefineMethodSpec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definemethodspec-method.md) method.</span></span>  
  
- <span data-ttu-id="4194a-117">`UserString` record, creato chiamando il metodo [IMetaDataEmit::D efineuserstring](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineuserstring-method.md) .</span><span class="sxs-lookup"><span data-stu-id="4194a-117">`UserString` records, which you create by calling the [IMetaDataEmit::DefineUserString](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineuserstring-method.md) method.</span></span>  

<span data-ttu-id="4194a-118">A partire da .NET Core 3,0, `ApplyMetaData` supporta anche i tipi seguenti:</span><span class="sxs-lookup"><span data-stu-id="4194a-118">Starting with .NET Core 3.0, `ApplyMetaData` also supports the following types:</span></span>

- <span data-ttu-id="4194a-119">`TypeDef` record, creato chiamando il metodo [IMetaDataEmit::D efinetypedef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md) .</span><span class="sxs-lookup"><span data-stu-id="4194a-119">`TypeDef` records, which you create by calling the [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md) method.</span></span>

- <span data-ttu-id="4194a-120">`MethodDef` record, creato chiamando il metodo [IMetaDataEmit::D efinemethod](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethod-method.md) .</span><span class="sxs-lookup"><span data-stu-id="4194a-120">`MethodDef` records, which you create by calling the [IMetaDataEmit::DefineMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethod-method.md) method.</span></span> <span data-ttu-id="4194a-121">Tuttavia, l'aggiunta di metodi virtuali a un tipo esistente non è supportata.</span><span class="sxs-lookup"><span data-stu-id="4194a-121">However, adding virtual methods to an existing type is not supported.</span></span> <span data-ttu-id="4194a-122">È necessario aggiungere i metodi virtuali prima del callback di [ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) .</span><span class="sxs-lookup"><span data-stu-id="4194a-122">Virtual methods must be added before the [ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) callback.</span></span>

## <a name="requirements"></a><span data-ttu-id="4194a-123">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="4194a-123">Requirements</span></span>  
 <span data-ttu-id="4194a-124">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4194a-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4194a-125">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4194a-125">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4194a-126">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4194a-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4194a-127">**Versioni .NET Framework:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4194a-127">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4194a-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4194a-128">See also</span></span>

- [<span data-ttu-id="4194a-129">Interfaccia ICorProfilerInfo7</span><span class="sxs-lookup"><span data-stu-id="4194a-129">ICorProfilerInfo7 Interface</span></span>](icorprofilerinfo7-interface.md)
