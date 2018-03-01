---
title: Metodo ICorProfilerCallback6::GetAssemblyReferences
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- cpp
api_name:
- ICorProfilerCallback6.GetAssemblyReferences
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.assetid: 8b391afb-d79f-41bd-94ce-43ce62c6b5fc
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: bc2e80d6d8207a869d43beb46cc9448bdd86dfec
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallback6getassemblyreferences-method"></a><span data-ttu-id="1444e-102">Metodo ICorProfilerCallback6::GetAssemblyReferences</span><span class="sxs-lookup"><span data-stu-id="1444e-102">ICorProfilerCallback6::GetAssemblyReferences Method</span></span>
<span data-ttu-id="1444e-103">[Supportato in .NET Framework 4.5.2 e versioni successive]</span><span class="sxs-lookup"><span data-stu-id="1444e-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="1444e-104">Indica al profiler che un assembly è in una fase iniziale di caricamento, quando Common Language Runtime esegue un percorso di chiusura del riferimento all'assembly.</span><span class="sxs-lookup"><span data-stu-id="1444e-104">Notifies the profiler that an assembly is in a very early loading stage, when the common language runtime performs an assembly reference closure walk.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1444e-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1444e-105">Syntax</span></span>  
  
```cpp
HRESULT GetAssemblyReferences(        [in, string] const WCHAR* wszAssemblyPath,  
        [in] ICorProfilerAssemblyReferenceProvider* pAsmRefProvider  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1444e-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="1444e-106">Parameters</span></span>  
 `wszAssemblyPath`  
 <span data-ttu-id="1444e-107">[in] Percorso e nome dell'assembly i cui metadati verranno modificati.</span><span class="sxs-lookup"><span data-stu-id="1444e-107">[in] The path and name of the assembly whose metadata will be modified.</span></span>  
  
 `pAsmRefProvider`  
 <span data-ttu-id="1444e-108">[in] Un puntatore all'indirizzo di un [ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md) fa riferimento all'interfaccia che specifica l'assembly da aggiungere.</span><span class="sxs-lookup"><span data-stu-id="1444e-108">[in] A pointer to the address of an [ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md) interface that specifies the assembly references to add.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1444e-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="1444e-109">Return Value</span></span>  
 <span data-ttu-id="1444e-110">I valori restituiti da questo callback vengono ignorati.</span><span class="sxs-lookup"><span data-stu-id="1444e-110">Return values from this callback are ignored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1444e-111">Note</span><span class="sxs-lookup"><span data-stu-id="1444e-111">Remarks</span></span>  
 <span data-ttu-id="1444e-112">Questo callback viene controllato impostando il [COR_PRF_HIGH_ADD_ASSEMBLY_REFERENCES](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md) flag maschera eventi quando si chiama il [icorprofilercallback5:: Seteventmask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) metodo.</span><span class="sxs-lookup"><span data-stu-id="1444e-112">This callback is controlled by setting the [COR_PRF_HIGH_ADD_ASSEMBLY_REFERENCES](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md) event mask flag when calling the [ICorProfilerCallback5::SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) method.</span></span> <span data-ttu-id="1444e-113">Se il profiler si registra per il [icorprofilercallback6:: Getassemblyreferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) il metodo di callback, il runtime passa il percorso e il nome dell'assembly da caricare, insieme a un puntatore a un [ ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md) oggetto dell'interfaccia a tale metodo.</span><span class="sxs-lookup"><span data-stu-id="1444e-113">If the profiler registers for the [ICorProfilerCallback6::GetAssemblyReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) callback method, the runtime passes the path and name of the assembly to be loaded, along with a pointer to an [ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md) interface object to that method.</span></span> <span data-ttu-id="1444e-114">Il profiler può quindi chiamare il [Icorprofilerassemblyreferenceprovider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) metodo con un `COR_PRF_ASSEMBLY_REFERENCE_INFO` oggetto per ogni assembly di destinazione al quale intende fare riferimento dall'assembly specificato nella `GetAssemblyReferences` callback.</span><span class="sxs-lookup"><span data-stu-id="1444e-114">The profiler can then call the [ICorProfilerAssemblyReferenceProvider::AddAssemblyReference](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) method with a `COR_PRF_ASSEMBLY_REFERENCE_INFO` object for each target assembly it plans to reference from the assembly specified in the `GetAssemblyReferences` callback.</span></span>  
  
 <span data-ttu-id="1444e-115">Usare il callback `GetAssemblyReferences` solo se il profiler deve modificare i metadati di un assembly per aggiungere riferimenti.</span><span class="sxs-lookup"><span data-stu-id="1444e-115">Use the `GetAssemblyReferences` callback only if the profiler has to modify an assembly's metadata to add assembly references.</span></span> <span data-ttu-id="1444e-116">(Si noti che l'effettiva modifica dei metadati dell'assembly, un'operazione viene eseguita nel [ICorProfilerCallback:: ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)metodo di callback.) Il profiler deve implementare il metodo di callback `GetAssemblyReferences` per comunicare a Common Language Runtime (CLR) che i riferimenti ad assembly verranno aggiunti dopo il caricamento del form.</span><span class="sxs-lookup"><span data-stu-id="1444e-116">(But note that the actual modification of an assembly's metadata is done in the [ICorProfilerCallback::ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)callback method.) The profiler should implement the `GetAssemblyReferences` callback method to inform the common language runtime (CLR) that assembly references will be added when the module has been loaded.</span></span>  <span data-ttu-id="1444e-117">Questo garantisce che le decisioni di condivisione prese da CLR in questa fase iniziale restino valide anche se il profiler prevede di modificare i riferimenti all'assembly di metadati in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="1444e-117">This helps ensure that assembly sharing decisions made by the CLR during this early stage remain valid although the profiler plans to modify the metadata assembly references later.</span></span>  <span data-ttu-id="1444e-118">In questo modo è possibile evitare alcune situazioni in cui le modifiche dei metadati del profiler provocano un errore `SECURITY_E_INCOMPATIBLE_SHARE`.</span><span class="sxs-lookup"><span data-stu-id="1444e-118">This can avoid some instances in which profiler metadata modifications cause an `SECURITY_E_INCOMPATIBLE_SHARE` error.</span></span>  
  
 <span data-ttu-id="1444e-119">Il profiler utilizza la [ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md) oggetto fornito da questo metodo per aggiungere riferimenti ad assembly per il CLR assembly al walker di chiusura.</span><span class="sxs-lookup"><span data-stu-id="1444e-119">The profiler uses the [ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md) object provided by this method to add assembly references to the CLR assembly reference closure walker.</span></span>  <span data-ttu-id="1444e-120">Il [ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md) oggetto deve essere usato solo dall'interno di questo callback.</span><span class="sxs-lookup"><span data-stu-id="1444e-120">The [ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md) object should be used only from within this callback.</span></span> <span data-ttu-id="1444e-121">Le chiamate al [Icorprofilerassemblyreferenceprovider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) metodo da questo callback non ottenere metadati modificati, ma solo in un percorso di chiusura del riferimento assembly modificato.</span><span class="sxs-lookup"><span data-stu-id="1444e-121">Calls to the [ICorProfilerAssemblyReferenceProvider::AddAssemblyReference](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) method from this callback don't result in modified metadata, but only in a modified assembly reference closure walk.</span></span> <span data-ttu-id="1444e-122">Il profiler dovrà comunque usare un [IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md) oggetto da aggiungere in modo esplicito i riferimenti ad assembly dall'interno di [ICorProfilerCallback:: ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback per il tipo di riferimento assembly, anche se implementa il `GetAssemblyReferences` callback.</span><span class="sxs-lookup"><span data-stu-id="1444e-122">The profiler will still have to use an [IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md) object to explicitly add assembly references from within the [ICorProfilerCallback::ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback for the referencing assembly, even if it implements the `GetAssemblyReferences` callback.</span></span>  
  
 <span data-ttu-id="1444e-123">Il profiler deve essere preparato a ricevere chiamate duplicate a questo callback per lo stesso assembly e deve rispondere in modo identico per ogni chiamata duplicata (eseguendo lo stesso set di [ICorProfilerAssemblyReferenceProvider:: AddAssemblyReference](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) chiamate).</span><span class="sxs-lookup"><span data-stu-id="1444e-123">The profiler should be prepared to receive duplicate calls to this callback for the same assembly, and should respond identically for each such duplicate call (by making the same set of [ICorProfilerAssemblyReferenceProvider::AddAssemblyReference](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) calls).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1444e-124">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1444e-124">Requirements</span></span>  
 <span data-ttu-id="1444e-125">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1444e-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1444e-126">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1444e-126">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1444e-127">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1444e-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1444e-128">**Versioni di .NET framework:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1444e-128">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1444e-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1444e-129">See Also</span></span>  
 [<span data-ttu-id="1444e-130">Interfaccia ICorProfilerCallback6</span><span class="sxs-lookup"><span data-stu-id="1444e-130">ICorProfilerCallback6 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-interface.md)  
 [<span data-ttu-id="1444e-131">Metodo ModuleLoadFinished</span><span class="sxs-lookup"><span data-stu-id="1444e-131">ModuleLoadFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)  
 [<span data-ttu-id="1444e-132">Struttura COR_PRF_ASSEMBLY_REFERENCE_INFO</span><span class="sxs-lookup"><span data-stu-id="1444e-132">COR_PRF_ASSEMBLY_REFERENCE_INFO Structure</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-assembly-reference-info-structure.md)  
 [<span data-ttu-id="1444e-133">Interfaccia ICorProfilerAssemblyReferenceProvider</span><span class="sxs-lookup"><span data-stu-id="1444e-133">ICorProfilerAssemblyReferenceProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md)
