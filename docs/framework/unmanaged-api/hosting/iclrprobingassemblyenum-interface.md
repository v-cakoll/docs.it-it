---
title: Interfaccia ICLRProbingAssemblyEnum
ms.date: 03/30/2017
api_name:
- ICLRProbingAssemblyEnum
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRProbingAssemblyEnum
helpviewer_keywords:
- ICLRProbingAssemblyEnum interface [.NET Framework hosting]
ms.assetid: e7d3ccab-b0f0-4872-8935-0ed72920171b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c295a5633dedf1f0c85a9a697fea5524ee03fafc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33432698"
---
# <a name="iclrprobingassemblyenum-interface"></a><span data-ttu-id="815e8-102">Interfaccia ICLRProbingAssemblyEnum</span><span class="sxs-lookup"><span data-stu-id="815e8-102">ICLRProbingAssemblyEnum Interface</span></span>
<span data-ttu-id="815e8-103">Fornisce metodi che consentono all'host ottenere l'identità di ricerca di un assembly utilizzando le informazioni di identità dell'assembly sono interne a common language runtime (CLR), senza la necessità di creare o riconoscere l'identità.</span><span class="sxs-lookup"><span data-stu-id="815e8-103">Provides methods that enable the host to get the probing identities of an assembly by using the assembly's identity information that is internal to the common language runtime (CLR), without needing to create or understand that identity.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="815e8-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="815e8-104">Methods</span></span>  
  
|<span data-ttu-id="815e8-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="815e8-105">Method</span></span>|<span data-ttu-id="815e8-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="815e8-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="815e8-107">Metodo Get</span><span class="sxs-lookup"><span data-stu-id="815e8-107">Get Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-get-method.md)|<span data-ttu-id="815e8-108">Ottiene l'identità dell'assembly in corrispondenza dell'indice specificato.</span><span class="sxs-lookup"><span data-stu-id="815e8-108">Gets the assembly identity at the specified index.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="815e8-109">Note</span><span class="sxs-lookup"><span data-stu-id="815e8-109">Remarks</span></span>  
 <span data-ttu-id="815e8-110">I metodi come [ICLRAssemblyIdentityManager::](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getprobingassembliesfromreference-method.md) restituiscono un `ICLRProbingAssemblyEnum` istanza.</span><span class="sxs-lookup"><span data-stu-id="815e8-110">Methods such as [ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getprobingassembliesfromreference-method.md) return an `ICLRProbingAssemblyEnum` instance.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="815e8-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="815e8-111">Requirements</span></span>  
 <span data-ttu-id="815e8-112">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="815e8-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="815e8-113">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="815e8-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="815e8-114">**Libreria:** inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="815e8-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="815e8-115">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="815e8-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="815e8-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="815e8-116">See Also</span></span>  
 [<span data-ttu-id="815e8-117">Interfaccia ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="815e8-117">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 [<span data-ttu-id="815e8-118">Interfaccia ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="815e8-118">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [<span data-ttu-id="815e8-119">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="815e8-119">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
