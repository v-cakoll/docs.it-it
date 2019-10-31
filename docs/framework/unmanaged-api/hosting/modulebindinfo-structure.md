---
title: Struttura ModuleBindInfo
ms.date: 03/30/2017
api_name:
- ModuleBindInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ModuleBindInfo
helpviewer_keywords:
- ModuleBindInfo structure [.NET Framework hosting]
ms.assetid: 632d4adc-dbc9-4ce8-9397-abc3285c1c69
topic_type:
- apiref
ms.openlocfilehash: ae40d8adaae70ccff6e8058858a506267d58873f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133744"
---
# <a name="modulebindinfo-structure"></a><span data-ttu-id="009b7-102">Struttura ModuleBindInfo</span><span class="sxs-lookup"><span data-stu-id="009b7-102">ModuleBindInfo Structure</span></span>
<span data-ttu-id="009b7-103">Fornisce informazioni dettagliate sul modulo a cui si fa riferimento e sull'assembly che la contiene.</span><span class="sxs-lookup"><span data-stu-id="009b7-103">Provides detailed information about the referenced module and the assembly that contains it.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="009b7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="009b7-104">Syntax</span></span>  
  
```cpp  
typedef struct _ModuleBindInfo {  
    DWORD    dwAppDomainId;  
    LPCWSTR  lpAssemblyIdentity;  
    LPCWSTR  lpModuleName  
} ModuleBindInfo;  
```  
  
## <a name="members"></a><span data-ttu-id="009b7-105">Members</span><span class="sxs-lookup"><span data-stu-id="009b7-105">Members</span></span>  
  
|<span data-ttu-id="009b7-106">Member</span><span class="sxs-lookup"><span data-stu-id="009b7-106">Member</span></span>|<span data-ttu-id="009b7-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="009b7-107">Description</span></span>|  
|------------|-----------------|  
|`dwAppDomainId`|<span data-ttu-id="009b7-108">Identificatore univoco per il `IStream` restituito da una chiamata al metodo [IHostAssemblyStore::P rovidemodule](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-providemodule-method.md) da cui deve essere caricato il modulo a cui si fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="009b7-108">A unique identifier for the `IStream` that is returned by a call to the [IHostAssemblyStore::ProvideModule](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-providemodule-method.md) method from which the referenced module is to be loaded.</span></span>|  
|`lpAssemblyIdentity`|<span data-ttu-id="009b7-109">Identificatore univoco per l'assembly che contiene il modulo a cui si fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="009b7-109">A unique identifier for the assembly that contains the referenced module.</span></span>|  
|`lpModuleName`|<span data-ttu-id="009b7-110">Nome del modulo a cui si fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="009b7-110">The name of the referenced module.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="009b7-111">Note</span><span class="sxs-lookup"><span data-stu-id="009b7-111">Remarks</span></span>  
 <span data-ttu-id="009b7-112">`ModuleBindInfo` viene passato come parametro a `IHostAssemblyStore::ProvideModule`.</span><span class="sxs-lookup"><span data-stu-id="009b7-112">`ModuleBindInfo` is passed as a parameter to `IHostAssemblyStore::ProvideModule`.</span></span> <span data-ttu-id="009b7-113">L'host fornisce l'identificatore univoco `dwAppDomainId` al Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="009b7-113">The host supplies the unique identifier `dwAppDomainId` to the common language runtime (CLR).</span></span> <span data-ttu-id="009b7-114">Dopo che una chiamata al metodo [IHostAssemblyStore::P rovideassembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) restituisce, il runtime usa l'identificatore per determinare se è stato eseguito il mapping del contenuto della `IStream`.</span><span class="sxs-lookup"><span data-stu-id="009b7-114">After a call to the [IHostAssemblyStore::ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) method returns, the runtime uses the identifier to determine whether the contents of the `IStream` have been mapped.</span></span> <span data-ttu-id="009b7-115">In tal caso, il runtime carica la copia esistente anziché rimappare il flusso.</span><span class="sxs-lookup"><span data-stu-id="009b7-115">If so, the runtime loads the existing copy rather than remapping the stream.</span></span> <span data-ttu-id="009b7-116">Il runtime usa anche questo identificatore come chiave di ricerca per i flussi restituiti dalle chiamate al metodo `IHostAssemblyStore::ProvideAssembly`.</span><span class="sxs-lookup"><span data-stu-id="009b7-116">The runtime also uses this identifier as a lookup key for streams that are returned from calls to the `IHostAssemblyStore::ProvideAssembly` method.</span></span> <span data-ttu-id="009b7-117">Pertanto, l'identificatore deve essere univoco per le richieste di modulo e per le richieste di assembly.</span><span class="sxs-lookup"><span data-stu-id="009b7-117">Therefore, the identifier must be unique for module requests as well as for assembly requests.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="009b7-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="009b7-118">Requirements</span></span>  
 <span data-ttu-id="009b7-119">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="009b7-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="009b7-120">**Intestazione:** MSCorEE. idl</span><span class="sxs-lookup"><span data-stu-id="009b7-120">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="009b7-121">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="009b7-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="009b7-122">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="009b7-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="009b7-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="009b7-123">See also</span></span>

- [<span data-ttu-id="009b7-124">Strutture di hosting</span><span class="sxs-lookup"><span data-stu-id="009b7-124">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
- [<span data-ttu-id="009b7-125">Struttura AssemblyBindInfo</span><span class="sxs-lookup"><span data-stu-id="009b7-125">AssemblyBindInfo Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/assemblybindinfo-structure.md)
- [<span data-ttu-id="009b7-126">Interfaccia ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="009b7-126">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="009b7-127">Interfaccia ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="009b7-127">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="009b7-128">Interfaccia IHostAssemblyManager</span><span class="sxs-lookup"><span data-stu-id="009b7-128">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
