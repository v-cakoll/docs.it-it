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
ms.openlocfilehash: 31be0525c637e50c1161129277d651b56dadfaa3
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84006753"
---
# <a name="modulebindinfo-structure"></a><span data-ttu-id="616b8-102">Struttura ModuleBindInfo</span><span class="sxs-lookup"><span data-stu-id="616b8-102">ModuleBindInfo Structure</span></span>
<span data-ttu-id="616b8-103">Fornisce informazioni dettagliate sul modulo a cui si fa riferimento e sull'assembly che la contiene.</span><span class="sxs-lookup"><span data-stu-id="616b8-103">Provides detailed information about the referenced module and the assembly that contains it.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="616b8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="616b8-104">Syntax</span></span>  
  
```cpp  
typedef struct _ModuleBindInfo {  
    DWORD    dwAppDomainId;  
    LPCWSTR  lpAssemblyIdentity;  
    LPCWSTR  lpModuleName  
} ModuleBindInfo;  
```  
  
## <a name="members"></a><span data-ttu-id="616b8-105">Membri</span><span class="sxs-lookup"><span data-stu-id="616b8-105">Members</span></span>  
  
|<span data-ttu-id="616b8-106">Membro</span><span class="sxs-lookup"><span data-stu-id="616b8-106">Member</span></span>|<span data-ttu-id="616b8-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="616b8-107">Description</span></span>|  
|------------|-----------------|  
|`dwAppDomainId`|<span data-ttu-id="616b8-108">Identificatore univoco dell'oggetto `IStream` restituito da una chiamata al metodo [IHostAssemblyStore::P rovidemodule](ihostassemblystore-providemodule-method.md) da cui deve essere caricato il modulo a cui si fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="616b8-108">A unique identifier for the `IStream` that is returned by a call to the [IHostAssemblyStore::ProvideModule](ihostassemblystore-providemodule-method.md) method from which the referenced module is to be loaded.</span></span>|  
|`lpAssemblyIdentity`|<span data-ttu-id="616b8-109">Identificatore univoco per l'assembly che contiene il modulo a cui si fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="616b8-109">A unique identifier for the assembly that contains the referenced module.</span></span>|  
|`lpModuleName`|<span data-ttu-id="616b8-110">Nome del modulo a cui si fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="616b8-110">The name of the referenced module.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="616b8-111">Commenti</span><span class="sxs-lookup"><span data-stu-id="616b8-111">Remarks</span></span>  
 <span data-ttu-id="616b8-112">`ModuleBindInfo`viene passato come parametro a `IHostAssemblyStore::ProvideModule` .</span><span class="sxs-lookup"><span data-stu-id="616b8-112">`ModuleBindInfo` is passed as a parameter to `IHostAssemblyStore::ProvideModule`.</span></span> <span data-ttu-id="616b8-113">L'host fornisce l'identificatore univoco `dwAppDomainId` al Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="616b8-113">The host supplies the unique identifier `dwAppDomainId` to the common language runtime (CLR).</span></span> <span data-ttu-id="616b8-114">Dopo che una chiamata al metodo [IHostAssemblyStore::P rovideassembly](ihostassemblystore-provideassembly-method.md) restituisce, il runtime usa l'identificatore per determinare se `IStream` è stato eseguito il mapping del contenuto di.</span><span class="sxs-lookup"><span data-stu-id="616b8-114">After a call to the [IHostAssemblyStore::ProvideAssembly](ihostassemblystore-provideassembly-method.md) method returns, the runtime uses the identifier to determine whether the contents of the `IStream` have been mapped.</span></span> <span data-ttu-id="616b8-115">In tal caso, il runtime carica la copia esistente anziché rimappare il flusso.</span><span class="sxs-lookup"><span data-stu-id="616b8-115">If so, the runtime loads the existing copy rather than remapping the stream.</span></span> <span data-ttu-id="616b8-116">Il runtime usa anche questo identificatore come chiave di ricerca per i flussi restituiti dalle chiamate al `IHostAssemblyStore::ProvideAssembly` metodo.</span><span class="sxs-lookup"><span data-stu-id="616b8-116">The runtime also uses this identifier as a lookup key for streams that are returned from calls to the `IHostAssemblyStore::ProvideAssembly` method.</span></span> <span data-ttu-id="616b8-117">Pertanto, l'identificatore deve essere univoco per le richieste di modulo e per le richieste di assembly.</span><span class="sxs-lookup"><span data-stu-id="616b8-117">Therefore, the identifier must be unique for module requests as well as for assembly requests.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="616b8-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="616b8-118">Requirements</span></span>  
 <span data-ttu-id="616b8-119">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="616b8-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="616b8-120">**Intestazione:** MSCorEE. idl</span><span class="sxs-lookup"><span data-stu-id="616b8-120">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="616b8-121">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="616b8-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="616b8-122">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="616b8-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="616b8-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="616b8-123">See also</span></span>

- [<span data-ttu-id="616b8-124">Strutture di hosting</span><span class="sxs-lookup"><span data-stu-id="616b8-124">Hosting Structures</span></span>](hosting-structures.md)
- [<span data-ttu-id="616b8-125">Struttura AssemblyBindInfo</span><span class="sxs-lookup"><span data-stu-id="616b8-125">AssemblyBindInfo Structure</span></span>](assemblybindinfo-structure.md)
- [<span data-ttu-id="616b8-126">Interfaccia ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="616b8-126">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="616b8-127">Interfaccia ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="616b8-127">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="616b8-128">Interfaccia IHostAssemblyManager</span><span class="sxs-lookup"><span data-stu-id="616b8-128">IHostAssemblyManager Interface</span></span>](ihostassemblymanager-interface.md)
