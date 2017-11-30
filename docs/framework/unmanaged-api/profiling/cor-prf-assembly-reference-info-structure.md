---
title: Struttura COR_PRF_ASSEMBLY_REFERENCE_INFO
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: cpp
ms.assetid: c8c1d916-8d1a-4f82-8128-9fd3732383fc
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 000a338400efa0d70e690f585518304a8b525346
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="corprfassemblyreferenceinfo-structure"></a><span data-ttu-id="e0cf2-102">Struttura COR_PRF_ASSEMBLY_REFERENCE_INFO</span><span class="sxs-lookup"><span data-stu-id="e0cf2-102">COR_PRF_ASSEMBLY_REFERENCE_INFO Structure</span></span>
<span data-ttu-id="e0cf2-103">[Supportato in .NET Framework 4.5.2 e versioni successive]</span><span class="sxs-lookup"><span data-stu-id="e0cf2-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="e0cf2-104">Fornisce Common Language Runtime con informazioni su un riferimento all'assembly che deve considerare quando esegue un percorso di chiusura del riferimento all'assembly.</span><span class="sxs-lookup"><span data-stu-id="e0cf2-104">Provides the common language runtime with information about an assembly reference that it should consider when performing an assembly reference closure walk.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0cf2-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e0cf2-105">Syntax</span></span>  
  
```cpp  
typedef struct _COR_PRF_ASSEMBLY_REFERENCE_INFO {  
    void* pbPublicKeyOrToken;  
    ULONG cbPublicKeyOrToken;  
    LPCWSTR szName;  
    ASSEMBLYMETADATA* pMetaData;  
    void* pbHashValue;  
    ULONG cbHashValue;  
    DWORD dwAssemblyRefFlags;  
} COR_PRF_EX_CLAUSE_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="e0cf2-106">Membri</span><span class="sxs-lookup"><span data-stu-id="e0cf2-106">Members</span></span>  
  
|<span data-ttu-id="e0cf2-107">Membro</span><span class="sxs-lookup"><span data-stu-id="e0cf2-107">Member</span></span>|<span data-ttu-id="e0cf2-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e0cf2-108">Description</span></span>|  
|------------|-----------------|  
|`pbPublicKeyOrToken`|<span data-ttu-id="e0cf2-109">Un puntatore alla chiave pubblica o token dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="e0cf2-109">A pointer to the public key or token of the assembly.</span></span>|  
|`cbPublicKeyOrToken`|<span data-ttu-id="e0cf2-110">Il numero di byte nella chiave pubblica o token.</span><span class="sxs-lookup"><span data-stu-id="e0cf2-110">The number of bytes in the public key or token.</span></span>|  
|`szName`|<span data-ttu-id="e0cf2-111">Il nome dell'assembly al quale viene fatto riferimento.</span><span class="sxs-lookup"><span data-stu-id="e0cf2-111">The name of the assembly that is referenced.</span></span>|  
|`pMetaData`|<span data-ttu-id="e0cf2-112">Un puntatore ai metadati dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="e0cf2-112">A pointer to the assembly's metadata.</span></span>|  
|`pbHashValue`|<span data-ttu-id="e0cf2-113">Un puntatore a un oggetto binario hash di grandi dimensioni (BLOB).</span><span class="sxs-lookup"><span data-stu-id="e0cf2-113">A pointer to a hash binary large object (BLOB).</span></span>|  
|`cbHashValue`|<span data-ttu-id="e0cf2-114">Il numero di byte nel BLOB hash.</span><span class="sxs-lookup"><span data-stu-id="e0cf2-114">The number of bytes in the hash BLOB.</span></span>|  
|`dwAssemblyRefFlags`|<span data-ttu-id="e0cf2-115">I flag dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="e0cf2-115">The assembly's flags.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e0cf2-116">Note</span><span class="sxs-lookup"><span data-stu-id="e0cf2-116">Remarks</span></span>  
 <span data-ttu-id="e0cf2-117">La struttura `COR_PRF_EX_CLAUSE_INFO` è popolata dal profiler quando dichiara altri riferimenti ad assembly che Common Language Runtime deve considerare quando esegue un percorso di chiusura del riferimento all'assembly.</span><span class="sxs-lookup"><span data-stu-id="e0cf2-117">The `COR_PRF_EX_CLAUSE_INFO` structure is populated by the profiler when it declares additional assembly references that the common language runtime should consider when performing an assembly reference closure walk.</span></span>  
  
 <span data-ttu-id="e0cf2-118">Se il profiler si registra per il [icorprofilercallback6:: Getassemblyreferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) il metodo di callback, il runtime passa il percorso e il nome dell'assembly da caricare, insieme a un puntatore a un [ ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md) oggetto dell'interfaccia a tale metodo.</span><span class="sxs-lookup"><span data-stu-id="e0cf2-118">If the profiler registers for the [ICorProfilerCallback6::GetAssemblyReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) callback method, the runtime passes the path and name of the assembly to be loaded, along with a pointer to an [ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md) interface object to that method.</span></span> <span data-ttu-id="e0cf2-119">Il profiler può quindi chiamare il [Icorprofilerassemblyreferenceprovider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) metodo con un `COR_PRF_ASSEMBLY_REFERENCE_INFO` oggetto per ogni assembly di destinazione al quale intende fare riferimento dall'assembly specificato nella [ Icorprofilercallback6:: Getassemblyreferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) callback.</span><span class="sxs-lookup"><span data-stu-id="e0cf2-119">The profiler can then call the [ICorProfilerAssemblyReferenceProvider::AddAssemblyReference](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) method with a `COR_PRF_ASSEMBLY_REFERENCE_INFO` object for each target assembly it plans to reference from the assembly specified in the [ICorProfilerCallback6::GetAssemblyReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e0cf2-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e0cf2-120">Requirements</span></span>  
 <span data-ttu-id="e0cf2-121">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e0cf2-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e0cf2-122">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e0cf2-122">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e0cf2-123">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e0cf2-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e0cf2-124">**Versioni di .NET framework:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e0cf2-124">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0cf2-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e0cf2-125">See Also</span></span>  
 [<span data-ttu-id="e0cf2-126">Strutture di profilatura</span><span class="sxs-lookup"><span data-stu-id="e0cf2-126">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)  
 [<span data-ttu-id="e0cf2-127">Metodo GetAssemblyReferences</span><span class="sxs-lookup"><span data-stu-id="e0cf2-127">GetAssemblyReferences Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md)  
 [<span data-ttu-id="e0cf2-128">Metodo AddAssemblyReference</span><span class="sxs-lookup"><span data-stu-id="e0cf2-128">AddAssemblyReference Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-addassemblyreference-method.md)
