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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f14d3dcaad1cc8cac11599b1647d61df3a793301
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61765180"
---
# <a name="modulebindinfo-structure"></a><span data-ttu-id="4cb74-102">Struttura ModuleBindInfo</span><span class="sxs-lookup"><span data-stu-id="4cb74-102">ModuleBindInfo Structure</span></span>
<span data-ttu-id="4cb74-103">Fornisce informazioni dettagliate sul modulo cui viene fatto riferimento e l'assembly che lo contiene.</span><span class="sxs-lookup"><span data-stu-id="4cb74-103">Provides detailed information about the referenced module and the assembly that contains it.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4cb74-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4cb74-104">Syntax</span></span>  
  
```  
typedef struct _ModuleBindInfo {  
    DWORD    dwAppDomainId;  
    LPCWSTR  lpAssemblyIdentity;  
    LPCWSTR  lpModuleName  
} ModuleBindInfo;  
```  
  
## <a name="members"></a><span data-ttu-id="4cb74-105">Membri</span><span class="sxs-lookup"><span data-stu-id="4cb74-105">Members</span></span>  
  
|<span data-ttu-id="4cb74-106">Member</span><span class="sxs-lookup"><span data-stu-id="4cb74-106">Member</span></span>|<span data-ttu-id="4cb74-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4cb74-107">Description</span></span>|  
|------------|-----------------|  
|`dwAppDomainId`|<span data-ttu-id="4cb74-108">Un identificatore univoco per il `IStream` restituito da una chiamata ai [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-providemodule-method.md) metodo da cui è possibile caricare il modulo di cui viene fatto riferimento.</span><span class="sxs-lookup"><span data-stu-id="4cb74-108">A unique identifier for the `IStream` that is returned by a call to the [IHostAssemblyStore::ProvideModule](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-providemodule-method.md) method from which the referenced module is to be loaded.</span></span>|  
|`lpAssemblyIdentity`|<span data-ttu-id="4cb74-109">Identificatore univoco per l'assembly che contiene il modulo di cui viene fatto riferimento.</span><span class="sxs-lookup"><span data-stu-id="4cb74-109">A unique identifier for the assembly that contains the referenced module.</span></span>|  
|`lpModuleName`|<span data-ttu-id="4cb74-110">Il nome del modulo cui viene fatto riferimento.</span><span class="sxs-lookup"><span data-stu-id="4cb74-110">The name of the referenced module.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4cb74-111">Note</span><span class="sxs-lookup"><span data-stu-id="4cb74-111">Remarks</span></span>  
 <span data-ttu-id="4cb74-112">`ModuleBindInfo` viene passato come parametro al `IHostAssemblyStore::ProvideModule`.</span><span class="sxs-lookup"><span data-stu-id="4cb74-112">`ModuleBindInfo` is passed as a parameter to `IHostAssemblyStore::ProvideModule`.</span></span> <span data-ttu-id="4cb74-113">L'identificatore univoco viene fornito dall'host `dwAppDomainId` a common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="4cb74-113">The host supplies the unique identifier `dwAppDomainId` to the common language runtime (CLR).</span></span> <span data-ttu-id="4cb74-114">Dopo una chiamata al [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) metodo viene restituito, il runtime usa l'identificatore per determinare se il contenuto del `IStream` sono stati mappati.</span><span class="sxs-lookup"><span data-stu-id="4cb74-114">After a call to the [IHostAssemblyStore::ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) method returns, the runtime uses the identifier to determine whether the contents of the `IStream` have been mapped.</span></span> <span data-ttu-id="4cb74-115">In questo caso, il runtime carica la copia esistente anziché la modifica del flusso.</span><span class="sxs-lookup"><span data-stu-id="4cb74-115">If so, the runtime loads the existing copy rather than remapping the stream.</span></span> <span data-ttu-id="4cb74-116">Il runtime usa anche questo identificatore come chiave di ricerca per i flussi che vengono restituiti dalle chiamate al `IHostAssemblyStore::ProvideAssembly` (metodo).</span><span class="sxs-lookup"><span data-stu-id="4cb74-116">The runtime also uses this identifier as a lookup key for streams that are returned from calls to the `IHostAssemblyStore::ProvideAssembly` method.</span></span> <span data-ttu-id="4cb74-117">Pertanto, l'identificatore deve essere univoco per le richieste di modulo anche per quanto riguarda le richieste di assembly.</span><span class="sxs-lookup"><span data-stu-id="4cb74-117">Therefore, the identifier must be unique for module requests as well as for assembly requests.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4cb74-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4cb74-118">Requirements</span></span>  
 <span data-ttu-id="4cb74-119">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4cb74-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4cb74-120">**Intestazione:** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="4cb74-120">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="4cb74-121">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="4cb74-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4cb74-122">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4cb74-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4cb74-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4cb74-123">See also</span></span>

- [<span data-ttu-id="4cb74-124">Strutture di hosting</span><span class="sxs-lookup"><span data-stu-id="4cb74-124">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
- [<span data-ttu-id="4cb74-125">Struttura AssemblyBindInfo</span><span class="sxs-lookup"><span data-stu-id="4cb74-125">AssemblyBindInfo Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/assemblybindinfo-structure.md)
- [<span data-ttu-id="4cb74-126">Interfaccia ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="4cb74-126">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="4cb74-127">Interfaccia ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="4cb74-127">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="4cb74-128">Interfaccia IHostAssemblyManager</span><span class="sxs-lookup"><span data-stu-id="4cb74-128">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
