---
title: Struttura AssemblyBindInfo
ms.date: 03/30/2017
api_name:
- AssemblyBindInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- AssemblyBindInfo
helpviewer_keywords:
- AssemblyBindInfo structure [.NET Framework hosting]
ms.assetid: 6fc01e98-c2e7-49de-ab9f-95937cc89017
topic_type:
- apiref
ms.openlocfilehash: 615637813b08629aaea74b23fa2737f52d61bafb
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616918"
---
# <a name="assemblybindinfo-structure"></a><span data-ttu-id="a74c3-102">Struttura AssemblyBindInfo</span><span class="sxs-lookup"><span data-stu-id="a74c3-102">AssemblyBindInfo Structure</span></span>
<span data-ttu-id="a74c3-103">Fornisce informazioni dettagliate sull'assembly a cui si fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="a74c3-103">Provides detailed information about the referenced assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a74c3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a74c3-104">Syntax</span></span>  
  
```cpp  
typedef struct _AssemblyBindInfo {  
    DWORD       dwAppDomainId;  
    LPCWSTR     lpReferencedIdentity;  
    LPCWSTR     lpPostPolicyIdentity;  
    DWORD       ePolicyLevel;  
} AssemblyBindInfo;  
```  
  
## <a name="members"></a><span data-ttu-id="a74c3-105">Membri</span><span class="sxs-lookup"><span data-stu-id="a74c3-105">Members</span></span>  
  
|<span data-ttu-id="a74c3-106">Membro</span><span class="sxs-lookup"><span data-stu-id="a74c3-106">Member</span></span>|<span data-ttu-id="a74c3-107">Description</span><span class="sxs-lookup"><span data-stu-id="a74c3-107">Description</span></span>|  
|------------|-----------------|  
|`dwAppDomainId`|<span data-ttu-id="a74c3-108">Identificatore univoco per l'oggetto `IStream` restituito da una chiamata a [IHostAssemblyStore::P rovideassembly](ihostassemblystore-provideassembly-method.md), da cui deve essere caricato l'assembly a cui si fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="a74c3-108">A unique identifier for the `IStream` returned by a call to [IHostAssemblyStore::ProvideAssembly](ihostassemblystore-provideassembly-method.md), from which the referenced assembly is to be loaded.</span></span>|  
|`lpReferencedIdentity`|<span data-ttu-id="a74c3-109">Identificatore univoco per l'assembly a cui si fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="a74c3-109">A unique identifier for the referenced assembly.</span></span>|  
|`lpPostPolicyIdentity`|<span data-ttu-id="a74c3-110">Identificatore dell'assembly a cui si fa riferimento dopo l'applicazione di tutti i valori dei criteri di associazione.</span><span class="sxs-lookup"><span data-stu-id="a74c3-110">The identifier for the referenced assembly after the application of any binding policy values.</span></span>|  
|`ePolicyLevel`|<span data-ttu-id="a74c3-111">Uno dei valori di [EPolicyAction](epolicyaction-enumeration.md) che indica quali criteri di controllo delle versioni, se presenti, devono essere applicati all'assembly a cui si fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="a74c3-111">One of the [EPolicyAction](epolicyaction-enumeration.md) values that indicate which versioning policies, if any, should be applied to the referenced assembly.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a74c3-112">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="a74c3-112">Remarks</span></span>  
 <span data-ttu-id="a74c3-113">L'host fornisce l'identificatore univoco `dwAppDomainId` al Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="a74c3-113">The host supplies the unique identifier `dwAppDomainId` to the common language runtime (CLR).</span></span> <span data-ttu-id="a74c3-114">Dopo che una chiamata a `IHostAssemblyStore::ProvideAssembly` restituisce, il runtime usa l'identificatore per determinare se `IStream` è stato eseguito il mapping del contenuto di.</span><span class="sxs-lookup"><span data-stu-id="a74c3-114">After a call to `IHostAssemblyStore::ProvideAssembly` returns, the runtime uses the identifier to determine whether the contents of the `IStream` have been mapped.</span></span> <span data-ttu-id="a74c3-115">In tal caso, il runtime carica la copia esistente anziché rimappare il flusso.</span><span class="sxs-lookup"><span data-stu-id="a74c3-115">If so, the runtime loads the existing copy rather than remapping the stream.</span></span> <span data-ttu-id="a74c3-116">Il runtime usa anche questo identificatore come chiave di ricerca per i flussi restituiti dalle chiamate a [IHostAssemblyStore::P rovidemodule](ihostassemblystore-providemodule-method.md).</span><span class="sxs-lookup"><span data-stu-id="a74c3-116">The runtime also uses this identifier as a lookup key for streams returned from calls to [IHostAssemblyStore::ProvideModule](ihostassemblystore-providemodule-method.md).</span></span> <span data-ttu-id="a74c3-117">Pertanto, l'identificatore deve essere univoco per le richieste di modulo e per le richieste di assembly.</span><span class="sxs-lookup"><span data-stu-id="a74c3-117">Therefore, the identifier must be unique for module requests and for assembly requests.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a74c3-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a74c3-118">Requirements</span></span>  
 <span data-ttu-id="a74c3-119">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a74c3-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a74c3-120">**Intestazione:** MSCorEE. idl</span><span class="sxs-lookup"><span data-stu-id="a74c3-120">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="a74c3-121">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="a74c3-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a74c3-122">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a74c3-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a74c3-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a74c3-123">See also</span></span>

- [<span data-ttu-id="a74c3-124">Strutture di hosting</span><span class="sxs-lookup"><span data-stu-id="a74c3-124">Hosting Structures</span></span>](hosting-structures.md)
- [<span data-ttu-id="a74c3-125">Interfaccia ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="a74c3-125">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="a74c3-126">Interfaccia ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="a74c3-126">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="a74c3-127">Interfaccia IHostAssemblyManager</span><span class="sxs-lookup"><span data-stu-id="a74c3-127">IHostAssemblyManager Interface</span></span>](ihostassemblymanager-interface.md)
- [<span data-ttu-id="a74c3-128">Interfaccia IHostAssemblyStore</span><span class="sxs-lookup"><span data-stu-id="a74c3-128">IHostAssemblyStore Interface</span></span>](ihostassemblystore-interface.md)
- [<span data-ttu-id="a74c3-129">Struttura ModuleBindInfo</span><span class="sxs-lookup"><span data-stu-id="a74c3-129">ModuleBindInfo Structure</span></span>](modulebindinfo-structure.md)
