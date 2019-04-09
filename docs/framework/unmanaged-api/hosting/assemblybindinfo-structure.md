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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ce79987c7fcf45b8d10dcc4613e053ee735941de
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59112814"
---
# <a name="assemblybindinfo-structure"></a><span data-ttu-id="181a7-102">Struttura AssemblyBindInfo</span><span class="sxs-lookup"><span data-stu-id="181a7-102">AssemblyBindInfo Structure</span></span>
<span data-ttu-id="181a7-103">Informazioni dettagliate sugli assembly di riferimento.</span><span class="sxs-lookup"><span data-stu-id="181a7-103">Provides detailed information about the referenced assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="181a7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="181a7-104">Syntax</span></span>  
  
```  
typedef struct _AssemblyBindInfo {  
    DWORD       dwAppDomainId;  
    LPCWSTR     lpReferencedIdentity;  
    LPCWSTR     lpPostPolicyIdentity;  
    DWORD       ePolicyLevel;  
} AssemblyBindInfo;  
```  
  
## <a name="members"></a><span data-ttu-id="181a7-105">Membri</span><span class="sxs-lookup"><span data-stu-id="181a7-105">Members</span></span>  
  
|<span data-ttu-id="181a7-106">Member</span><span class="sxs-lookup"><span data-stu-id="181a7-106">Member</span></span>|<span data-ttu-id="181a7-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="181a7-107">Description</span></span>|  
|------------|-----------------|  
|`dwAppDomainId`|<span data-ttu-id="181a7-108">Un identificatore univoco per il `IStream` restituito da una chiamata a [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md), da cui deve essere caricato l'assembly di riferimento.</span><span class="sxs-lookup"><span data-stu-id="181a7-108">A unique identifier for the `IStream` returned by a call to [IHostAssemblyStore::ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md), from which the referenced assembly is to be loaded.</span></span>|  
|`lpReferencedIdentity`|<span data-ttu-id="181a7-109">Un identificatore univoco per l'assembly di riferimento.</span><span class="sxs-lookup"><span data-stu-id="181a7-109">A unique identifier for the referenced assembly.</span></span>|  
|`lpPostPolicyIdentity`|<span data-ttu-id="181a7-110">L'identificatore per l'assembly di riferimento dopo l'applicazione di tutti i valori dei criteri di associazione.</span><span class="sxs-lookup"><span data-stu-id="181a7-110">The identifier for the referenced assembly after the application of any binding policy values.</span></span>|  
|`ePolicyLevel`|<span data-ttu-id="181a7-111">Uno dei [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) valori che indicano quali criteri di controllo delle versioni, se presente, devono essere applicati all'assembly di riferimento.</span><span class="sxs-lookup"><span data-stu-id="181a7-111">One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values that indicate which versioning policies, if any, should be applied to the referenced assembly.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="181a7-112">Note</span><span class="sxs-lookup"><span data-stu-id="181a7-112">Remarks</span></span>  
 <span data-ttu-id="181a7-113">L'identificatore univoco viene fornito dall'host `dwAppDomainId` a common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="181a7-113">The host supplies the unique identifier `dwAppDomainId` to the common language runtime (CLR).</span></span> <span data-ttu-id="181a7-114">Dopo una chiamata a `IHostAssemblyStore::ProvideAssembly` viene restituito, il runtime usa l'identificatore per determinare se il contenuto del `IStream` sono stati mappati.</span><span class="sxs-lookup"><span data-stu-id="181a7-114">After a call to `IHostAssemblyStore::ProvideAssembly` returns, the runtime uses the identifier to determine whether the contents of the `IStream` have been mapped.</span></span> <span data-ttu-id="181a7-115">In questo caso, il runtime carica la copia esistente anziché la modifica del flusso.</span><span class="sxs-lookup"><span data-stu-id="181a7-115">If so, the runtime loads the existing copy rather than remapping the stream.</span></span> <span data-ttu-id="181a7-116">Il runtime usa anche questo identificatore come chiave di ricerca per i flussi restituiscano dalle chiamate a [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-providemodule-method.md).</span><span class="sxs-lookup"><span data-stu-id="181a7-116">The runtime also uses this identifier as a lookup key for streams returned from calls to [IHostAssemblyStore::ProvideModule](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-providemodule-method.md).</span></span> <span data-ttu-id="181a7-117">Pertanto, l'identificatore deve essere univoco per le richieste di modulo e per le richieste di assembly.</span><span class="sxs-lookup"><span data-stu-id="181a7-117">Therefore, the identifier must be unique for module requests and for assembly requests.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="181a7-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="181a7-118">Requirements</span></span>  
 <span data-ttu-id="181a7-119">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="181a7-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="181a7-120">**Intestazione:** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="181a7-120">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="181a7-121">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="181a7-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="181a7-122">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="181a7-122">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="181a7-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="181a7-123">See also</span></span>

- [<span data-ttu-id="181a7-124">Strutture di hosting</span><span class="sxs-lookup"><span data-stu-id="181a7-124">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
- [<span data-ttu-id="181a7-125">Interfaccia ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="181a7-125">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="181a7-126">Interfaccia ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="181a7-126">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="181a7-127">Interfaccia IHostAssemblyManager</span><span class="sxs-lookup"><span data-stu-id="181a7-127">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [<span data-ttu-id="181a7-128">Interfaccia IHostAssemblyStore</span><span class="sxs-lookup"><span data-stu-id="181a7-128">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
- [<span data-ttu-id="181a7-129">Struttura ModuleBindInfo</span><span class="sxs-lookup"><span data-stu-id="181a7-129">ModuleBindInfo Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/modulebindinfo-structure.md)
