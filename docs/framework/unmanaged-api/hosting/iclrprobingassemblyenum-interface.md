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
ms.openlocfilehash: 118345f246de3d7ee68d51cf37e8cdea9de1fdba
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59094294"
---
# <a name="iclrprobingassemblyenum-interface"></a><span data-ttu-id="67a9e-102">Interfaccia ICLRProbingAssemblyEnum</span><span class="sxs-lookup"><span data-stu-id="67a9e-102">ICLRProbingAssemblyEnum Interface</span></span>
<span data-ttu-id="67a9e-103">Fornisce metodi che consentono l'host per cui ottenere l'identità di ricerca di un assembly con le informazioni di identità dell'assembly che sono interne di common language runtime (CLR), senza dover creare o comprendere tale identità.</span><span class="sxs-lookup"><span data-stu-id="67a9e-103">Provides methods that enable the host to get the probing identities of an assembly by using the assembly's identity information that is internal to the common language runtime (CLR), without needing to create or understand that identity.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="67a9e-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="67a9e-104">Methods</span></span>  
  
|<span data-ttu-id="67a9e-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="67a9e-105">Method</span></span>|<span data-ttu-id="67a9e-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="67a9e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="67a9e-107">Metodo Get</span><span class="sxs-lookup"><span data-stu-id="67a9e-107">Get Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-get-method.md)|<span data-ttu-id="67a9e-108">Ottiene l'identità dell'assembly in corrispondenza dell'indice specificato.</span><span class="sxs-lookup"><span data-stu-id="67a9e-108">Gets the assembly identity at the specified index.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="67a9e-109">Note</span><span class="sxs-lookup"><span data-stu-id="67a9e-109">Remarks</span></span>  
 <span data-ttu-id="67a9e-110">I metodi come [ICLRAssemblyIdentityManager](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getprobingassembliesfromreference-method.md) restituiscono una `ICLRProbingAssemblyEnum` istanza.</span><span class="sxs-lookup"><span data-stu-id="67a9e-110">Methods such as [ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getprobingassembliesfromreference-method.md) return an `ICLRProbingAssemblyEnum` instance.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="67a9e-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="67a9e-111">Requirements</span></span>  
 <span data-ttu-id="67a9e-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="67a9e-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="67a9e-113">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="67a9e-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="67a9e-114">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="67a9e-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="67a9e-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="67a9e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67a9e-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="67a9e-116">See also</span></span>

- [<span data-ttu-id="67a9e-117">Interfaccia ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="67a9e-117">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="67a9e-118">Interfaccia ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="67a9e-118">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="67a9e-119">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="67a9e-119">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
