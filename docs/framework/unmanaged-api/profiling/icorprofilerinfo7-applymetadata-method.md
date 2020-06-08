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
# <a name="icorprofilerinfo7applymetadata-method"></a><span data-ttu-id="d370c-102">Metodo ICorProfilerInfo7:: ApplyMetaData</span><span class="sxs-lookup"><span data-stu-id="d370c-102">ICorProfilerInfo7::ApplyMetaData Method</span></span>
<span data-ttu-id="d370c-103">[Supportata in .NET Framework 4.6.1 e versioni successive]</span><span class="sxs-lookup"><span data-stu-id="d370c-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="d370c-104">Applica i metadati appena definiti dai `IMetadataEmit::Define*` metodi a un modulo specificato.</span><span class="sxs-lookup"><span data-stu-id="d370c-104">Applies the metadata newly defined by the `IMetadataEmit::Define*` methods to a specified module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d370c-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d370c-105">Syntax</span></span>  
  
```cpp
HRESULT ApplyMetaData(  
        [in] ModuleID moduleID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d370c-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="d370c-106">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="d370c-107">in Identificatore del modulo i cui metadati sono stati modificati.</span><span class="sxs-lookup"><span data-stu-id="d370c-107">[in] The identifier of the module whose metadata was changed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d370c-108">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="d370c-108">Remarks</span></span>  
 <span data-ttu-id="d370c-109">Se vengono apportate modifiche ai metadati dopo il callback [ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) , è necessario chiamare questo metodo prima di utilizzare i nuovi metadati.</span><span class="sxs-lookup"><span data-stu-id="d370c-109">If metadata changes are made after the [ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) callback, you must call this method before using the new metadata.</span></span>  
  
 <span data-ttu-id="d370c-110">`ApplyMetaData`supporta solo l'aggiunta dei seguenti tipi di metadati:</span><span class="sxs-lookup"><span data-stu-id="d370c-110">`ApplyMetaData` only supports adding the following types of metadata:</span></span>  
  
- <span data-ttu-id="d370c-111">`AssemblyRef`record creati chiamando [IMetaDataAssemblyEmit::D efineassemblyref](../metadata/imetadataassemblyemit-defineassemblyref-method.md).</span><span class="sxs-lookup"><span data-stu-id="d370c-111">`AssemblyRef` records, which you create by calling the [IMetaDataAssemblyEmit::DefineAssemblyRef](../metadata/imetadataassemblyemit-defineassemblyref-method.md).</span></span> <span data-ttu-id="d370c-112">ProcessOnStatus.</span><span class="sxs-lookup"><span data-stu-id="d370c-112">method.</span></span>  
  
- <span data-ttu-id="d370c-113">`TypeRef`record, che vengono creati chiamando il metodo [IMetaDataEmit::D efinetyperefbyname](../metadata/imetadataemit-definetyperefbyname-method.md) .</span><span class="sxs-lookup"><span data-stu-id="d370c-113">`TypeRef` records, which you create by calling the [IMetaDataEmit::DefineTypeRefByName](../metadata/imetadataemit-definetyperefbyname-method.md) method.</span></span>  
  
- <span data-ttu-id="d370c-114">`TypeSpec`record, che vengono creati chiamando il metodo [IMetaDataEmit:: GetTokenFromTypeSpec](../metadata/imetadataemit-gettokenfromtypespec-method.md) .</span><span class="sxs-lookup"><span data-stu-id="d370c-114">`TypeSpec` records, which you create by calling the [IMetaDataEmit::GetTokenFromTypeSpec](../metadata/imetadataemit-gettokenfromtypespec-method.md) method.</span></span>  
  
- <span data-ttu-id="d370c-115">`MemberRef`record, che vengono creati chiamando il metodo [IMetaDataEmit::D efinememberref](../metadata/imetadataemit-definememberref-method.md) .</span><span class="sxs-lookup"><span data-stu-id="d370c-115">`MemberRef` records, which you create by calling the [IMetaDataEmit::DefineMemberRef](../metadata/imetadataemit-definememberref-method.md) method.</span></span>  
  
- <span data-ttu-id="d370c-116">`MemberSpec`record, che vengono creati chiamando il metodo [IMetaDataEmit2::D efinemethodspec](../metadata/imetadataemit2-definemethodspec-method.md) .</span><span class="sxs-lookup"><span data-stu-id="d370c-116">`MemberSpec` records, which you create by calling the [IMetaDataEmit2::DefineMethodSpec](../metadata/imetadataemit2-definemethodspec-method.md) method.</span></span>  
  
- <span data-ttu-id="d370c-117">`UserString`record, che vengono creati chiamando il metodo [IMetaDataEmit::D efineuserstring](../metadata/imetadataemit-defineuserstring-method.md) .</span><span class="sxs-lookup"><span data-stu-id="d370c-117">`UserString` records, which you create by calling the [IMetaDataEmit::DefineUserString](../metadata/imetadataemit-defineuserstring-method.md) method.</span></span>  

<span data-ttu-id="d370c-118">A partire da .NET Core 3,0, `ApplyMetaData` supporta anche i tipi seguenti:</span><span class="sxs-lookup"><span data-stu-id="d370c-118">Starting with .NET Core 3.0, `ApplyMetaData` also supports the following types:</span></span>

- <span data-ttu-id="d370c-119">`TypeDef`record, che vengono creati chiamando il metodo [IMetaDataEmit::D efinetypedef](../metadata/imetadataemit-definetypedef-method.md) .</span><span class="sxs-lookup"><span data-stu-id="d370c-119">`TypeDef` records, which you create by calling the [IMetaDataEmit::DefineTypeDef](../metadata/imetadataemit-definetypedef-method.md) method.</span></span>

- <span data-ttu-id="d370c-120">`MethodDef`record, che vengono creati chiamando il metodo [IMetaDataEmit::D efinemethod](../metadata/imetadataemit-definemethod-method.md) .</span><span class="sxs-lookup"><span data-stu-id="d370c-120">`MethodDef` records, which you create by calling the [IMetaDataEmit::DefineMethod](../metadata/imetadataemit-definemethod-method.md) method.</span></span> <span data-ttu-id="d370c-121">Tuttavia, l'aggiunta di metodi virtuali a un tipo esistente non è supportata.</span><span class="sxs-lookup"><span data-stu-id="d370c-121">However, adding virtual methods to an existing type is not supported.</span></span> <span data-ttu-id="d370c-122">È necessario aggiungere i metodi virtuali prima del callback di [ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) .</span><span class="sxs-lookup"><span data-stu-id="d370c-122">Virtual methods must be added before the [ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) callback.</span></span>

## <a name="requirements"></a><span data-ttu-id="d370c-123">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d370c-123">Requirements</span></span>  
 <span data-ttu-id="d370c-124">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d370c-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d370c-125">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d370c-125">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d370c-126">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d370c-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d370c-127">**Versioni .NET Framework:**[!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d370c-127">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d370c-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d370c-128">See also</span></span>

- [<span data-ttu-id="d370c-129">Interfaccia ICorProfilerInfo7</span><span class="sxs-lookup"><span data-stu-id="d370c-129">ICorProfilerInfo7 Interface</span></span>](icorprofilerinfo7-interface.md)
