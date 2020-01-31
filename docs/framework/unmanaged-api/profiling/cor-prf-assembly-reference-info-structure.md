---
title: Struttura COR_PRF_ASSEMBLY_REFERENCE_INFO
ms.date: 03/30/2017
dev_langs:
- cpp
ms.assetid: c8c1d916-8d1a-4f82-8128-9fd3732383fc
ms.openlocfilehash: 4fdc8e1074bf45de3a8ab85500a85b124ce34fa1
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76867334"
---
# <a name="cor_prf_assembly_reference_info-structure"></a><span data-ttu-id="b37a9-102">Struttura COR_PRF_ASSEMBLY_REFERENCE_INFO</span><span class="sxs-lookup"><span data-stu-id="b37a9-102">COR_PRF_ASSEMBLY_REFERENCE_INFO Structure</span></span>
<span data-ttu-id="b37a9-103">[Supportato in .NET Framework 4.5.2 e versioni successive]</span><span class="sxs-lookup"><span data-stu-id="b37a9-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="b37a9-104">Fornisce Common Language Runtime con informazioni su un riferimento all'assembly che deve considerare quando esegue un percorso di chiusura del riferimento all'assembly.</span><span class="sxs-lookup"><span data-stu-id="b37a9-104">Provides the common language runtime with information about an assembly reference that it should consider when performing an assembly reference closure walk.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b37a9-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b37a9-105">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="b37a9-106">Membri</span><span class="sxs-lookup"><span data-stu-id="b37a9-106">Members</span></span>  
  
|<span data-ttu-id="b37a9-107">Member</span><span class="sxs-lookup"><span data-stu-id="b37a9-107">Member</span></span>|<span data-ttu-id="b37a9-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b37a9-108">Description</span></span>|  
|------------|-----------------|  
|`pbPublicKeyOrToken`|<span data-ttu-id="b37a9-109">Un puntatore alla chiave pubblica o token dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="b37a9-109">A pointer to the public key or token of the assembly.</span></span>|  
|`cbPublicKeyOrToken`|<span data-ttu-id="b37a9-110">Il numero di byte nella chiave pubblica o token.</span><span class="sxs-lookup"><span data-stu-id="b37a9-110">The number of bytes in the public key or token.</span></span>|  
|`szName`|<span data-ttu-id="b37a9-111">Il nome dell'assembly al quale viene fatto riferimento.</span><span class="sxs-lookup"><span data-stu-id="b37a9-111">The name of the assembly that is referenced.</span></span>|  
|`pMetaData`|<span data-ttu-id="b37a9-112">Un puntatore ai metadati dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="b37a9-112">A pointer to the assembly's metadata.</span></span>|  
|`pbHashValue`|<span data-ttu-id="b37a9-113">Un puntatore a un oggetto binario hash di grandi dimensioni (BLOB).</span><span class="sxs-lookup"><span data-stu-id="b37a9-113">A pointer to a hash binary large object (BLOB).</span></span>|  
|`cbHashValue`|<span data-ttu-id="b37a9-114">Il numero di byte nel BLOB hash.</span><span class="sxs-lookup"><span data-stu-id="b37a9-114">The number of bytes in the hash BLOB.</span></span>|  
|`dwAssemblyRefFlags`|<span data-ttu-id="b37a9-115">I flag dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="b37a9-115">The assembly's flags.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b37a9-116">Note</span><span class="sxs-lookup"><span data-stu-id="b37a9-116">Remarks</span></span>  
 <span data-ttu-id="b37a9-117">La struttura `COR_PRF_EX_CLAUSE_INFO` è popolata dal profiler quando dichiara altri riferimenti ad assembly che Common Language Runtime deve considerare quando esegue un percorso di chiusura del riferimento all'assembly.</span><span class="sxs-lookup"><span data-stu-id="b37a9-117">The `COR_PRF_EX_CLAUSE_INFO` structure is populated by the profiler when it declares additional assembly references that the common language runtime should consider when performing an assembly reference closure walk.</span></span>  
  
 <span data-ttu-id="b37a9-118">Se il profiler viene registrato per il metodo di callback [ICorProfilerCallback6:: GetAssemblyReferences](icorprofilercallback6-getassemblyreferences-method.md) , il runtime passa il percorso e il nome dell'assembly da caricare, insieme a un puntatore a un oggetto di interfaccia [ICorProfilerAssemblyReferenceProvider](icorprofilerassemblyreferenceprovider-interface.md) a tale metodo.</span><span class="sxs-lookup"><span data-stu-id="b37a9-118">If the profiler registers for the [ICorProfilerCallback6::GetAssemblyReferences](icorprofilercallback6-getassemblyreferences-method.md) callback method, the runtime passes the path and name of the assembly to be loaded, along with a pointer to an [ICorProfilerAssemblyReferenceProvider](icorprofilerassemblyreferenceprovider-interface.md) interface object to that method.</span></span> <span data-ttu-id="b37a9-119">Il profiler può quindi chiamare il metodo [ICorProfilerAssemblyReferenceProvider:: AddAssemblyReference](icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) con un oggetto `COR_PRF_ASSEMBLY_REFERENCE_INFO` per ogni assembly di destinazione a cui fa riferimento l'assembly specificato nel callback [ICorProfilerCallback6:: GetAssemblyReferences](icorprofilercallback6-getassemblyreferences-method.md) .</span><span class="sxs-lookup"><span data-stu-id="b37a9-119">The profiler can then call the [ICorProfilerAssemblyReferenceProvider::AddAssemblyReference](icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) method with a `COR_PRF_ASSEMBLY_REFERENCE_INFO` object for each target assembly it plans to reference from the assembly specified in the [ICorProfilerCallback6::GetAssemblyReferences](icorprofilercallback6-getassemblyreferences-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b37a9-120">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="b37a9-120">Requirements</span></span>  
 <span data-ttu-id="b37a9-121">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b37a9-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b37a9-122">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b37a9-122">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b37a9-123">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b37a9-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b37a9-124">**Versioni .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b37a9-124">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b37a9-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b37a9-125">See also</span></span>

- [<span data-ttu-id="b37a9-126">Strutture di profilatura</span><span class="sxs-lookup"><span data-stu-id="b37a9-126">Profiling Structures</span></span>](profiling-structures.md)
- [<span data-ttu-id="b37a9-127">Metodo GetAssemblyReferences</span><span class="sxs-lookup"><span data-stu-id="b37a9-127">GetAssemblyReferences Method</span></span>](icorprofilercallback6-getassemblyreferences-method.md)
- [<span data-ttu-id="b37a9-128">Metodo AddAssemblyReference</span><span class="sxs-lookup"><span data-stu-id="b37a9-128">AddAssemblyReference Method</span></span>](icorprofilerassemblyreferenceprovider-addassemblyreference-method.md)
