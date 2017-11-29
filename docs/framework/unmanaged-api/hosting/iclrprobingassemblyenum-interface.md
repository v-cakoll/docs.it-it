---
title: Interfaccia ICLRProbingAssemblyEnum
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRProbingAssemblyEnum
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRProbingAssemblyEnum
helpviewer_keywords: ICLRProbingAssemblyEnum interface [.NET Framework hosting]
ms.assetid: e7d3ccab-b0f0-4872-8935-0ed72920171b
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6d810ab6e62c6df1b00305947de552ecdbe82141
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="iclrprobingassemblyenum-interface"></a><span data-ttu-id="6a9a3-102">Interfaccia ICLRProbingAssemblyEnum</span><span class="sxs-lookup"><span data-stu-id="6a9a3-102">ICLRProbingAssemblyEnum Interface</span></span>
<span data-ttu-id="6a9a3-103">Fornisce metodi che consentono all'host ottenere l'identità di ricerca di un assembly utilizzando le informazioni di identità dell'assembly sono interne a common language runtime (CLR), senza la necessità di creare o riconoscere l'identità.</span><span class="sxs-lookup"><span data-stu-id="6a9a3-103">Provides methods that enable the host to get the probing identities of an assembly by using the assembly's identity information that is internal to the common language runtime (CLR), without needing to create or understand that identity.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6a9a3-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="6a9a3-104">Methods</span></span>  
  
|<span data-ttu-id="6a9a3-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="6a9a3-105">Method</span></span>|<span data-ttu-id="6a9a3-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6a9a3-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6a9a3-107">Get (metodo)</span><span class="sxs-lookup"><span data-stu-id="6a9a3-107">Get Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-get-method.md)|<span data-ttu-id="6a9a3-108">Ottiene l'identità dell'assembly in corrispondenza dell'indice specificato.</span><span class="sxs-lookup"><span data-stu-id="6a9a3-108">Gets the assembly identity at the specified index.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6a9a3-109">Note</span><span class="sxs-lookup"><span data-stu-id="6a9a3-109">Remarks</span></span>  
 <span data-ttu-id="6a9a3-110">I metodi come [ICLRAssemblyIdentityManager::](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getprobingassembliesfromreference-method.md) restituiscono un `ICLRProbingAssemblyEnum` istanza.</span><span class="sxs-lookup"><span data-stu-id="6a9a3-110">Methods such as [ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getprobingassembliesfromreference-method.md) return an `ICLRProbingAssemblyEnum` instance.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6a9a3-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6a9a3-111">Requirements</span></span>  
 <span data-ttu-id="6a9a3-112">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6a9a3-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6a9a3-113">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="6a9a3-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6a9a3-114">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6a9a3-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6a9a3-115">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6a9a3-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a9a3-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6a9a3-116">See Also</span></span>  
 [<span data-ttu-id="6a9a3-117">ICLRAssemblyIdentityManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="6a9a3-117">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 [<span data-ttu-id="6a9a3-118">ICLRAssemblyReferenceList (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="6a9a3-118">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [<span data-ttu-id="6a9a3-119">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="6a9a3-119">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
