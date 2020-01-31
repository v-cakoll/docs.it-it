---
title: Metodo ICorProfilerCallback6::GetAssemblyReferences
ms.date: 03/30/2017
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
ms.openlocfilehash: 0717ef5fdb6c0447ceeb801f239be08f8cca5988
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865051"
---
# <a name="icorprofilercallback6getassemblyreferences-method"></a><span data-ttu-id="48653-102">Metodo ICorProfilerCallback6::GetAssemblyReferences</span><span class="sxs-lookup"><span data-stu-id="48653-102">ICorProfilerCallback6::GetAssemblyReferences Method</span></span>
<span data-ttu-id="48653-103">[Supportato in .NET Framework 4.5.2 e versioni successive]</span><span class="sxs-lookup"><span data-stu-id="48653-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="48653-104">Indica al profiler che un assembly è in una fase iniziale di caricamento, quando Common Language Runtime esegue un percorso di chiusura del riferimento all'assembly.</span><span class="sxs-lookup"><span data-stu-id="48653-104">Notifies the profiler that an assembly is in a very early loading stage, when the common language runtime performs an assembly reference closure walk.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48653-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="48653-105">Syntax</span></span>  
  
```cpp
HRESULT GetAssemblyReferences(        [in, string] const WCHAR* wszAssemblyPath,  
        [in] ICorProfilerAssemblyReferenceProvider* pAsmRefProvider  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="48653-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="48653-106">Parameters</span></span>  
 `wszAssemblyPath`  
 <span data-ttu-id="48653-107">[in] Percorso e nome dell'assembly i cui metadati verranno modificati.</span><span class="sxs-lookup"><span data-stu-id="48653-107">[in] The path and name of the assembly whose metadata will be modified.</span></span>  
  
 `pAsmRefProvider`  
 <span data-ttu-id="48653-108">in Puntatore all'indirizzo di un'interfaccia [ICorProfilerAssemblyReferenceProvider](icorprofilerassemblyreferenceprovider-interface.md) che specifica i riferimenti ad assembly da aggiungere.</span><span class="sxs-lookup"><span data-stu-id="48653-108">[in] A pointer to the address of an [ICorProfilerAssemblyReferenceProvider](icorprofilerassemblyreferenceprovider-interface.md) interface that specifies the assembly references to add.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="48653-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="48653-109">Return Value</span></span>  
 <span data-ttu-id="48653-110">I valori restituiti da questo callback vengono ignorati.</span><span class="sxs-lookup"><span data-stu-id="48653-110">Return values from this callback are ignored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="48653-111">Note</span><span class="sxs-lookup"><span data-stu-id="48653-111">Remarks</span></span>  
 <span data-ttu-id="48653-112">Questo callback viene controllato impostando il flag della maschera di evento [COR_PRF_HIGH_ADD_ASSEMBLY_REFERENCES](cor-prf-high-monitor-enumeration.md) quando si chiama il metodo [ICorProfilerCallback5:: SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) .</span><span class="sxs-lookup"><span data-stu-id="48653-112">This callback is controlled by setting the [COR_PRF_HIGH_ADD_ASSEMBLY_REFERENCES](cor-prf-high-monitor-enumeration.md) event mask flag when calling the [ICorProfilerCallback5::SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) method.</span></span> <span data-ttu-id="48653-113">Se il profiler viene registrato per il metodo di callback [ICorProfilerCallback6:: GetAssemblyReferences](icorprofilercallback6-getassemblyreferences-method.md) , il runtime passa il percorso e il nome dell'assembly da caricare, insieme a un puntatore a un oggetto di interfaccia [ICorProfilerAssemblyReferenceProvider](icorprofilerassemblyreferenceprovider-interface.md) a tale metodo.</span><span class="sxs-lookup"><span data-stu-id="48653-113">If the profiler registers for the [ICorProfilerCallback6::GetAssemblyReferences](icorprofilercallback6-getassemblyreferences-method.md) callback method, the runtime passes the path and name of the assembly to be loaded, along with a pointer to an [ICorProfilerAssemblyReferenceProvider](icorprofilerassemblyreferenceprovider-interface.md) interface object to that method.</span></span> <span data-ttu-id="48653-114">Il profiler può quindi chiamare il metodo [ICorProfilerAssemblyReferenceProvider:: AddAssemblyReference](icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) con un oggetto `COR_PRF_ASSEMBLY_REFERENCE_INFO` per ogni assembly di destinazione a cui fa riferimento l'assembly specificato nel callback di `GetAssemblyReferences`.</span><span class="sxs-lookup"><span data-stu-id="48653-114">The profiler can then call the [ICorProfilerAssemblyReferenceProvider::AddAssemblyReference](icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) method with a `COR_PRF_ASSEMBLY_REFERENCE_INFO` object for each target assembly it plans to reference from the assembly specified in the `GetAssemblyReferences` callback.</span></span>  
  
 <span data-ttu-id="48653-115">Usare il callback `GetAssemblyReferences` solo se il profiler deve modificare i metadati di un assembly per aggiungere riferimenti.</span><span class="sxs-lookup"><span data-stu-id="48653-115">Use the `GetAssemblyReferences` callback only if the profiler has to modify an assembly's metadata to add assembly references.</span></span> <span data-ttu-id="48653-116">Si noti tuttavia che la modifica effettiva dei metadati di un assembly viene eseguita nel metodo di callback [ICorProfilerCallback:: ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md). Il profiler deve implementare il metodo di callback `GetAssemblyReferences` per informare l'Common Language Runtime (CLR) che i riferimenti ad assembly verranno aggiunti quando il modulo è stato caricato.</span><span class="sxs-lookup"><span data-stu-id="48653-116">(But note that the actual modification of an assembly's metadata is done in the [ICorProfilerCallback::ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md)callback method.) The profiler should implement the `GetAssemblyReferences` callback method to inform the common language runtime (CLR) that assembly references will be added when the module has been loaded.</span></span>  <span data-ttu-id="48653-117">Questo garantisce che le decisioni di condivisione prese da CLR in questa fase iniziale restino valide anche se il profiler prevede di modificare i riferimenti all'assembly di metadati in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="48653-117">This helps ensure that assembly sharing decisions made by the CLR during this early stage remain valid although the profiler plans to modify the metadata assembly references later.</span></span>  <span data-ttu-id="48653-118">In questo modo è possibile evitare alcune situazioni in cui le modifiche dei metadati del profiler provocano un errore `SECURITY_E_INCOMPATIBLE_SHARE`.</span><span class="sxs-lookup"><span data-stu-id="48653-118">This can avoid some instances in which profiler metadata modifications cause an `SECURITY_E_INCOMPATIBLE_SHARE` error.</span></span>  
  
 <span data-ttu-id="48653-119">Il profiler usa l'oggetto [ICorProfilerAssemblyReferenceProvider](icorprofilerassemblyreferenceprovider-interface.md) fornito da questo metodo per aggiungere riferimenti ad assembly al Walker di chiusura del riferimento all'assembly CLR.</span><span class="sxs-lookup"><span data-stu-id="48653-119">The profiler uses the [ICorProfilerAssemblyReferenceProvider](icorprofilerassemblyreferenceprovider-interface.md) object provided by this method to add assembly references to the CLR assembly reference closure walker.</span></span>  <span data-ttu-id="48653-120">L'oggetto [ICorProfilerAssemblyReferenceProvider](icorprofilerassemblyreferenceprovider-interface.md) deve essere utilizzato solo dall'interno di questo callback.</span><span class="sxs-lookup"><span data-stu-id="48653-120">The [ICorProfilerAssemblyReferenceProvider](icorprofilerassemblyreferenceprovider-interface.md) object should be used only from within this callback.</span></span> <span data-ttu-id="48653-121">Le chiamate al metodo [ICorProfilerAssemblyReferenceProvider:: AddAssemblyReference](icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) da questo callback non comportano la modifica dei metadati, ma solo in un percorso di chiusura del riferimento all'assembly modificato.</span><span class="sxs-lookup"><span data-stu-id="48653-121">Calls to the [ICorProfilerAssemblyReferenceProvider::AddAssemblyReference](icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) method from this callback don't result in modified metadata, but only in a modified assembly reference closure walk.</span></span> <span data-ttu-id="48653-122">Il profiler dovrà ancora usare un oggetto [IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md) per aggiungere in modo esplicito i riferimenti ad assembly dal callback [ICorProfilerCallback:: ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) per l'assembly di riferimento, anche se implementa il callback `GetAssemblyReferences`.</span><span class="sxs-lookup"><span data-stu-id="48653-122">The profiler will still have to use an [IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md) object to explicitly add assembly references from within the [ICorProfilerCallback::ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) callback for the referencing assembly, even if it implements the `GetAssemblyReferences` callback.</span></span>  
  
 <span data-ttu-id="48653-123">Il profiler deve essere pronto a ricevere chiamate duplicate a questo callback per lo stesso assembly e deve rispondere in modo identico per ogni chiamata duplicata (effettuando lo stesso set di chiamate [ICorProfilerAssemblyReferenceProvider:: AddAssemblyReference](icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) ).</span><span class="sxs-lookup"><span data-stu-id="48653-123">The profiler should be prepared to receive duplicate calls to this callback for the same assembly, and should respond identically for each such duplicate call (by making the same set of [ICorProfilerAssemblyReferenceProvider::AddAssemblyReference](icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) calls).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="48653-124">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="48653-124">Requirements</span></span>  
 <span data-ttu-id="48653-125">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="48653-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="48653-126">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="48653-126">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="48653-127">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="48653-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="48653-128">**Versioni .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="48653-128">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48653-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="48653-129">See also</span></span>

- [<span data-ttu-id="48653-130">Interfaccia ICorProfilerCallback6</span><span class="sxs-lookup"><span data-stu-id="48653-130">ICorProfilerCallback6 Interface</span></span>](icorprofilercallback6-interface.md)
- [<span data-ttu-id="48653-131">Metodo ModuleLoadFinished</span><span class="sxs-lookup"><span data-stu-id="48653-131">ModuleLoadFinished Method</span></span>](icorprofilercallback-moduleloadfinished-method.md)
- [<span data-ttu-id="48653-132">Struttura COR_PRF_ASSEMBLY_REFERENCE_INFO</span><span class="sxs-lookup"><span data-stu-id="48653-132">COR_PRF_ASSEMBLY_REFERENCE_INFO Structure</span></span>](cor-prf-assembly-reference-info-structure.md)
- [<span data-ttu-id="48653-133">Interfaccia ICorProfilerAssemblyReferenceProvider</span><span class="sxs-lookup"><span data-stu-id="48653-133">ICorProfilerAssemblyReferenceProvider Interface</span></span>](icorprofilerassemblyreferenceprovider-interface.md)
